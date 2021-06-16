---
layout: page
title: Cross Product
---
<style>
    .red{
        color:red;
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

Next <img src="https://latex.codecogs.com/svg.latex?\large&space;A\times{B}=\left[\begin{array}{c}A_{x} \\ A_{y} \\ A_{z}\end{array}\right]\times{\left[\begin{array}{c}B_{x} \\ B_{y} \\ B_{z}\end{array}\right]}"/> then <img src="https://latex.codecogs.com/svg.latex?\large&space;a=A_{z}B_{x}-A_{x}B_{z}"/>

Finally <img src="https://latex.codecogs.com/svg.latex?\large&space;A\times{B}=\left[\begin{array}{c}A_{x} \\ A_{y} \\ A_{z}\end{array}\right]\times{\left[\begin{array}{c}B_{x} \\ B_{y} \\ B_{z}\end{array}\right]}"/> then <img src="https://latex.codecogs.com/svg.latex?\large&space;a=A_{x}B_{y}-A_{y}B_{x}"/>

Therefore we get <img src="https://latex.codecogs.com/svg.latex?\large&space;A\times{B}=\left[\begin{array}{c}(A_{y}B_{z}-A_{z}B_{y}) \\ (A_{z}B_{x}-A_{x}B_{z}) \\ (A_{x}B_{y}-A_{y}B_{x})\end{array}\right]"/>

Using our intial example we get:

<img src="https://latex.codecogs.com/svg.latex?\large&space;\left[\begin{array}{c}2 \\ 3 \\4\end{array}\right]\times{\left[\begin{array}{c}5 \\ 2 \\ -2\end{array}\right]}=\left[\begin{array}{c}(-3)(-2)-(4)(2)\\ (4)(5)-(2)(-2) \\ (2)(2)-(-3)(5)\end{array}\right]=\left[\begin{array}{c}-2 \\ 24 \\ 19\end{array}\right]"/>

It is best if another example is used. This example also has a graphical representation in, 3D, of the Cross Product.

Given the 3D vectors of <img src="https://latex.codecogs.com/svg.latex?\large&space;A=\left[\begin{array}{c}1 \\ 3 \\ -2\end{array}\right]"/> and <img src="https://latex.codecogs.com/svg.latex?\large&space;B=\left[\begin{array}{c}2 \\ -4 \\ 4\end{array}\right]"/> we can calculate the Cross Product as:

<img src="https://latex.codecogs.com/svg.latex?\large&space;A\times{B}=\left[\begin{array}{c}(3)(4)-(-2)(-4) \\ (-2)(2)-(1)(4) \\ (1)(-4)-(3)(2)\end{array}\right]=\left[\begin{array}{c}12-8 \\ -4-4 \\ -4-6\end{array}\right]=\left[\begin{array}{c}4 \\ -8 \\ -10\end{array}\right]"/>

![cross-product-example](files/cross-product-example.jpg)<br>
![cross-product-graphical](files/cross-product-graphical.jpg)<br>
![cross-product-graphical-perpendicular](files/cross-product-graphical-perpendicular.jpg)



### [Outcome Home](outcome1.md)
### [PHYS1521 Home](../)