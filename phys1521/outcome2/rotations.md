---
layout: page
title: Marix Rotations
---
## Introduction
Previously the work with matrices has all be linear transformations, transformations that used matrix multiplication. Linear transformations can be extended to include simple rotations. This lesson uses the 3D and 4D homogeneous coordinate systems for consistency.

### Left-hand Rule (LHR) vs. Right-hand Rule (RHR):
There are many ways in which you can create a 3D coordinate system but the two most common are the LHR and the RHR as shown in the figure below.
 
![3d-rules](../outcome1/files/3d-rules.jpg)

To visualize this, create a 3D system using your thumb (x-axis), index finger (y-axis), and middle finger (z-axis). Try rotating your left hand to match the LHR, then with your right-hand match the RHR.

## Rotations in 2D & 3D
### Key Concepts
The key concepts of this part of the lesson are:
* Rotation in pure 2D space
* Rotation about a cardinal axis (i.e., simple 3D rotations)
* Euler angles to matrix
* Matrix to Euler angles

### Lesson
To see how rotations work in 3D the 2D system must be covered as it forms the basis of the remainder of this lesson. In 2D, as was stated in the previous lesson, the 2D coordinate system uses a single reference axis, i.e., the z-axis if the coordinate system is extrapolated to the 3D world, or the w-axis to maintain consistency with the final 3D rotations. For now, it is best to “pretend” that the 2D system contains a z-axis. The inclusion of the z-axis is necessary to go from 2D to 3D and then to the 4D homogeneous system. In this 2D world the world is in 3D and the z-axis is the rotation axis.

Earlier a matrix was defined as an array of vectors. Using this in the figure below, with two vectors, P and Q, the following matrix can be constructed:

<img src="https://latex.codecogs.com/svg.latex?\large&space;\left[\begin{array}{c}P\\Q\end{array}\right]=\left[\begin{array}{cc}1&0\\0&1\end{array}\right]"/>

![rotations-2d-explained](files/rotations-2d-explained.jpg)

Rotating the two vectors about an angle θ their positions change (recall basic trigonometry) to **P’** and **Q’**. This new position can be written as the matrix below:

<img src="https://latex.codecogs.com/svg.latex?\large&space;R(\theta)=\left[\begin{array}{c}P'\\Q'\end{array}\right]=\left[\begin{array}{cc}P'_{x}&Q'_{x}\\P'_{y}&Q'_{y}\end{array}\right]=\left[\begin{array}{cc}cos(\theta)&-sin(\theta)\\sin(\theta)&cos(\theta)\end{array}\right]"/>

As this was done without including the rotation axis (which was explained as either using the z-axis or the w-axis) the resulting rotation matrix in 3D format is:

<img src="https://latex.codecogs.com/svg.latex?\large&space;R(\theta)=\left[\begin{array}{ccc}cos(\theta)&-sin(\theta)&0\\sin(\theta)&cos(\theta)&0\\0&0&1\end{array}\right]"/>

_Whether the z-axis or the w-axis is used the resulting rotation matrix does not change the value of z or w._

Example Given the vector, in homogeneous space, <img src="https://latex.codecogs.com/svg.latex?\large&space;V=\left[\begin{array}{c}3\\4\\1\end{array}\right]"/> and a rotation angle of 20<sup>o</sup> calculate the new coordiantes of the vector:

<img src="https://latex.codecogs.com/svg.latex?\large&space;R(\theta)=\left[\begin{array}{ccc}cos(20)&-sin(20)&0\\sin(20)&cos(20)&0\\0&0&1\end{array}\right]"/>

<img src="https://latex.codecogs.com/svg.latex?\large&space;V'=\left[\begin{array}{ccc}0.9397&-0.3420&0\\0.3420&0.9397&0\\0&0&1\end{array}\right]\times{\left[\begin{array}{c}3\\4\\1\end{array}\right]}\approx{\left[\begin{array}{c}1.4510\\4.7848\\1\end{array}\right]}"/>

![rotation-2d-math](files/rotation-2d-math.jpg)

Now that a simple 2D rotation matrix has been defined the next step is to expand this to a 3D system. In a 3D system, there are 3 rotation axes, x, y, and z. For now, the assumption is that the 3D form from above is a rotation about the z-axis. The next question would be what would the matrix look like if the rotation is about the x, or the y axis? First it is important to rewrite the rotation matrix:

<img src="https://latex.codecogs.com/svg.latex?\large&space;R_{z}(\theta)=\left[\begin{array}{ccc}cos(20)&-sin(20)&0\\sin(20)&cos(20)&0\\0&0&1\end{array}\right]"/>

For rotation about the x axis the matrix is:

<img src="https://latex.codecogs.com/svg.latex?\large&space;R_{x}(\theta)=\left[\begin{array}{ccc}1&0&0\\0&cos(20)&-sin(\theta)\\0&sin(\theta)&cos(\theta)\end{array}\right]"/>

Rotation about the y-axis is:

<img src="https://latex.codecogs.com/svg.latex?\large&space;R_{y}(\theta)=\left[\begin{array}{ccc}cos(\theta)&0&sin(\theta)\\0&1&0\\-sin(\theta)&0&cos(\theta)\end{array}\right]"/>

As with the other linear transformations, each of these rotation matrices need to be put in homogeneous, or 4D, form:

<img src="https://latex.codecogs.com/svg.latex?\large&space;R_{z}(\theta)=\left[\begin{array}{cccc}cos(20)&-sin(20)&0&0\\sin(20)&cos(20)&0&0\\0&0&1&0\\0&0&0&1\end{array}\right]"/>&nbsp;<img src="https://latex.codecogs.com/svg.latex?\large&space;R_{x}(\theta)=\left[\begin{array}{cccc}1&0&0&0\\0&cos(20)&-sin(\theta)&0\\0&sin(\theta)&cos(\theta)&0\\0&0&0&1\end{array}\right]"/>&nbsp;<img src="https://latex.codecogs.com/svg.latex?\large&space;R_{y}(\theta)=\left[\begin{array}{cccc}cos(\theta)&0&sin(\theta)&0\\0&1&0&0\\-sin(\theta)&0&cos(\theta)&0\\0&0&0&1\end{array}\right]"/>

In each of these new matrices the reference, or w-axis, does not change with any of the rotations, which is the desired result.

Using simple linear transformations only one rotation is done at a time. For example, take a point (2, 1, 4) and rotate it individually about the x-, y- and z-axis with a rotation angle of 90<sup>o</sup>. The first step would be to construct the individual matrices as shown below but first <img src="https://latex.codecogs.com/svg.latex?\large&space;cos(90)=0"/> and <img src="https://latex.codecogs.com/svg.latex?\large&space;sin(90)=1"/>

<img src="https://latex.codecogs.com/svg.latex?\large&space;R_{z}(\theta)=\left[\begin{array}{cccc}0&-1&0&0\\1&0&0&0\\0&0&1&0\\0&0&0&1\end{array}\right]"/>&nbsp;<img src="https://latex.codecogs.com/svg.latex?\large&space;R_{x}(\theta)=\left[\begin{array}{cccc}1&0&0&0\\0&0&-1&0\\0&1&0&0\\0&0&0&1\end{array}\right]"/>&nbsp;<img src="https://latex.codecogs.com/svg.latex?\large&space;R_{y}(\theta)=\left[\begin{array}{cccc}0&0&1&0\\0&1&0&0\\-1&0&0&0\\0&0&0&1\end{array}\right]"/>

Now perform the multiplication:

<img src="https://latex.codecogs.com/svg.latex?\large&space;R_{z}=\left[\begin{array}{cccc}cos(20)&-1&0&0\\1&0&0&0\\0&0&1&0\\0&0&0&1\end{array}\right]\times{\left[\begin{array}{c}2\\1\\4\\1\end{array}\right]}=\left[\begin{array}{c}-1\\2\\4\\1\end{array}\right]"/>

<img src="https://latex.codecogs.com/svg.latex?\large&space;R_{x}=\left[\begin{array}{cccc}1&0&0&0\\0&0&-1&0\\0&1&0&0\\0&0&0&1\end{array}\right]\times{\left[\begin{array}{c}2\\1\\4\\1\end{array}\right]}=\left[\begin{array}{c}2\\-4\\1\\1\end{array}\right]"/>

<img src="https://latex.codecogs.com/svg.latex?\large&space;R_{y}(\theta)=\left[\begin{array}{cccc}0&0&1&0\\0&1&0&0\\-1&0&0&0\\0&0&0&1\end{array}\right]\times{\left[\begin{array}{c}2\\1\\4\\1\end{array}\right]}=\left[\begin{array}{c}4\\1\\-2\\1\end{array}\right]"/>

As a side note the rotation matrices created above have some common names such as pitch (attitude), roll (bank), or yaw (heading). These terms only make sense relative to the direction of travel in a 3D coordinate space but typically in a LHR system roll is rotation about the z-axis, pitch is rotation about the x-axis. (In a RHR system, roll is about the x-axis and pitch is about the z-axis.)

Considering the multiplication rules for matrices if a rotation were to take place about more than one axis of rotation in each game loop, does the order of multiplication matter? Yes, the order matters (the instructor could take any two of the matrices and multiply them in different order and show that the resulting matrix is not the same; the problem is compounded when using all three rotation matrices). There is a standard that will be used in this class which is Roll-Pitch-Yaw (RPY). The calculation is first R<sub>x</sub> x R<sub>y</sub>, then this result is multiplied by R<sub>z</sub>, <img src="https://latex.codecogs.com/svg.latex?\large&space;R_{RPY}=R_{z}\times({R_{x}\times{R_{y}}})"/>

<img src="https://latex.codecogs.com/svg.latex?\large&space;R_{RPY}=\left[\begin{array}{ccc}cos(Y)cos(R)-sin(Y)sin(P)sin(R)&-sin(R)cos(P)&sin(Y)cos(R)+cos(Y)sin(P)sin(R)\\cos(Y)sin(R)+sin(Y)sin(P)cos(R)&cos(R)cos(P)&sin(R)sin(Y)-cos(Y)sin(P)cos(R)\\-sin(Y)cos(P)&sin(P)&cos(Y)cos(P)\end{array}\right]"/>

For example, given the vector, in homogeneous space, <img src="https://latex.codecogs.com/svg.latex?\large&space;V=\left[\begin{array}{c}3\\4\\-1\\1\end{array}\right]"/> and the rotation angles of **Roll=5<sup>o</sup>**, **Pitch=10<sup>o</sup>**, and **Yaw=10<sup>o</sup>** calculate the individual rotation matrices, the product of the vectors with each matrix, the RPY matrix and the product of the vector and this matrix:

![roll-pitch-yaw-math](files/roll-pitch-yaw-math.jpg)

The reverse of this operation, Matrix to Euler Angles, is also possible. The technique used here will restrict yaw and roll to ±180<sup>o</sup> and pitch to ±90<sup>o</sup>. An additional restraint is that there are no additional linear transforms in the matrix, such as shifting and scaling.

Examining the Euler-to-Matrix result it is easiest to start with the pitch angle (from the matrix cell M<sub>32</sub>).

<img src="https://latex.codecogs.com/svg.latex?\large&space;M_{32}=sin(P)"/> therefore <img src="https://latex.codecogs.com/svg.latex?\large&space;P=sin^{-1}(M_{32})"/>

The result of the inverse sine operation will yield results in the range of <img src="https://latex.codecogs.com/svg.latex?\large&space;\frac{-\pi}{2}"/> to <img src="https://latex.codecogs.com/svg.latex?\large&space;\frac{\pi}{2}"/> which is -90<sup>o</sup> to +90<sup>o</sup>, which is the desired range. Once P has been calculated the value <img src="https://latex.codecogs.com/svg.latex?\large&space;cos(P)"/> can also be computed, if <img src="https://latex.codecogs.com/svg.latex?\large&space;cos(P)\neq{0}"/>, using cell M<sub>31</sub>.

<img src="https://latex.codecogs.com/svg.latex?\large&space;M_{31}=-sin(Y)cos(P)"/>

<img src="https://latex.codecogs.com/svg.latex?\large&space;sin(Y)=-\frac{M_{31}}{cos(P)}"/>

<img src="https://latex.codecogs.com/svg.latex?\large&space;M_{33}=cos(Y)cos(P)"/>

<img src="https://latex.codecogs.com/svg.latex?\large&space;cos(Y)=\frac{M_{33}}{cos(P)}"/>

<img src="https://latex.codecogs.com/svg.latex?\large&space;Y=tan^{-1}\left(\frac{sin(Y)}{cos(Y)}\right)=tan^{-1}\left(\frac{\frac{-M_{31}}{cos(P)}}{\frac{M_{33}}{cos(P)}}\right)=tan^{-1}\left(\frac{-M_{31}}{M_{33}}\right)"/>

Next the calculation for the Roll angle needs to be done using cells M<sub>12</sub> and M<sub>22</sub>:

<img src="https://latex.codecogs.com/svg.latex?\large&space;M_{12}=-sin(R)cos(P)"/>

<img src="https://latex.codecogs.com/svg.latex?\large&space;sin(R)=-\frac{M_{12}}{cos(P)}"/>

<img src="https://latex.codecogs.com/svg.latex?\large&space;M_{22}=cos(R)cos(P)"/>

<img src="https://latex.codecogs.com/svg.latex?\large&space;cos(R)=\frac{M_{22}}{cos(P)}"/>

<img src="https://latex.codecogs.com/svg.latex?\large&space;R=tan^{-1}\left(\frac{sin(R)}{cos(R)}\right)=tan^{-1}\left(\frac{\frac{-M_{12}}{cos(P)}}{\frac{M_{22}}{cos(P)}}\right)=tan^{-1}\left(\frac{-M_{12}}{M_{22}}\right)"/>

In programming the correct function to use is the `ATAN2` function to give the correct angle.

For example, the matrix below, calculate the Euler angles:

<img src="https://latex.codecogs.com/svg.latex?\large&space;R_{RPY}=\left[\begin{array}{ccc}0.8826&-0.4698&0.3188\\0.5438&0.8138&-0.2049\\-0.1632&0.3420&0.9254\end{array}\right]"/>

<img src="https://latex.codecogs.com/svg.latex?\large&space;P=sin^{-1}(M_{32})=sin^{-1}(0.3420)\approx{20^{o}}"/>

<img src="https://latex.codecogs.com/svg.latex?\large&space;Y=tan^{-1}\left(\frac{-M_{31}}{M_{33}}\right)=tan^{-1}\left(\frac{0.1632}{0.9254}\right)\approx{10^{o}}"/>

<img src="https://latex.codecogs.com/svg.latex?\large&space;R=tan^{-1}=\left(\frac{-M_{12}}{M_{22}}\right)=tan^{-1}\left(\frac{0.4698}{0.8138}\right)\approx{30^{o}}"/>

![matrix-to-euler](files/matrix-to-euler.jpg)

So, what happens if cos(P) = 0? Obviously, division by zero is not possible. Yet when <img src="https://latex.codecogs.com/svg.latex?\large&space;cos(P)=0"/> then <img src="https://latex.codecogs.com/svg.latex?\large&space;P\pm{90^{o}}"/>. In this situation, the result is Gimbal Lock; the object is either pointing straight up or straight down. In this Gimbal Lock the Yaw (heading) and Roll (bank) now rotate about the same axis (the y-axis). To solve for this now arbitrarily assign all rotations about the y-axis to Yaw (heading) and set Roll (bank) to zero. Now the following values are known:

<img src="https://latex.codecogs.com/svg.latex?\large&space;cos(P)=0"/>,<img src="https://latex.codecogs.com/svg.latex?\large&space;R=0"/>, <img src="https://latex.codecogs.com/svg.latex?\large&space;sin(R)=0"/>, and <img src="https://latex.codecogs.com/svg.latex?\large&space;cos(R)=1"/>

Substitute these values into the matrix to get:

<img src="https://latex.codecogs.com/svg.latex?\large&space;R_{RPY}=\left[\begin{array}{ccc}cos(Y)&0&sin(Y)\\sin(Y)sin(P)&0&-cos(Y)sin(P)\\0&sin(P)&0\end{array}\right]"/>

<img src="https://latex.codecogs.com/svg.latex?\large&space;Y=tan^{-1}\left(\frac{M_{13}}{M_{11}}\right)"/>

## Exercises & Assignments
Have students complete the [2D & 3D Rotations worksheet](matrix-worksheet-4.md). Once complete proceed to Moodle to complete Knowledge Check 08 - 2D & 3D Rotations (strongly recommended to be completed prior to attempting Lab 2).

#### [Outcome Home](index.md)
#### [PHYS1521 Home](../)