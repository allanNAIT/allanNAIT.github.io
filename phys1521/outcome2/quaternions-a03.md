---
layout: page
title: Quaternions and the Cubic Formula
---

## Introduction
Although not covered in the notes on Moodle, this topic may be of interest for those who want to know more about Quaternions. This short addendum introduces you to some higher level, complex, math relating to quaternions.

## Cubic Formula
In algebra you are aware of the **Quadratic Formula** <img src="https://latex.codecogs.com/svg.image?a^2&plus;b^2&plus;c^2=0" title="a^2+b^2+c^2=0" /> and the solution equation<br>
<img src="https://latex.codecogs.com/svg.image?x=\frac{-b\pm{\sqrt{b^2-4ac}}}{2a}" title="x=\frac{-b\pm{\sqrt{b^2-4ac}}}{2a}" />

What is not taught is the solution to the **Cubic Formula** <img src="https://latex.codecogs.com/svg.image?ax^3&plus;bx^2&plus;cx&plus;d=0" title="ax^3+bx^2+cx+d=0" />. This formula is quite difficult to solve. One way to solve it was to use the simplified version of <img src="https://latex.codecogs.com/svg.image?x^2&plus;px&plus;q=0" title="x^2+px+q=0" />. This has the following solution:<br>
<img src="https://latex.codecogs.com/svg.image?x=\xi\sqrt{\frac{-q}{2}&plus;\sqrt{\frac{q^2}{4}&plus;\frac{p^3}{27}}}&plus;\xi^2\sqrt{\frac{-q}{2}-\sqrt{\frac{q^2}{4}&plus;\frac{p^3}{27}}}" title="x=\xi\sqrt{\frac{-q}{2}+\sqrt{\frac{q^2}{4}+\frac{p^3}{27}}}+\xi^2\sqrt{\frac{-q}{2}-\sqrt{\frac{q^2}{4}+\frac{p^3}{27}}}" />

Where <img src="https://latex.codecogs.com/svg.image?\xi=1,\frac{-1&plus;\sqrt{-3}}{2},\frac{-1-\sqrt{-3}}{2}" title="\xi=1,\frac{-1+\sqrt{-3}}{2},\frac{-1-\sqrt{-3}}{2}" />.

Because complex numbers exist in a plane, multiplication of complex numbers yields a rotation in a 4D hypersphere. A 4D hypersphere has a 3D surface.

## Example
Given a point <img src="https://latex.codecogs.com/svg.image?(x,y,z)" title="(x,y,z)" /> around an axis of a unit vector <img src="https://latex.codecogs.com/svg.image?[U_x,U_y,U_z]" title="[U_x,U_y,U_z]" /> and an angle <img src="https://latex.codecogs.com/svg.image?\theta" title="\theta" /> results in <img src="https://latex.codecogs.com/svg.image?(x',y',z')" title="(x',y',z')" />.

This expands to:<br>
<img src="https://latex.codecogs.com/svg.image?x'i&plus;y'j&plus;z'k=q(xi&plus;yj&plus;zk)q^{-1}" title="x'i+y'j+z'k=q(xi+yj+zk)q^{-1}" />.

Where <img src="https://latex.codecogs.com/svg.image?q=cos\left&space;(&space;\frac{\theta}{2}&space;\right&space;)&plus;sin\left&space;(&space;\frac{\theta}{2}&space;\right&space;)(U_xi&plus;U_yj&plus;U_zk)" title="q=cos\left ( \frac{\theta}{2} \right )+sin\left ( \frac{\theta}{2} \right )(U_xi+U_yj+U_zk)" />.

_Note: this last equation looks similar to the Quaternion equation used in this course._

## Exercises & Assignments
There are no exercises or assignments associated with this Addendum.

##### [Outcome Home](index.md)
### [PHYS1521 Home](../)