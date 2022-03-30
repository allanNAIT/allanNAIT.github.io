---
layout: page
title: Cross Product
---
<style>
    .red{
        color:red;
        font-weight: bold;
    }
</style>

## Introduction
The other key vector concept is that of the Cross Product. The Cross Product differs from the Dot Product, whose result is a scalar, in that it produces another 3D vector. <span class="red">There is NO Cross Product for 2D vectors.</span>

## Cross Product
### Key Concepts
The key concepts for this part of the lesson are:
* Computing a Cross Product
* Computing the Surface Normal

### Lesson
As stated in the previous lesson, the multiplication of vectors is different from multiplying scalar values. For example, we know that:

<img src="https://latex.codecogs.com/svg.latex?\large&space;\left[\begin{array}{c}2 \\ 3 \\4\end{array}\right]\cdot{\left[\begin{array}{c}5 \\ 2 \\ -2\end{array}\right]}=10+(-6)+(-8)=-4"/>

However, the other symbol for multiplication, `x`, produces a different result:

<img src="https://latex.codecogs.com/svg.latex?\large&space;\left[\begin{array}{c}2 \\ 3 \\4\end{array}\right]\times{\left[\begin{array}{c}5 \\ 2 \\ -2\end{array}\right]}=\left[\begin{array}{c}-2 \\ 24 \\ 19\end{array}\right]"/>

Looking at this result the computation is not obvious.

With <img src="https://latex.codecogs.com/svg.latex?\large&space;A\times{B}=\left[\begin{array}{c}A_{x} \\ A_{y} \\ A_{z}\end{array}\right]\times{\left[\begin{array}{c}B_{x} \\ B_{y} \\ B_{z}\end{array}\right]}"/> then <img src="https://latex.codecogs.com/svg.latex?\large&space;a=A_{y}B_{z}-A_{z}B_{y}"/>

Next <img src="https://latex.codecogs.com/svg.latex?\large&space;A\times{B}=\left[\begin{array}{c}A_{x} \\ A_{y} \\ A_{z}\end{array}\right]\times{\left[\begin{array}{c}B_{x} \\ B_{y} \\ B_{z}\end{array}\right]}"/> then <img src="https://latex.codecogs.com/svg.latex?\large&space;b=A_{z}B_{x}-A_{x}B_{z}"/>

Finally <img src="https://latex.codecogs.com/svg.latex?\large&space;A\times{B}=\left[\begin{array}{c}A_{x} \\ A_{y} \\ A_{z}\end{array}\right]\times{\left[\begin{array}{c}B_{x} \\ B_{y} \\ B_{z}\end{array}\right]}"/> then <img src="https://latex.codecogs.com/svg.latex?\large&space;c=A_{x}B_{y}-A_{y}B_{x}"/>

Therefore we get <img src="https://latex.codecogs.com/svg.latex?\large&space;A\times{B}=\left[\begin{array}{c}(A_{y}B_{z}-A_{z}B_{y}) \\ (A_{z}B_{x}-A_{x}B_{z}) \\ (A_{x}B_{y}-A_{y}B_{x})\end{array}\right]"/>

Using our intial example we get:

<img src="https://latex.codecogs.com/svg.latex?\large&space;\left[\begin{array}{c}2 \\ 3 \\4\end{array}\right]\times{\left[\begin{array}{c}5 \\ 2 \\ -2\end{array}\right]}=\left[\begin{array}{c}(-3)(-2)-(4)(2)\\ (4)(5)-(2)(-2) \\ (2)(2)-(-3)(5)\end{array}\right]=\left[\begin{array}{c}-2 \\ 24 \\ 19\end{array}\right]"/>

It is best if another example is used. This example also has a graphical representation in, 3D, of the Cross Product.

Given the 3D vectors of <img src="https://latex.codecogs.com/svg.latex?\large&space;A=\left[\begin{array}{c}1 \\ 3 \\ -2\end{array}\right]"/> and <img src="https://latex.codecogs.com/svg.latex?\large&space;B=\left[\begin{array}{c}2 \\ -4 \\ 4\end{array}\right]"/> we can calculate the Cross Product as:

<img src="https://latex.codecogs.com/svg.latex?\large&space;A\times{B}=\left[\begin{array}{c}(3)(4)-(-2)(-4) \\ (-2)(2)-(1)(4) \\ (1)(-4)-(3)(2)\end{array}\right]=\left[\begin{array}{c}12-8 \\ -4-4 \\ -4-6\end{array}\right]=\left[\begin{array}{c}4 \\ -8 \\ -10\end{array}\right]"/>

![cross-product-example](files/cross-product-example.jpg)<br>
![cross-product-graphical](files/cross-product-graphical.jpg)<br>
![cross-product-graphical-perpendicular](files/cross-product-graphical-perpendicular.jpg)

The first graphical view shows a vector that is perpendicular to A and B, which is the result of the Cross Product, and shows a vector <img src="https://latex.codecogs.com/svg.latex?\large&space;\frac{A\times{B}}{\Vert{A\times{B}}\Vert}"/>, this vector is sometimes called the Surface Normal. The second graphical view shows, as best that can be done, that the **normalized** Cross Product is perpendicular to both A and B.

The concept of a **normalized** vector was previously covered. It is an important concept that students need to know. A **normalized** vector has a magnitude of 1. It is computed by dividing each vector component by the magnitude of the vector.

Geometrically it can be shown that:

<img src="https://latex.codecogs.com/svg.latex?\large&space;\Vert{A\times{B}}\Vert=(\Vert{A}\Vert)(\Vert{B}\Vert)(sin(\theta))"/>

This result is equal to the area of the parallelogram formed by the two sides A and B.

The true meaning of a **Surface Normal** depends on the type of surface. The simplest type of surface is one formed by three points in 3D coordinate space. To find the surface normal of the plane formed by these three points, use the following steps:
1.	Choose one point as a reference point.
2.	Determine the vectors from the reference point to the other two points that determine the plane.
3.	Calculate the Cross Product of the vectors from step 2.
4.	Normalize the calculation from step 3.

### Example
Given three points <img src="https://latex.codecogs.com/svg.latex?\large&space;A=(3,2,4)"/>, <img src="https://latex.codecogs.com/svg.latex?\large&space;B=(-2,3,-4)"/>, and <img src="https://latex.codecogs.com/svg.latex?\large&space;C=(4,-2,3)"/>, calculate the surface normal.

Using **A** as the reference point, the vectors <img src="https://latex.codecogs.com/svg.latex?\large&space;\vec{AB}"/> and <img src="https://latex.codecogs.com/svg.latex?\large&space;\vec{AC}"/> are calculated as follows:

<img src="https://latex.codecogs.com/svg.latex?\large&space;V_{1}=B-A=\left[\begin{array}{c}-2-3 \\ 3-2 \\ -4-4\end{array}\right]=\left[\begin{array}{c}-5 \\ 1 \\ 8\end{array}\right]"/>

<img src="https://latex.codecogs.com/svg.latex?\large&space;V_{2}=B-A=\left[\begin{array}{c}4-3\\ -2-2 \\ 3-4\end{array}\right]=\left[\begin{array}{c}1 \\ -4 \\ -1\end{array}\right]"/>

Next calculate <img src="https://latex.codecogs.com/svg.latex?\large&space;V_{1}\times{V_{2}}"/> (the Cross product):

<img src="https://latex.codecogs.com/svg.latex?\large&space;N=V_{1}\times{V_{2}}=\left[\begin{array}{c}-5 \\ 1 \\ 8\end{array}\right]\times{\left[\begin{array}{c}1 \\ -4 \\ -1\end{array}\right]}=\left[\begin{array}{c}(1)(-1)-(-4)(-8) \\ (-8)(1)-(-5)(-1) \\ (-5)(-4)-(1)(1)\end{array}\right]=\left[\begin{array}{c}-33 \\ -13 \\ 19\end{array}\right]"/>

Finally, normalize the Cross Product:

<img src="https://latex.codecogs.com/svg.latex?\large&space;\Vert{N}\Vert=\sqrt{(-33)^2+(-13)^2+(19)^2}=\sqrt{1619}"/>

<img src="https://latex.codecogs.com/svg.latex?\large&space;\hat{N}=\frac{1}{\sqrt{1619}}\left[\begin{array}{c}-33 \\ -13 \\ 19\end{array}\right]\approx{\left[\begin{array}{c}-0.8201 \\ -0.3231 \\ 0.4772\end{array}\right]}"/>

![surface-normal-solution-1](files/surface-normal-solution-1.jpg)

As we can choose any of the three points as a reference point, selecting a different point as a reference point will give a different resulting Surface Normal (A and C swapped; C is the reference point):

![surface-normal-solution-2](files/surface-normal-solution-2.jpg)

## Exercises & Assignments
Complete the [Vector Exercises Part 3](vector-worksheet-3.md) worksheet. Once complete proceed to Moodle to complete Knowledge Check 04 - Vectors Pt. 3 (Cross Product) (strongly recommended to be completed prior to attempting Lab 1).

#### [Outcome Home](index.md)
#### [PHYS1521 Home](../)