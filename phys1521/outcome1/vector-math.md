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

The proper way to represent this is <img src="https://latex.codecogs.com/svg.latex?\large&space;||A||=5"/>


### [Outcome Home](outcome1.md)
### [PHYS1521 Home](../)