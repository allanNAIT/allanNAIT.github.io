---
layout: page
title: Vector Math
---
## Introduction
Most of the work done in game programming, and thus in this course, is done using vectors. Some students may know some basics of what a vector is and how to represent it. 

## Representation of a Vector
### Key Concepts
The key concepts for this part of the lesson are:
* The mathematical representation of a vector
* The geometric representation of a vector
* Addition & subtraction of vectors
* Scaling a vector
* Magnitude and distance equations

## Lesson
### Representation
A vector is a mathematical number that has both `magnitude` and `direction` and as such there needs to be a way of representing a vector; mathematically for computations, and geometrically to support the mathematical computations.
Additionally, like basic numbers (scalar values), mathematical operations should be able to be performed on them.

As this course is for game programming the fundamental representation of a vector will be mathematical. There are two forms, as shown below, which represent the same vector:

<img src="https://latex.codecogs.com/svg.latex?\large&space;V=\left[\begin{array}{ccc}2 & 3 & -1\end{array}\right]"/>&nbsp;(Horizontal or row form, [seen on Knowledge Chechs])

<img src="https://latex.codecogs.com/svg.latex?\large&space;V=\left[\begin{array}{c}2 \\ 3 \\ -1\end{array}\right]"/>&nbsp;(Vertical or column form [used in this course])

The form used depends does not matter unless multiplying a matrix by a vector (future lesson) and as such both forms will be used interchangeably (the row form will be used on Moodle Knowledge Checks).

There is a loose relationship between a vector and point in either a 2D or 3D coordinate system. Typically, a vector is in the form:

<img src="https://latex.codecogs.com/svg.latex?\large&space;V=\left[\begin{array}{ccc}V_{x} & V_{y} & V_{z}\end{array}\right]"/>&nbsp;<b>OR</b><img src="https://latex.codecogs.com/svg.latex?\large&space;V=\left[\begin{array}{c}V_{x} \\ V_{y} \\ V_{z}\end{array}\right]"/>

As either of these forms can be used it would make sense that a vector can be represented graphically using a 2D or 3D coordinate system. It is important to note here that the location of a vector in either a 2D or 3D coordinate system is purely arbitrary; that is the same vector can be drawn graphically in different locations on a coordinate system but still be the same vector.

#### Example
<img src="https://latex.codecogs.com/svg.latex?\large&space;A=\left[\begin{array}{c}3 \\ 4\end{array}\right]=B=\left[\begin{array}{c}3 \\ 4\end{array}\right]"/>

![2d-vector-graph](files/2d-vector-graph.jpg)

It is now important to emphasize that the x and y components of a vector do not represent actual distances from the origin of a 2D coordinate system (recall that the 2D coordinate system is itself a relative representation) but a change in x and y component directions; we can place a vector anywhere on a 2D coordinate system and it would still represent the actual vector.

### Addition & Subtraction
How would you answer the following example:

Given <img src="https://latex.codecogs.com/svg.latex?\large&space;A=\left[\begin{array}{c}2 \\ -4\end{array}\right]"/>&nbsp;and <img src="https://latex.codecogs.com/svg.latex?\large&space;B=\left[\begin{array}{c}-3 \\ 5\end{array}\right]"/>&nbsp; what is A + B? <img src="https://latex.codecogs.com/svg.latex?\large&space;A+B=\left[\begin{array}{c}2 + (-3) \\ (-4) + 5\end{array}\right]=\left[\begin{array}{c}-1 \\ 1\end{array}\right]"/>


What about A - B? <img src="https://latex.codecogs.com/svg.latex?\large&space;A-B=\left[\begin{array}{c}2 - (-3) \\ (-4) - 5\end{array}\right]=\left[\begin{array}{c}5 \\ -9\end{array}\right]"/>

It is important that students understand the result is simply the addition, or subtraction, of individual vector components. Mathematically <img src="https://latex.codecogs.com/svg.latex?\large&space;A+B=B+A"/> and <img src="https://latex.codecogs.com/svg.latex?\large&space;A-B\neq{B-A}"/>.

### Scaling
In mathematics you learned that <img src="https://latex.codecogs.com/svg.latex?\large&space;2x3=6"/> (and other multiplication facts). Does the following make sense:

<img src="https://latex.codecogs.com/svg.latex?\large&space;2\times{\left[\begin{array}{c}3 \\ -1\end{array}\right]=\left[\begin{array}{c}6 \\ -2\end{array}\right]}"/>

This is mathematically identical to:
<img src="https://latex.codecogs.com/svg.latex?\large&space;\left[\begin{array}{c}3 \\ -1\end{array}\right]+\left[\begin{array}{c}3 \\ -1\end{array}\right]=\left[\begin{array}{c}6 \\ -2\end{array}\right]"/>

This can be shown graphically as well if needed to reinforce this concept. The main concept is that and vector can be multiplied by a scalar value to produce a new vector.

### Magnitude & Direction
Using the vectors from the graphical representation, calculate the magnitude of the vectors. The answer should be 5 by using the Pythagorean Theorem:

<img src="https://latex.codecogs.com/svg.latex?\large&space;magnitude=\sqrt{3^2+4^2}=5"/>

The proper way to represent this is <img src="https://latex.codecogs.com/svg.latex?\large&space;\Vert{A}\Vert=5"/>

We know that a vector has both magnitude and direction. The direction of a vector can be found using basic trigonometry:

<img src="https://latex.codecogs.com/svg.latex?\large&space;direction=tan^{-1}\left(\frac{opposite}{adjacent}\right)=tan^{-1}\left(\frac{4}{3}\right)=53.130102354155978703144387440907^{o}"/>

Calculate the direction of the following vectors:

<ol type="a">
    <li><img src="https://latex.codecogs.com/svg.latex?\large&space;A=\left[\begin{array}{c}-3 \\ -4\end{array}\right]"/><br><br></li>
    <li><img src="https://latex.codecogs.com/svg.latex?\large&space;A=\left[\begin{array}{c}3 \\ -4\end{array}\right]"/><br><br></li>
    <li><img src="https://latex.codecogs.com/svg.latex?\large&space;A=\left[\begin{array}{c}-3 \\ 4\end{array}\right]"/></li>
</ol>

_The direction for A is the same as the original vector example but the direction of the x and y values are opposite. The directions for both B and C are the same but graphically they are not. What is the problem?_

The tan<sup>-1</sup> function does not distinguish between quadrants of a 2D coordinate system. In programming there are two functions that can be used `atan` and `atan2`. Using `atan` will give you the wrong result when the vector is in an opposite quadrant, while the `atan2` function should give you the correct angle value.

With the calculations the vector can be written as:<br>
`magnitude@direction`

For the majority of this course you will not have to convert from the component form to the magnitude and direction (polar) form but be aware of the issues. Most of the work will have vectors in component form with some conversion from polar to component form.

Given a vector 20@30<sup>o</sup> convert this to component form.

<img src="https://latex.codecogs.com/svg.latex?\large&space;20@30^{o}=\left[\begin{array}{c}20cos(30) \\ 20sin(30)\end{array}\right]=\left[\begin{array}{c}17.320508075688772935274463415059 \\ 10\end{array}\right]"/>

Up to this point the number of decimal places used has not been specified (answers shown were from the computer’s calculator application and no rounding was used). Refer to [Notation Statndards](../notation-standards.md) for use of decimal places.

## Exercises & Assignments
Have students complete the [Vector Exercises Part 1 worksheet](vector-worksheet-1.md). Once complete proceed to Moodle to complete Knowledge Check 02 - Vectors Pt. 1 (Conversion) (strongly recommended to be completed prior to attempting Lab 1).

### [Outcome Home](outcome1.md)
### [PHYS1521 Home](../)