---
layout: page
title: Multiplication of Two Quaternions
---

## Introduction
Although not covered in the notes on Moodle, this topic may be of interest for those who want to know more about Quaternions. What is important in this topic is that <img src="https://latex.codecogs.com/svg.latex?\large&space;Q_{1}\times{Q_{2}}\neq{Q_{2}\times{Q_{1}}}"/>. This is from the fundamental principle that rotations are not communative.

## Multiplying Two Quaternions
Given <img src="https://latex.codecogs.com/svg.latex?\large&space;Q_{1}=(w_{1},V_{1})"/>, where <img src="https://latex.codecogs.com/svg.latex?\large&space;V_{1}=(x_{1},y_{1},z_{1})"/> and <img src="https://latex.codecogs.com/svg.latex?\large&space;Q_{2}=(w_{2},V_{2})"/> where <img src="https://latex.codecogs.com/svg.latex?\large&space;V_{2}=(x_{2},y_{2},z_{2})"/>, the multiplication of Quaternions follows:<br>
<img src="https://latex.codecogs.com/svg.latex?\large&space;Q_{1}\times{Q_{2}}=(w_{1}w_{2}-V_{1}\cdot{V_{2}},w_{1}V_{2}+w_{2}V_{1}+V_{1}\times{V_{2}})"/>.

Reversing the order of multiplication gives us:<br>
<img src="https://latex.codecogs.com/svg.latex?\large&space;Q_{2}\times{Q_{1}}=(w_{2}w_{1}-V_{2}\cdot{V_{1}},w_{2}V_{1}+w_{1}V_{2}+V_{2}\times{V_{1}})"/>.

The non-communative part of these two equations is<img src="https://latex.codecogs.com/svg.latex?\large&space;V_{1}\times{V_{2}}\neq{V_{2}\times{V_{1}}}"/> (they are in opposite directions refer to the [Vector Cross Product](../outcome1/cross-product.md)).

## Sample Calculations
Here are the results of a sample calculation of multiplying two Quaternions:<br>
![quat_times_quat](files/quat_times_quat.jpg)

Notice the opposite direction of the **z-component** of the results of the Cross Product.
## Exercises & Assignments
There are no exercises or assignments associated with this Addendum.

##### [Outcome Home](index.md)
### [PHYS1521 Home](../)