---
layout: page
title: Quaternions and Rotations
---

## Introduction
Although not covered in the notes on Moodle, this topic may be of interest for those who want to know more about Quaternions. This is an oversimplified explanation of Quaternions and rotations. From Addendum 3, you learned a little about the 4D hypersphere. In this addendum, this knowledge will be further explained in terms of roations with Quaternions.

## Rotations using Quaternions
There are a number of special quaternions:
* <img src="https://latex.codecogs.com/svg.image?(1,0,0,0)" title="(1,0,0,0)" /> = identity
* <img src="https://latex.codecogs.com/svg.image?(0,1,0,0)" title="(0,1,0,0)" /> = pitch by 180<sup>o</sup> (<img src="https://latex.codecogs.com/svg.image?\pi" title="\pi" />)
* <img src="https://latex.codecogs.com/svg.image?(0,0,1,0)" title="(0,0,1,0)" /> = yaw by <img src="https://latex.codecogs.com/svg.image?\pi" title="\pi" />
* <img src="https://latex.codecogs.com/svg.image?(0,0,0,1)" title="(0,0,0,1)" /> = roll by <img src="https://latex.codecogs.com/svg.image?\pi" title="\pi" />

Changing the rotaion from <img src="https://latex.codecogs.com/svg.image?\pi" title="\pi" /> to <img src="https://latex.codecogs.com/svg.image?\frac{\pi}{2}" title="\frac{\pi}{2}" />, the following quaternions are:
* <img src="https://latex.codecogs.com/svg.image?\left&space;(&space;\frac{1}{\sqrt{2}},&space;\frac{1}{\sqrt{2}},0,0\right&space;)" title="\left ( \frac{1}{\sqrt{2}},\frac{1}{\sqrt{2}},0,0\right )" /> = pitch by 90<sup>o</sup>
* <img src="https://latex.codecogs.com/svg.image?\left&space;(&space;\frac{1}{\sqrt{2}},0,\frac{1}{\sqrt{2}},0\right&space;)" title="\left ( \frac{1}{\sqrt{2}},0,\frac{1}{\sqrt{2}},0\right )" /> = yaw by <img src="https://latex.codecogs.com/svg.image?\frac{\pi}{2}" title="\frac{\pi}{2}" />
* <img src="https://latex.codecogs.com/svg.image?\left&space;(&space;\frac{1}{\sqrt{2}},0,0,\frac{1}{\sqrt{2}}\right&space;)" title="\left ( \frac{1}{\sqrt{2}},0,0,\frac{1}{\sqrt{2}}\right )" /> = roll by <img src="https://latex.codecogs.com/svg.image?\frac{\pi}{2}" title="\frac{\pi}{2}" />

## Equivalents &amp; Inverses of Quaternions
* <img src="https://latex.codecogs.com/svg.image?(a,b,c,d&space;)=(-a,-b,-c,-d)" title="(a,b,c,d )=(-a,-b,-c,-d)" />
* <img src="https://latex.codecogs.com/svg.image?(a,-b,-c,-d)=(-a,b,c,d)" title="(a,-b,-c,-d)=(-a,b,c,d)" />
* <img src="https://latex.codecogs.com/svg.image?(-a,-b,-c,-d)=(-a,b,c,d)^{-1}" title="(-a,-b,-c,-d)=(-a,b,c,d)^{-1}" />

## Exercises & Assignments
There are no exercises or assignments associated with this Addendum.

##### [Outcome Home](index.md)
### [PHYS1521 Home](../)