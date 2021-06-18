---
layout: page
title: Determinants & Inverses
---
## Introduction
Previously the work with matrices has been multiplication, scaling, and linear transformations. With linear transformations, it was found that an object could be moved, and scaled in 2D and 3D space. This lesson will focus on getting the object back to its original position.

## Determinants
### Key Concepts
The key concepts for this part of the lesson are:
* Definition of a determinant
* Calculating a determinant for a 2x2, 3x3, and 4x4 matrices

## Lesson
Every square matrix has a special property called the determinant. The determinant is used to create an inverse matrix from a given matrix such that <img src="https://latex.codecogs.com/svg.latex?\large&space;M\times{M^(-1)}=I"/>. Not every square matrix has an inverse, as will be covered later in this lesson, but for now that is the purpose of covering determinants. It is important to get an understanding of what a determinant is before it is calculated.

Given the matrix:

<img src="https://latex.codecogs.com/svg.latex?\large&space;M=\left[\begin{array}{cc}3&1\\1&2\end{array}\right]"/>

The matrix can be graphically represented by plotting its basis vectors and creating a parallelogram with the determinant of the matrix equal to the area of the parallelogram:

![parallelogram](files/parallelogram.jpg)

Now that a determinant of a 2x2 matrix can be shown graphically the next step is to compute the determinant mathematically. The determinant of **M** is written as <img src="https://latex.codecogs.com/svg.latex?\large&space;detM"/> or <img src="https://latex.codecogs.com/svg.latex?\large&space;\vert{M}\vert"/> (note this symbol is not the absolute value).

<img src="https://latex.codecogs.com/svg.latex?\large&space;\vert{M}\vert=\left|\begin{array}{cc}M_{11}&M_{12}\\M_{21}&M_{22}\end{array}\right|=M_{11}M_{22}-M_{12}M_{21}"/>

<img src="https://latex.codecogs.com/svg.latex?\large&space;\vert{M}\vert=\left|\begin{array}{cc}3&1\\1&2\end{array}\right|=(3)(2)-(1)(1)=5"/>

The computed value of a determinant is not always a positive number; it can be negative or even zero. For example, given the matrix below:

<img src="https://latex.codecogs.com/svg.latex?\large&space;\vert{M}\vert=\left|\begin{array}{cc}-3&2\\4&5\end{array}\right|=(-3)(5)-(2)(4)=-23"/>

