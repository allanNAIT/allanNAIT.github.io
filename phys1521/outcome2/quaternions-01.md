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

<img src="https://latex.codecogs.com/svg.latex?\large&space;=\left[\begin{array}{c}Q_{1w}Q_{2w}-Q_{1x}Q_{2x}-Q_{1y}Q_{2y}-Q_{1z}Q_{2z}\\\left(\begin{array}{c}Q_{1w}Q_{2x}+Q_{1x}Q_{2w}+Q_{1y}Q_{2z}-Q_{1z}Q_{2y}\\Q_{1w}Q_{2y}+Q_{1y}Q_{2w}+Q_{1z}Q_{2x}-Q_{1x}Q_{2z}\\Q_{1w}Q_{2z}+Q_{1z}Q_{2w}+Q_{1x}Q_{2y}-Q_{1y}Q_{2x}\end{array}\right)\end{array}\right]"/>

Given this definition the multiplication of the three axis rotation quaternions is done as follows:

<img src="https://latex.codecogs.com/svg.latex?\large&space;Q=\left(\left[\begin{array}{c}cos(\frac{Y}{2})\\\left(\begin{array}{c}0\\sin(\frac{Y}{2})\\0\end{array}\right)\end{array}\right]\left[\begin{array}{c}cos(\frac{P}{2})\\\left(\begin{array}{c}sin(\frac{P}{2})\\0\\0\end{array}\right)\end{array}\right]\right)\left[\begin{array}{c}cos(\frac{R}{2})\\\left(\begin{array}{c}0\\0\\sin(\frac{R}{2})\end{array}\right)\end{array}\right]"/>

<img src="https://latex.codecogs.com/svg.latex?\large&space;Q=\left[\begin{array}{c}cos(\frac{Y}{2})cos(\frac{P}{2})\\\left(\begin{array}{c}cos(\frac{Y}{2})sin(\frac{P}{2})\\sin(\frac{Y}{2})cos(\frac{P}{2})\\-sin(\frac{Y}{2})sin(\frac{P}{2})\end{array}\right)\end{array}\right]\left[\begin{array}{c}cos(\frac{R}{2})\\\left(\begin{array}{c}0\\0\\sin(\frac{R}{2})\end{array}\right)\end{array}\right]"/>

<img src="https://latex.codecogs.com/svg.latex?\large&space;Q=\left[\begin{array}{c}cos(\frac{Y}{2})cos(\frac{P}{2})cos(\frac{R}{2})+sin(\frac{Y}{2})sin(\frac{P}{2})sin(\frac{R}{2})\\\left(\begin{array}{c}cos(\frac{Y}{2})sin(\frac{P}{2})cos(\frac{R}{2})+sin(\frac{Y}{2})cos(\frac{P}{2})sin(\frac{R}{2})\\sin(\frac{Y}{2})cos(\frac{P}{2})cos(\frac{R}{2})-cos(\frac{Y}{2})sin(\frac{P}{2})sin(\frac{R}{2})\\cos(\frac{Y}{2})cos(\frac{P}{2})sin(\frac{R}{2})-sin(\frac{Y}{2})sin(\frac{P}{2})cos(\frac{R}{2})\end{array}\right)\end{array}\right]"/>

For example, if the Euler angles are Roll=30<sup>o</sup>, Pitch=20<sup>o</sup> and Yaw=10<sup>o</sup> then the following Quaternion is created, First start by getting the individual sine and cosine values of the respective half angles:

Roll: <img src="https://latex.codecogs.com/svg.latex?\large&space;sin(\frac{30}{2})\approx{0.2588}"/> <img src="https://latex.codecogs.com/svg.latex?\large&space;cos(\frac{30}{2})\approx{0.9659}"/>

Pitch: <img src="https://latex.codecogs.com/svg.latex?\large&space;sin(\frac{20}{2})\approx{0.1736}"/> <img src="https://latex.codecogs.com/svg.latex?\large&space;cos(\frac{20}{2})\approx{0.9848}"/>

Yaw: <img src="https://latex.codecogs.com/svg.latex?\large&space;sin(\frac{10}{2})\approx{0.0872}"/> <img src="https://latex.codecogs.com/svg.latex?\large&space;cos(\frac{10}{2})\approx{0.9962}"/>

Next substitute into the Quaternion multiplication expression:

<img src="https://latex.codecogs.com/svg.latex?\large&space;Q=\left[\begin{array}{c}(0.9962)(0.9848)(0.9659)+(0.0872)(0.1736)(0.2588)\\\left(\begin{array}{c}(0.9962)(0.1736)(0.9659)+(0.0872)(0.9848)(0.2588)\\(0.0872)(0.9848)(0.9659)-(0.9962)(0.1736)(0.2588)\\(0.9962)(0.9848)(0.2588)-(0.0872)(0.1736)(0.9659)\end{array}\right)\end{array}\right]\approx{\left[\begin{array}{c}0.9515\\\left(\begin{array}{c}0.1893\\0.0382\\0.2393\end{array}\right)\end{array}\right]"/>

![quaternion-math](files/quaternion-math.jpg)

Just to make certain that this is a unit Quaternion, with a magnitude of 1 (accurate with rounding errors):

<img src="https://latex.codecogs.com/svg.latex?\large&space;\Vert{Q}\Vert=\sqrt{0.95154852^2+0.18930786^2+0.03813458^2+0.23929834^2}=1"/>

There are other possible multiplication orders of the Quaternions, which produce different results. However, some of them are equivalent due to the multiplicative property of Quaternions. The first result is equivalent to:

<img src="https://latex.codecogs.com/svg.latex?\large&space;Q=\left[\begin{array}{c}cos(\frac{Y}{2})\\\left(\begin{array}{c}0\\sin(\frac{Y}{2})\\0\end{array}\right)\end{array}\right]\left(\left[\begin{array}{c}cos(\frac{P}{2})\\\left(\begin{array}{c}sin(\frac{P}{2})\\0\\0\end{array}\right)\end{array}\right]\left[\begin{array}{c}cos(\frac{R}{2})\\\left(\begin{array}{c}0\\0\\sin(\frac{R}{2})\end{array}\right)\end{array}\right]\right)"/>

#### Create a Matrix from a Quaternion
It was shown in a previous lesson how to convert Euler angles to a rotation matrix. It should then be possible to convert a Quaternion to a rotation matrix. The final equation is what is important:

<img src="https://latex.codecogs.com/svg.latex?\large&space;R_{Q}=\left[\begin{array}{ccc}1-2(Q_{y}^2+Q_{z}^2)&2(Q_{x}Q_{y}-Q_{w}Q_{z})&2(Q_{x}Q_{z}+Q_{w}Q_{y})\\2(Q_{x}Q_{y}+Q_{w}Q_{z})&1-2(Q_{x}^2+Q_{z}^2)&2(Q_{y}Q_{z}-Q_{w}Q_{x})\\2(Q_{x}Q_{z}-Q_{w}Q_{y})&2(Q_{y}Q_{z}+Q_{w}Q_{x})&1-2(Q_{x}^2+Q_{y}^2)\end{array}\right]"/>

For example, use the following Quaternion and create a matrix:

<img src="https://latex.codecogs.com/svg.latex?\large&space;Q=\left[\begin{array}{c}0.95154852\\\left(\begin{array}{c}0.18930786\\0.03813458\\0.23929834\end{array}\right)\end{array}\right]"/>

First verify that this is a unit Quaternion:

<img src="https://latex.codecogs.com/svg.latex?\large&space;\Vert{Q}\Vert=\sqrt{0.95154852^2+0.18930786^2+0.03813458^2+0.23929834^2}=1"/>

Next calculate the individual matrix elements:

<img src="https://latex.codecogs.com/svg.latex?\large&space;M_{11}=1-2(0.03813458^2+0.23929834^2)\approx{0.8826}"/>

<img src="https://latex.codecogs.com/svg.latex?\large&space;M_{12}=2((0.18930786)(0.03813458)-(0.95154852)(0.2392834))\approx{-0.4410}"/>

<img src="https://latex.codecogs.com/svg.latex?\large&space;M_{13}=2((0.18930786)(0.2392834)+(0.95154852)(0.03813458))\approx{0.1632}"/>

<img src="https://latex.codecogs.com/svg.latex?\large&space;M_{21}=2((0.18930786)(0.03813458)+(0.95154852)(0.23929834))\approx{0.4698}"/>

<img src="https://latex.codecogs.com/svg.latex?\large&space;M_{22}=1-2(0.18930786^2+0.23929834^2)\approx{0.8138}"/>

<img src="https://latex.codecogs.com/svg.latex?\large&space;M_{23}=2((0.03813458)(0.23929834)-(0.95154852)(0.18930786))\approx{-0.3420}"/>

<img src="https://latex.codecogs.com/svg.latex?\large&space;M_{31}=2((0.18930786)(0.23929834)-(0.95154852)(0.03813458))\approx{0.0180}"/>

<img src="https://latex.codecogs.com/svg.latex?\large&space;M_{32}=2((0.03813458)(0.23929834)+(0.95154852)(0.18930786))\approx{0.3785}"/>

<img src="https://latex.codecogs.com/svg.latex?\large&space;M_{33}=1-2(0.18930786^2+0.03813458^2)\approx{0.9254}"/>

<img src="https://latex.codecogs.com/svg.latex?\large&space;R_Q=\left[\begin{array}{ccc}0.8826&-0.4408&0.1630\\0.4698&0.8138&-0.3420\\0.0180&0.3785&0.9254\end{array}\right]"/>

![quaternion-to-matrix-math](files/quaternion-to-matrix-math.jpg)

#### Create Euler Angles from a Quaternion
Now that conversion of Euler angles to a Quaternion is done there should be a way to take a given Quaternion and calculate the initial Euler angles. This is only necessary for output to the game user; once the rotations are in Quaternion form it is best to stay in that form.

In a previous lesson, it was possible to extract Euler angles from a full rotation matrix thus this technique will be adapted here. Note that the Gimbal Lock condition is not being addressed here.

<img src="https://latex.codecogs.com/svg.latex?\large&space;P=sin^{-1}(-M_{23})"/> <img src="https://latex.codecogs.com/svg.latex?\large&space;Y=tan^{-1}\left(\frac{M_{13}}{M_{33}}\right)"/> <img src="https://latex.codecogs.com/svg.latex?\large&space;R=tan^{-1}\left(\frac{M_{21}}{M_22}\right)"/>

Where the following has been previously calculated:

| Previously in this lesson |
|---------------------------|
| <img src="https://latex.codecogs.com/svg.latex?\large&space;M_{23}=2(Q_{y}Q_{z}-Q_{w}Q_{x})"/> |
| <img src="https://latex.codecogs.com/svg.latex?\large&space;M_{22}=1-2(Q_{x}^2+Q_{z}^2)"/> |
| <img src="https://latex.codecogs.com/svg.latex?\large&space;M_{13}=2(Q_{x}Q_{z}+Q_{w}Q_{y})"/> |
| <img src="https://latex.codecogs.com/svg.latex?\large&space;M_{21}=2(Q_{x}Q_{y}+Q_{w}Q_{z})"/> |
| <img src="https://latex.codecogs.com/svg.latex?\large&space;M_{33}=1-2(Q_{x}^2+Q_{y}^2)"/> |

Now with substitution:

<img src="https://latex.codecogs.com/svg.latex?\large&space;P=sin^{-1}(2(Q_{y}Q_{z}-Q_{w}Q_{x}))"/> <img src="https://latex.codecogs.com/svg.latex?\large&space;Y=tan^{-1}\left(\frac{-2(Q_{x}Q_{z}+Q_{w}Q_{y})}{1-2(Q_{x}^2+Q_{y}^2}\right)"/> <img src="https://latex.codecogs.com/svg.latex?\large&space;R=tan^{-1}\left(\frac{2(Q_{x}Q_{y}+Q_{w}Q_{z}}{1-2(Q_{x}^2+Q_{z}^2)}\right)"/>


