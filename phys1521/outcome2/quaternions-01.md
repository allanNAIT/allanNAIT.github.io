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

What is a Quaternion? A Quaternion, in game programming, is a mathematical representation of a rotation given by a _scalar_ component and a vector component: <img src="https://latex.codecogs.com/svg.latex?\large&space;Q=\left[\begin{array}{cc}w&V\end{array}\right]=\left[\begin{array}{cc}w&\left(\begin{array}{ccc}X&Y&Z\end{array\right)]"/> (this can be written in either row form or column form as the two forms are identical). The Quaternion is sometimes written as <img src="https://latex.codecogs.com/svg.latex?\large&space;Q=\left[\begin{array}{cccc}Q_w&Q_x&Q_y&Q_z\end{array}\right]"/>)