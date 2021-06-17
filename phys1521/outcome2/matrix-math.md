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

c\left[\begin{array}{ccc}2&-2&1\\1&0&0.5\\0&-1&1\end{array}\right]"/>

Typically, like vectors, the identifier of a matrix will be a capital letter. To access individual elements of the matrix we use subscripts such as shown below:

<img src="https://latex.codecogs.com/svg.latex?\large&space;B=\left[\begin{array}{ccc}B_{11}&B_{12}&B_{13}\\B_{21}&B_{22}&B_{23}\\B_{31}&B_{32}&B_{33}\end{array}\right]"/>

Where an element such as **B<sub>12</sub>** is read as **b one two**. This notation is 1-based, and this example shows the matrix that has the same number of rows as the number of columns, thus it is a square matrix.

There is one special square matrix, called the **Identity Matrix** that always has the value of 1 on each element of its diagonal as shown in the example below:

<img src="https://latex.codecogs.com/svg.latex?\large&space;I=\left[\begin{array}{ccc}1&0&0\\0&1}&0\\0&0&1}\end{array}\right]"/>

As a matrix can have 1 to many rows, with 1 to many columns it is reasonable to create a 1x3 or a 3x1 matrix as shown below:

<img src="https://latex.codecogs.com/svg.latex?\large&space;\left[\begin{array}{ccc}2&3&-4\end{array}\right]"/>&nbsp;<b>OR</b>&nbsp;<img src="https://latex.codecogs.com/svg.latex?\large&space;\left[\begin{array}{c}2\\3\\-4\end{array}\right]"/>

Both forms look very, very similar to that of a vector; the first could be a row vector, while the second could be a column vector with each “representing” the same vector. Previously it did not matter which form of vector was used but when representing a vector as a matrix the form becomes very important.

## Matrix Math
### Key Concepts
The key concepts for this part of the lesson are:
* Matrix transposition
* Multiplying a matrix by a scalar
* Multiplying two matrices
* Multiplying a vector and a matrix

### Lesson
There are a couple of basic math concepts that will not be formally covered but should be intuitively easy and they are addition and subtraction of matrices. The math is very like that of adding and subtracting vectors. These concepts do not have to be formally covered as they are generally never used with matrices in game programming. The concepts outlined in the Key Concepts are those that pertain to game programming.

#### Transposition
Transposition is the flipping of a matrix on its diagonal. For example, a 4x3 matrix when transposed becomes a 3x4 matrix. The example below illustrates this:

<img src="https://latex.codecogs.com/svg.latex?\large&space;A=\left[\begin{array}{ccc}2&3&-2\\1&0&0.5\\4&6&0\\0&-1&1\end{array}\right]"/>&nbsp;<em>then</em>&nbsp;<img src="https://latex.codecogs.com/svg.latex?\large&space;A^T=\left[\begin{array}{cccc}2&1&4&0\\3&0&6&-1\\-2&0.5&0&1\end{array}\right]"/>

Note how a row in A becomes a column in A<sup>T</sup> and vice versa. Most matrices in game programming are square matrices, either 2x2, 3x3, or 4x4, so use the following example:

<img src="https://latex.codecogs.com/svg.latex?\large&space;A=\left[\begin{array}{ccc}1&2&3\\4&5&6\\7&8&9\end{array}\right]"/>&nbsp;<em>then</em>&nbsp;<img src="https://latex.codecogs.com/svg.latex?\large&space;A^T=\left[\begin{array}{ccc}1&4&7\\2&5&8\\3&6&9\end{array}\right]"/>

Note that the values on the diagonal do not change during transposition. It is also possible to transpose a vector. Such a transposition will change a row vector into a column vector and vice versa.

<img src="https://latex.codecogs.com/svg.latex?\large&space;V=\left[\begin{array}{ccc}x&y&z\end{array}\right]"/>&nbsp;<em>then</em>&nbsp<img src="https://latex.codecogs.com/svg.latex?\large&space;V^T=\left[\begin{array}{ccc}x\\y\\z\end{array}\right]"/>

Once again, the form of the vector used will become important later.