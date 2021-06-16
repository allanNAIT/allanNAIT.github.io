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

### [Outcome Home](outcome1.md)
### [PHYS1521 Home](../)