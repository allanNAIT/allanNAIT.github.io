---
layout: page
title: Other Forces - Gravity
---
## Introduction
This lesson will include an additional concept related to Linear Mechanics.

## Gravity
### Key Concepts
The key concepts for this part of the lesson are:
* Understand the basics of gravitational force

### Lesson
Everyday people generally take gravity for granted; they know it is there but since it generally does not affect them, they ignore it. In video games gravity can be ignored, set to 0, or altered so that the game play is enhanced. Previously the value of weight was calculated using Earth’s standard gravity, at sea level and at the equator (the value of -9.81m/s<sup>2</sup> will be used throughout this course unless otherwise specified). There is a **Law of Universal Gravitation** that is expressed as:

<img src="https://latex.codecogs.com/svg.latex?\large&space;F=G\frac{m_1m_2}{d^2}"/> where <img src="https://latex.codecogs.com/svg.latex?\large&space;G=6.673\times{10^{-11}}Nm^2kg^{-2}"/>

This has very little to do with game programming unless a developer is creating a space-based game. In that case the interaction between bodies near a planet will come under this formula. The one interesting use of this equation is to calculate gravity. A simpler method is to use Newton’s 2<sup>nd</sup> Law, <img src="https://latex.codecogs.com/svg.latex?\large&space;F=mA"/> and rewrite the Universal Gravitational equation to get:

<img src="https://latex.codecogs.com/svg.latex?\large&space;F=mA=m_2\left(G\frac{m_1}{r^2}\right)"/>

Note that in the original equation d represented the distance between the centers of the two bodies so now only the radius, r, is used. As a result, gravity is to be calculated as <img src="https://latex.codecogs.com/svg.latex?\large&space;A=\left(G\frac{m_1}{r^2}\right)"/>

## Exercises & Assignments
Complete the [Gravitational Forces worksheet](gravity-worksheet.md). Once completed, and the [Springs Worksheet](springs-worksheet.md) is completed, proceed to Moodle to complete Knowledge Checks 13 (strongly recommended to be completed prior to attempting Lab 3).

### [Outcome Home](index.md)
### [PHYS1521 Home](../)