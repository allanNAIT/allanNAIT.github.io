---
layout: page
title: Linear Transformations
---
## Introduction
As mentioned earlier, matrices are used for transformation of objects (shifting, scaling, shearing, and rotation) in 2D and 3D coordinate spaces. In this lesson there is a bit of “jumping around” with the material. The rationale for this is that students need to understand how translation and scaling work in terms of 2D and 3D coordinate spaces, with the 3D coordinate space using a 4D homogeneous space, before covering rotations.

## Homogeneous Matrices
### Key Concepts
The key concepts for this part of the lesson are:
* The differences between 2D and 3D coordinate spaces for transformations

### Lesson
In a 2D coordinate system the z-axis is not shown (the z-axis is typically for a 3D coordinate system) but this axis plays a key role in transformations, and rotations (which will be covered in the next lesson). In the 2D system consider the z-axis as the focal point of all transformations. For example if an object needs to be moved from its current position to another position in the 2D plane there needs to be a standard reference point for the required transformation. This point will use the z-axis. Here it is important that the instructor choose whether to use row or column vectors as this choice needs to be consistent; the other option is to use both so that the students see both.

In a 2D system that is then extended to a 3D system the z-axis is used but there is no one focal axis that remains constant for any transformations, or rotations; in 3D there are now three axis that can be used for rotations, versus the implied z-axis in a 2D system. To get around this we extend the 3D system, <img src="https://latex.codecogs.com/svg.latex?\large&space;(x,y,z)"/> to a 4D system that is <img src="https://latex.codecogs.com/svg.latex?\large&space;(x,y,z,w)"/>; similarly, the 2D system can be extended from <img src="https://latex.codecogs.com/svg.latex?\large&space;(x,y)"/> to <img src="https://latex.codecogs.com/svg.latex?\large&space;(x,y,w)"/> to keep everything consistent as the z-axis is not really part of the 2D system. Typically the value of the w coordinate is 1. For example the point (2,3,-4) is a 3D system is represented as:

<img src="https://latex.codecogs.com/svg.latex?\large&space;\left[\begin{array}{cccc}2&3&-4&1\end{array}\right]"/>&nbsp;<b>OR</b>&nbsp;<img src="https://latex.codecogs.com/svg.latex?\large&space;\left[\begin{array}{c}2\\3\\-4\\1\end{array}\right]"/>

Similarly the homogeneous equivalent for the point (4, -1) in a 2D system is:

<img src="https://latex.codecogs.com/svg.latex?\large&space;\left[\begin{array}{ccc}4&-1&1\end{array}\right]"/>&nbsp;<b>OR</b>&nbsp;<img src="https://latex.codecogs.com/svg.latex?\large&space;\left[\begin{array}{c}4\\-1\\1\end{array}\right]"/>

## Transformations
### Key Concepts
The key concepts for this part of the lesson are:
* Construct a transformation matrix in 2D and 3D
* Shift a point (representing a single point of an object) in 2D and 3D space

### Lesson
As noted at the end of the last lesson two matrices were shown, with each representing a different graphics API system, which are shown below:

<img src="https://latex.codecogs.com/svg.latex?\large&space;T_{DX}^T={\left[\begin{array}{cccc}1&0&0&0\\0&1&0&0\\0&0&1&0\\T_{x}&T_{y}&T_{z}&1\end{array}\right]}^T=\left[\begin{array}{cccc}1&0&0&T_{x}\\0&1&0&T_{y}\\0&0&1&T_{z}\\0&0&0&1\end{array}\right]=T_{GL}"/>

Looking at T<sub>DX</sub> or T<sub>GL</sub> you should see that each 4x4 matrix uses the `w` coordinate axis. These matrices were introduced as transformations, but the term transformation was not formally explained. In this part of the lesson the transformation represented by these matrices is used to shift an object from one relative position to another position at a given displacement from the original position. Note that the T<sub>X</sub>, T<sub>Y</sub>, and T<sub>Z</sub> values represent components of the transformation.

By example in a 2D system there is a requirement to move an object from its current position to a position that is <img src="https://latex.codecogs.com/svg.latex?\large&space;(\Delta{x},\Delta{y})=(3,4)"/> from its original position. The transformation matrix for this action would be:

<img src="https://latex.codecogs.com/svg.latex?\large&space;\left[\begin{array}{ccc}1&0&T_{x}\\0&1&T_{y}\\0&0&1\end{array}\right]=\left[\begin{array}{ccc}1&0&3\\0&1&4\\0&0&1\end{array}\right]"/>

Given one point of the object at (-2, 4) the translated point would be:

<img src="https://latex.codecogs.com/svg.latex?\large&space;\left[\begin{array}{ccc}1&0&3\\0&1&4\\0&0&1\end{array}\right]\times{\left[\begin{array}{c}-2\\4\\1\end{array}\right]=\left[\begin{array}{c}(1)(-2)+(0)(4)+(3)(1)\\(0)(-2)+(1)(4)+(4)(1)\\(0)(-2)+(0)(4)+(1)(1)\end{array}\right]=\left[\begin{array}{c}1\\8\\1\end{array}\right]"/>

As with the majority of calculations that are done in this course the question that needs to be asked is whether the answer makes sense. Given the point (-2,4) if we simply add the transformation (3,4) we would get (1,8) using simple vector addition:

<img src="https://latex.codecogs.com/svg.latex?\large&space;\left[\begin{array}{c}-2\\4\end{array}\right]+\left[\begin{array}{c}3\\4\end{array}\right]=\left[\begin{array}{c}1\\8\end{array}\right]"/>

The use of the w-axis in this 2D example is a bit of an overkill but the power of the w-axis lies when doing 3D rotations, but before this is covered what about 3D transformations? Given a point (-2,5,3) of an object in 3D space. If the object is required to move by <img src="https://latex.codecogs.com/svg.latex?\large&space;(\Delta{x},\Delta{y},\Delta{z})=(-2, -3,5)"/> then the transformation matrix would be:

<img src="https://latex.codecogs.com/svg.latex?\large&space;\left[\begin{array}{cccc}1&0&0&-2\\0&1&0&-3\\0&0&1&5\\0&0&0&1\end{array}\right]\times{\left[\begin{array}{c}-4\\2\\8\\1\end{array}\right]}=\left[\begin{array}{c}-6\\-1\\13\\1\end{array}\right]"/>

## Scaling
### Key Concepts
The key concepts for this part of the lesson are:
* Construct a scaling matrix in 2D and 3D
* Scale a point (representing a single point of an object) in 2D and 3D space

### Lesson
Similar to transforming (shifting) an object in 2D and 3D space it is possible to scale an object, either uniformly or otherwise, in 2D and 3D space. This type of matrix takes the form of:

2D: <img src="https://latex.codecogs.com/svg.latex?\large&space;S=\left[\begin{array}{ccc}S_{x}&0&0\\0&S_{y}&0\\0&0&1\end{array}\right]"/>&nbsp;3D: <img src="https://latex.codecogs.com/svg.latex?\large&space;S=\left[\begin{array}{cccc}S_{x}&0&0&0\\0&S_{y}&0&0\\0&0&S_{z}&0\\0&0&0&1\end{array}\right]"/>

Note that this is one instance where the Row and Column major matrices are the same. To demonstrate this use the following example. Given an object in 3D space with one of its points at (4,-1,2) and this object is scaled by <img src="https://latex.codecogs.com/svg.latex?\large&space;(S_{x},S_{y},S_{z})=(3,2,4)"/>.

<img src="https://latex.codecogs.com/svg.latex?\large&space;\left[\begin{array}{cccc}3&0&0&0\\0&2&0&0\\0&0&4&0\\0&0&0&1\end{array}\right]\times{\left[\begin{array}{c}4\\-1\\2\\2\\1\end{array}\right]}=\left[\begin{array}{c}12\\-2\\8\\1\end{array}\right]"/>