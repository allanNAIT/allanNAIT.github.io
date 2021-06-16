---
layout: page
title: Notation Standards
permalink: /notation-standards/
---
## Introduction
Throughout this course your instructor will use many conventions to denote mathematical properties and identifiers. Some of these are standard and in many published resources some of the notations used in this course differ from what is considered standard. As the intent of this course is to not make you an expert in Mathematics or Physics, the notations used simplify the understanding and, hopefully, make the programming aspect of video games easier for the programmer.

## Accuracy
In actual game programming most data types are either **Integer** or **Float** data types. The rationale for this is the game loop, for whatever game engine you are using, must process all the calculations in each time slice in order to maintain a decent frames per second (fps) for game playability. While **Integer** data types are easy to process computationally by the computer floating point, or numbers with decimal places, are not so. In most computer programming, where accuracy is desired, programmers use the **Double** (double precision **Float**) data type. In game programming the trade-off between accuracy and speed generally sides with speed thus the use of the **Float** data type.

In this course, unless otherwise directed, students will round all answers to 4 decimal places. The best practice for this is to store all the calculated answers in the calculator’s memory then round only the final answer. (The computer calculator used by your instructor does this). As with any answer (calculated value) in game programming, close is close enough. When completing the online Knowledge Checks there is a rounding factor of 0.005 which should account for most of the rounding errors in your calculations.

## Types of Numbers
There is a distinct difference between the data type of a number and its actual representation. The data type will store the value of the number, whereas the representation of the number will be something else entirely. There are two basic types of numeric representations, scalars and vectors. This introduction does not go into depth on the similarities and differences of these two representations, except how your instructor will represent each type. Scalar data will always be represented by lowercase alphabetical characters (i.e., s, m, or t), while vector data will be represented by UPPERCASE alphabetical characters (i.e., V, A, or F).

Doing any internet research, you may find different notations used for vectors such as <img src="https://latex.codecogs.com/svg.latex?\large&space;\vec{v}"/>,<img src="https://latex.codecogs.com/svg.latex?\large&space;\vec{V}"/>, or **v**. While each type of notation has its place, your instructor has chosen to make it simpler.

## Subscripts & Superscripts
Often there are not enough letters, or combination of letters, to identify a specific value in mathematics. It could be possible to use programming variable naming conventions but doing so would complicate the math equations and, in all likelihood, confuse the student. For this reason, certain subscripts and superscripts are used throughout the course.

### Subscripts
Subscripts are used to denote different values of the same type, i.e., x<sub>1</sub>, x<sub>2</sub>, F<sub>net</sub>, and F<sub>a</sub>. Another type of subscript is E<sub>o</sub> which is used to denote energy loss.

### Superscripts
Numeric superscripts are used quite often mathematically, such as in the equation a<sup>2</sup> + b<sup>2</sup> = c<sup>2</sup>. In addition to these standard superscripts certain superscript notations will be used in the course:
* <img src="https://latex.codecogs.com/svg.latex?\large&space;\hat{A}"/> = normalizes A
* <img src="https://latex.codecogs.com/svg.latex?\large&space;\bar{AB}"/> = length of line segment between A and B

## Other Notations
There are other notations used throughout this course, such as:
* <img src="https://latex.codecogs.com/svg.latex?\large&space;\Vert{A}\Vert"/> = magnitude of A
* <img src="https://latex.codecogs.com/svg.latex?\large&space;\vert{A}\vert"/> = determinant of A (where A is a matrix)

## Greek Letters
It is standard to use the Greek alphabet to identify mathematical, or physical, properties. The following will be used throughout this course:
* <img src="https://latex.codecogs.com/svg.latex?\large&space;\Delta"/> = change (i.e., <img src="https://latex.codecogs.com/svg.latex?\large&space;\Delta{x}=x_{2}-x_{1}"/>)
* The following symbols are used to denote angles:
  * <img src="https://latex.codecogs.com/svg.latex?\large&space;\theta"/> = theta
  * <img src="https://latex.codecogs.com/svg.latex?\large&space;\alpha"/> = alpha
  * <img src="https://latex.codecogs.com/svg.latex?\large&space;\beta"/> = beta
* <img src="https://latex.codecogs.com/svg.latex?\large&space;\mu"/> (pronounced mu) is used for the friction coefficient
* <img src="https://latex.codecogs.com/svg.latex?\large&space;\epsilon"/> (pronpuced epsilon) is used for the coefficient of elasticity
* <img src="https://latex.codecogs.com/svg.latex?\large&space;\tau"/> (pronounced tau) is used for torque
* <img src="https://latex.codecogs.com/svg.latex?\large&space;\omega"/> (pronounced omega) is used for angular velocity
* <img src="https://latex.codecogs.com/svg.latex?\large&space;\alpha"/> (pronouced alpha) is also used for angular acceleration
* _I_ (pronounced iota) is used for inertia
* <img src="https://latex.codecogs.com/svg.latex?\large&space;\Sigma"/> (pronounced sigma) is used for summations
* <img src="https://latex.codecogs.com/svg.latex?\large&space;\zeta"/> (pronounced zeta) is used in spring damping

## Other Symbols
You may encounter some other symbols such as:
* <img src="https://latex.codecogs.com/svg.latex?\large&space;\int"/> which is used for integration in calculus
* <img src="https://latex.codecogs.com/svg.latex?\large&space;\cong"/> which means approximately equal to
* <img src="https://latex.codecogs.com/svg.latex?\large&space;\therefore"/> which is gemnerally used for therefore

### [PHYS1521 Home](index.md)