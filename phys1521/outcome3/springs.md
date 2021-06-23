---
layout: page
title: Other Forces - Springs
---
## Introduction
This lesson will include an additional concept related to Linear Mechanics.

## Key Concepts
The key concepts for this part of the lesson are:
* Understand the basics of Spring forces

### Lesson
Spring forces are much more prevalent in game programming; any video game that closely simulates the driving of a vehicle uses springs. Naturally, springs want to stay in their current state and will contract to this state if extended and extend to this state if compressed. However, the returning to the state of rest often produces a bounce effect, or harmonic oscillation.

The formula for springs, known as Hooke’s Law, is:

<img src="https://latex.codecogs.com/svg.latex?\large&space;F_r=k(l_{rest}-l)"/> **OR** <img src="https://latex.codecogs.com/svg.latex?\large&space;F=-kx"/>

In this formula, _k_ is the spring constant, which is an indication of the stiffness of the spring. In order for the formula to balance correctly, in terms of units, _k_ cannot be a pure number; its units are N/m. The l<sub>rest</sub> variable represents the length of the spring at rest, and l represents the length, either stretched or compressed. There are some basic calculations that could be done with springs, one of which is done to calculate the k of a spring:

<img src="https://latex.codecogs.com/svg.latex?\large&space;k=\frac{F_r}{l_{rest}-l}"/>

Or the length of a spring given an applied force:

<img src="https://latex.codecogs.com/svg.latex?\large&space;l=l_{rest}-\left(\frac{F_r}{k}\right)"/>

As interesting as these could be the importance of springs is on the motion properties of an object affected by a spring.

<img src="https://latex.codecogs.com/svg.latex?\large&space;F_r=k(l_{rest}-l)"/> yields <img src="https://latex.codecogs.com/svg.latex?\large&space;A(t)=-Kx(t)"/> where <img src="https://latex.codecogs.com/svg.latex?\large&space;K=\frac{k}{m}"/>

Imagine hanging an object from the end of a spring that is attached to a surface. After the object is released, the spring begins to extend and contract in _cosine wave-type_ manner until the spring is extended to a final position (the correct way to solve this is with differential equations which are way, way beyond the scope of this course).

As the pattern closely resembles a cosine wave, we can calculate the angular frequency:

<img src="https://latex.codecogs.com/svg.latex?\large&space;\omega=\sqrt{K}=\sqrt{\frac{k}{m}}"/> where <img src="https://latex.codecogs.com/svg.latex?\large&space;\sqrt{K}"/> is the angular frequency

Therefore, as ω is measured as radians/second it is possible to measure the frequency of the oscillation:

<img src="https://latex.codecogs.com/svg.latex?\large&space;Freq=\frac{\omega}{2\pi}=\frac{\sqrt{K}}{2\pi}=\frac{1}{2\pi}\left(\sqrt{\frac{k}{m}}\right)"/>