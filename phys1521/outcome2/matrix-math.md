---
layout: page
title: Matrix Math
---
## Introduction
Along with Vectors, Matrices form the foundation of the math used by game engines. In Algebra matrices are taught so that students can solve a system of linear equations. In game programming matrices are used for transformation of objects (shifting, scaling, shearing, and rotation) in 2D and 3D coordinate spaces. Before the transformation topics can be covered an understanding, or review, of matrices is required.

## Definition and Notation
### Key Concepts
The key concepts for this part of the lesson are:
* Matrix definition
* Matrix dimensions
* Row vs. Column matrices
* Vectors as matrices

### Lesson
What is a matrix is and what it is used for? A matrix is defined as a mathematical entity with rows and columns that represent a set of data. With this definition, a matrix could be defined as something like 4x3 which is read to be 4 rows with each row having 3 columns. An example of such a matrix is shown below (note the use of square brackets, which is like that used with vectors):

<img src="https://latex.codecogs.com/svg.latex?\large&space;A=\left[\begin{array}{ccc}2\\3\\-2&1\\0\\0.5&4\\6\\0&0\\-1\\1\end{array}\right]"/>

Typically, like vectors, the identifier of a matrix will be a capital letter. To access individual elements of the matrix we use subscripts such as shown below:

<img src="https://latex.codecogs.com/svg.latex?\large&space;B=\left[\begin{array}{ccc}B_{11}\\B_{12}\\B_{13}&B_{21}\\B_{22}\\B_{23}&B_{31}\\B_{32}\\B_{33}\end{array}\right]"/>