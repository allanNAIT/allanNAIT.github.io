---
layout: page
title: Quaternions Pt. 1
---
## Introduction
Previously the rotations in 3D used Euler angles. Although this approach works there are other methods of storing rotation information. One such technique is using a Quaternion; another is using Rotors which are not covered in this course.

## Quaternions
### Key Concepts
The key concepts of this part of the lesson are:
* Define what a Quaternion is and the pros and cons vs. Euler Angles
* Create a Quaternion from Euler Angles
* Create a Matrix from a Quaternion
* Create Euler Angles from a Quaternion
* Create a Quaternion from a Matrix

#### Quaternion Definition
From the reading assignment ask students what they know of a Quaternion? Why would these be used in 3D game programming? What is “wrong” with Euler angles?

There is a lot of complex math involved with creating and using a Quaternion, which is why almost every game engine hides this math in built-in functions. The focus of this lesson (and this course) is to show students the basics behind Quaternions and how they can be used.

What is a Quaternion? A Quaternion, in game programming, is a mathematical representation of a rotation given by a _scalar_ component and a vector component: <img src="https://latex.codecogs.com/svg.latex?\large&space;Q=\left[\begin{array}{cc}w&V\end{array}\right]=\left[\begin{array}{cc}w&\left(\begin{array}{ccc}X&Y&Z\end{array}\right)\end{array}\right]"/> (this can be written in either row form or column form as the two forms are identical). The Quaternion is sometimes written as <img src="https://latex.codecogs.com/svg.latex?\large&space;Q=\left[\begin{array}{cccc}Q_w&Q_x&Q_y&Q_z\end{array}\right]"/> although this is not technically correct, but it does allow the reader to distinguish each of the components and treat a Quaternion as a 4D vector (helpful for a Dot Product; which is computed the same way as with a 3D vector only extended by one component). One interesting fact of a Quaternion is its magnitude is **always 1**.

The components used for a Quaternion is very close to those used in rotating about an arbitrary axis in 3D, but they are not the same. The _scalar_ component of a Quaternion, **w**, is used to represent the amount of rotation, while the vector component, **V**, is used to represent the axis of the rotation.

There are two general representations for Quaternions: x-axis heading, and z-axis heading. A Google search will yield results that show x-axis heading (i.e., [www.euclideanspace.com](http://www.euclideanspace.com/){:target="_blank"}). The differences are shown in the table below:

Rotation | x-axis heading | z-axis heading
---------|----------------|---------------
Roll or Bank | x-axis | z-axis
Pitch or Attitude | z-axis | x-axis
Yaw or Heading | y-axis | y-axis

There is no left hand or right-hand rule with Quaternions, only which axis is used as the forward, or heading, axis. _This course will use only z-axis calculations in calculator screenshots, and Knowledge Checks._

#### Create a Quaternion from Euler Angles
To begin with the rotation angle is halved (do not have to wonder why, it is the nature of how a Quaternion is constructed; complex numbers and such). Next represent each of the three axis rotations as quaternions:

<img src="https://latex.codecogs.com/svg.latex?\large&space;Y=\left[\begin{array}{c}cos(\frac{Y}{2})\\\left(\begin{array}{c}0\\sin(\frac{Y}{2})\\0\end{array}\right)\end{array}\right]"/> <img src="https://latex.codecogs.com/svg.latex?\large&space;P=\left[\begin{array}{c}cos(\frac{P}{2})\\\left(\begin{array}{c}sin(\frac{P}{2})\\0\\0\end{array}\right)\end{array}\right]"/> <img src="https://latex.codecogs.com/svg.latex?\large&space;R=\left[\begin{array}{c}cos(\frac{R}{2})\\\left(\begin{array}{c}0\\0\\sin(\frac{R}{2})\end{array}\right)\end{array}\right]"/>

Next step is to concatenate these three forms in the correct order, Roll, Pitch, Yaw (like the Euler Angle concatenation in the previous lesson). The multiplications are done right to left as follows:

<img src="https://latex.codecogs.com/svg.latex?\large&space;Q_1Q_2=\left[\begin{array}{cc}Q_{1w}&\left(\begin{array}{ccc}Q_{1x}&Q_{1y}&Q_{1z}\end{array}\right)\end{array}\right]\left[\begin{array}{cc}Q_{2w}&\left(\begin{array}{ccc}Q_{2x}&Q_{2y}&Q_{2z}\end{array}\right)\end{array}\right]"/>

<img src="https://latex.codecogs.com/svg.latex?\large&space;=\left[\begin{array}{c}Q_{1w}Q_{2w}-Q_{1x}Q_{2x}-Q_{1y}Q_{2y}-Q_{1z}Q_{2z}\\\left(\begin{array}{c}0\\sin(\frac{Y}{2})\\0\end{array}\right)\end{array}\right]"/>
