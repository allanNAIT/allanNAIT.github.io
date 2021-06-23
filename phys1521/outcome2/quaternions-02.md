---
layout: page
title: Rotate Vector by Quaternion
---
## Introduction
Previously we were able to convert Euler angles to a Quaternion, and a Quaternion to a Matrix. In game programming we want fast 3D rotations, thus this lesson outlines how to rotate a vector by a Quaternion.

## References
* [Faster Quaternion-Vector Multiplication](https://blog.molecular-matters.com/2013/05/24/a-faster-quaternion-vector-multiplication/){:target="_blank"}
* [Rotating a Vector by a Quaternion](https://fgiesen.wordpress.com/2019/02/09/rotating-a-single-vector-using-a-quaternion/){:target="_blank"}

## Matrix Method
### Key Concepts
The key concepts of this part of the lesson are:
* Review of previous concepts:
  * Create a Quaternion from Euler Angles
  * Create a Matrix from a Quaternion
  * Multiply a Vector by a Matrix

### Review Concepts
From Lesson 2.5 we learned that a Quaternion can be created from Euler angles as follows:

<img src="https://latex.codecogs.com/svg.latex?\large&space;Q=\left[\begin{array}{c}cos(\frac{Y}{2})\\\left(\begin{array}{c}0\\sin(\frac{Y}{2})\\0\end{array}\right)\end{array}\right]\left(\left[\begin{array}{c}cos(\frac{P}{2})\\\left(\begin{array}{c}sin(\frac{P}{2})\\0\\0\end{array}\right)\end{array}\right]\left[\begin{array}{c}cos(\frac{R}{2})\\\left(\begin{array}{c}0\\0\\sin(\frac{R}{2})\end{array}\right)\end{array}\right]\right)"/>

Also, from Lesson 2.5 we learned that the conversion of a Quaternion to a matrix was done by:

<img src="https://latex.codecogs.com/svg.latex?\large&space;R_{Q}=\left[\begin{array}{ccc}1-2(Q_{y}^2+Q_{z}^2)&2(Q_{x}Q_{y}-Q_{w}Q_{z})&2(Q_{x}Q_{z}+Q_{w}Q_{y})\\2(Q_{x}Q_{y}+Q_{w}Q_{z})&1-2(Q_{x}^2+Q_{z}^2)&2(Q_{y}Q_{z}-Q_{w}Q_{x})\\2(Q_{x}Q_{z}-Q_{w}Q_{y})&2(Q_{y}Q_{z}+Q_{w}Q_{x})&1-2(Q_{x}^2+Q_{y}^2)\end{array}\right]"/>

From Lesson 2.1 we learned that a vector multiplied by a matrix was done by:

<img src="https://latex.codecogs.com/svg.latex?\large&space;\left[\begin{array}{ccc}M_{11}&M_{12}&M_{13}\\M_{21}&M_{22}&M_{23}\\M_{31}&M_{32}&M_{33}\end{array}\right]\times{\left[\begin{array}{c}V_x\\V_y\\V_z\end{array}\right]}=\left[\begin{array}{c}V_xM_{11}+V_yM_{12}+V_zM_{13}\\V_xM_{21}+V_yM_{22}+V_zM_{23}\\V_xM_{31}+V_yM_{32}+V_zM_{33}\end{array}\right]={\left[\begin{array}{c}V_x\\V_y\\V_z\end{array}\right]}'"/>

Substitution gives us:

<img src="https://latex.codecogs.com/svg.latex?\large&space;R_{Q}=\left[\begin{array}{ccc}1-2(Q_{y}^2+Q_{z}^2)&2(Q_{x}Q_{y}-Q_{w}Q_{z})&2(Q_{x}Q_{z}+Q_{w}Q_{y})\\2(Q_{x}Q_{y}+Q_{w}Q_{z})&1-2(Q_{x}^2+Q_{z}^2)&2(Q_{y}Q_{z}-Q_{w}Q_{x})\\2(Q_{x}Q_{z}-Q_{w}Q_{y})&2(Q_{y}Q_{z}+Q_{w}Q_{x})&1-2(Q_{x}^2+Q_{y}^2)\end{array}\right]\times{\left[\begin{array}{c}V_x\\V_y\\V_z\end{array}\right]}={\left[\begin{array}{c}V_x\\V_y\\V_z\end{array}\right]}'"/>

Example
Given the Euler angles of Roll = 5<sup>o</sup>, Pitch = -10<sup>o</sup>, and Yaw = 15<sup>o</sup>, the resulting Quaternion would be:

<img src="https://latex.codecogs.com/svg.latex?\large&space;Q=\left[\begin{array}{c}0.98623585\\-0.08065606\\0.133679\\0.05444693\end{array}\right]"/>

The matrix would be (rounded to 4 decimal places):

<img src="https://latex.codecogs.com/svg.latex?\large&space;R_Q=\left[\begin{array}{ccc}0.9583&-0.1290&0.2549\\0.0858&0.9811&0.1736\\-0.2725&-0.1445&0.9513\end{array}\right]"/>

Now the final multiplication, given <img src="https://latex.codecogs.com/svg.latex?\large&space;V=\left[\begin{array}{c}2\\-3\\4\end{array}\right]"/> is:

<img src="https://latex.codecogs.com/svg.latex?\large&space;\left[\begin{array}{ccc}0.9583&-0.1290&0.2549\\0.0858&0.9811&0.1736\\-0.2725&-0.1445&0.9513\end{array}\right]\times{\left[\begin{array}{c}2\\-3\\4\end{array}\right]}=\left[\begin{array}{c}3.3231\\-2.0769\\3.6937\end{array}\right]"/>

## Direct (Optimized) Method
The reference for this lesson outlines the following equation for multiplying a vector by a Quaternion:

<img src="https://latex.codecogs.com/svg.latex?\large&space;V'=Q\times{V}\times{\bar{Q}}"/>

The product of two Quaternions is given by (given the two quaternions **A** and **B**, where a Quaternion is defined as <img src="https://latex.codecogs.com/svg.latex?\large&space;Q=(Q_r,Q_{xyz})"/>:

<img src="https://latex.codecogs.com/svg.latex?\large&space;AB=(A_rB_r-A_{xyz}\cdot{B_{xyz}},A_rB_{xyz}+B_rA_{xyz}+A_{xyz}\times{B_{xyz}})"/>

Also `V` must be treated like a Quaternion (i.e., <img src="https://latex.codecogs.com/svg.latex?\large&space;V_q=(0,V)"/>). The second reference goes through all the detail to get a faster method using the following steps:

<img src="https://latex.codecogs.com/svg.latex?\large&space;T=2\times{\left[\begin{array}{c}Q_x\\Q_y\\Q_z\end{array}\right]}\times{\left[\begin{array}{c}V_x\\V_y\\V_z\end{array}\right]}"/>

<img src="https://latex.codecogs.com/svg.latex?\large&space;V'=V+Q_w\times{T}+\left(\left[\begin{array}{c}Q_x\\Q_y\\Q_z\end{array}\right]\times{\left[\begin{array}{c}T_x\\T_y\\T_z\end{array}\right]}\right)"/>

The reference stated it was faster, thus the following comparison was done:

![vector-x-q-compare](files/vector-x-q-compare.jpg)

## Exercises & Assignments
Compare some previous calculations with this new method. This is the recommended approach for some of the calculations for Lab 2.

### [Outcome Home](outcome2.md)
### [PHYS1521 Home](../)