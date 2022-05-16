---
layout: page
title: Decision Structures - If-Then-Else
---

## Introduction
This topic introduces you to some fundamental coding practices for decision structure. There are several variations:
*  If-Then
*  If-Then-Else
*  Nested If-Then-Else
*  If-Else If

## Demo Problem
To demonstrate a decision structure, you will create a console application that determines the highest and smallest number from three inputted values.

### Input Variables
You will need three numeric (integer data type) variables:
*  `number1`
*  `number2`
*  `number3`

### Output Variables
You will need two numeric (integer data type) variables:
*  `highest`
*  `smallest`

![high-small-number-0](files/high-small-number-0.jpg)

### User Input
You will need the following code to get user input for this problem:<br>
![high-small-number-1](files/high-small-number-1.jpg)

### Process Steps
The logic to solve this problem is shown below:
1.  Compare `number` to `number2`; find the highest and smallest of the first two numbers:<br>
![high-small-number-2](files/high-small-number-2.jpg)<br>
_In this step we are not concered with the value of `number3`, that will come soon._
2.  Now compare the `highest`, which was determined above, with `number3`:<br>
![high-small-number-3](files/high-small-number-3.jpg)<br>
_In this step we are not concerned with `smallest`, that will come soon._
3. Finally, you will need to find the `smallest` value by comparing the `smallest` to `number3`:<br>
![high-small-number-4](files/high-small-number-4.jpg)<br>
_Question: Will this last decision structure always work?_

### Test Plan
Even though you have coded a _solution_ to the problem does not mean the solution is always going to work. Therefore, before executing the solution you need to create a test plan to outline all possible scenarios.

| Scenario | Highest | Smallest | Y/N |
| -------- | ------- | -------- | --- |
| number1 = 1<br>number2 = 2<br>number3 = 3 | 3| 1 |  |

#### [Decisions Home](index.md)
#### [CPSC1012 Home](../)