---
layout: page
title: Linear Motion
---
## Introduction
In this next part of the course, it can be too tempting to go too in-depth with Calculus. The calculus that is used in many references is too complex for the nature of this course. It is key that the students understand vectors as these will be used almost entirely in this section of the course.

## Basic Quantities and Units
### Key Concepts
The key concepts for this part of the lesson are:
* Understand the basic units of the SI (metric) system used in physics.

### Lesson
In this course the standard units of measure will be:
* _time_: seconds
* _distance_: meters

## Velocity
### Key Concepts
The key concepts for this part of the lesson are:
* Calculating average velocity.
* Understanding instantaneous velocity.
* Understanding what a derivative is and how it is used with velocity.

### Lesson
How to distinguish between _speed_ and **velocity**; _speed_ is a _scalar_, while **velocity** is a vector; often these two words are used interchangeably but they are not the same thing. Most people know that speed is a measure of distance over time, i.e., km/h, m/s, mph (miles per hour).

#### Average Velocity
Consider the problem of the tortoise and the hare. The tortoise moves at a steady pace throughout the race, while the hare runs very fast, rests for a time, continues running and resting until the end of the race is reached. If both the tortoise and the hare reach the finish line at the same time which one has the greater average velocity? The answer is they both have the same average velocity. How can this be so? Both travelled the same distance (displacement) over the same time. This yields the basic formula:

<img src="https://latex.codecogs.com/svg.latex?\large&space;\bar{V}=\fraction{displacement}{time}=\frac{\Delta{x}}{\Delta{t}}=\frac{x_f-x_i}{t_f-t_i}"/>

However, if a plot is made of each animal’s progress it does not appear to make sense as the hare accelerates and decelerates (acceleration will be discussed later in this lesson) and thus its _speed_ is constantly changing; in fact, at any given point on the plot the _speed_ of the hare is different than the _speed_ of the tortoise. Also, between any two points on the plot the average _speed_ of the hare could be zero. It is the overall result, as shown in the formula above that is important.

Example: Calculate the average velocity given that an object at <img src="https://latex.codecogs.com/svg.latex?\large&space;t_i=0"/>, with <img src="https://latex.codecogs.com/svg.latex?\large&space;x_i=100"/>, travels to a point <img src="https://latex.codecogs.com/svg.latex?\large&space;x_f=200"/> at an ending time of <img src="https://latex.codecogs.com/svg.latex?\large&space;t_f=10"/>:

<img src="https://latex.codecogs.com/svg.latex?\large&space;\bar{V}=\frac{200-100}{10-0}=10"/>

It is important here that normally units of measure are used. In a game the units of measure are not as important as the game play results but, in this course, get used to using units; the answer of 10 from the example above does not mean anything, but <img src="https://latex.codecogs.com/svg.latex?\large&space;10m/s"/> does; all final answers will include units of measure, but the detailed calculations do not require units of measure (mostly they just get in the way).

#### Instantaneous Velocity
In the tortoise and hare scenario above it was noted that at some points along the path the tortoise had a greater instantaneous velocity, while at other places the hare’s instantaneous velocity was greater. Simply using the formula for average velocity will not always work when the instantaneous velocity is needed.

## Acceleration
### Key Concepts
The key concepts of this part of the lesson are:
* Understand the relationship between velocity and acceleration.
* Calculate motion under constant acceleration.

### Lesson
What is the definition of acceleration. Must acceleration always be positive (negative acceleration means to slow down, i.e., braking). The dropping a ball bearing from the top of a building is a good example to show acceleration due to gravity. Starting at an initial velocity of zero and adding acceleration for each second the resulting equation is:

<img src="https://latex.codecogs.com/svg.latex?\large&space;V(t)=V_i+At"/>

When A=0 there is a constant velocity, or no change in velocity. When A > 0 a plot of the motion is like a ∪, and when A < 0 the plot looks like a ∩; these shapes are to represent parabolic curves.

The general equation of motion given an initial velocity and a constant acceleration:

<img src="https://latex.codecogs.com/svg.latex?\large&space;\Delta{D}=VIit+\frac{1}{2}At^2"/>

In the example of dropping the ball bearing from the building the velocity after each second was calculated but not how far it had travelled. This _distance_ is called **displacement** and can be calculated. For example, how far would the ball bearing travel, from rest, after 1 second?

<img src="https://latex.codecogs.com/svg.latex?\large&space;\Delta{D}=0+\frac{1}{2}(-9.81)1^2=-4.905m"/>
