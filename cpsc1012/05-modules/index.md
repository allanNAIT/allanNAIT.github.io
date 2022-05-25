---
layout: page
title: Modularization
---
## Introduction
**CONCEPT**: Methods are required too be able to write, and maintain, larger programs. A method is a reusable block of code to do _something_. Methods also help with code organization and readability. Each method in a program has a unique signature:
*  Method name, and
*  Data type order of 0 or more parameters.

_Note 1: Two, or more, methods can have the same name and still be unique if their individual data type paramter lists are different; this is called **overloading**._

_Note 2: For each parameter present in a method's signature, it is the data type that matters, **not** the parameter name assigned to the data type._

> A parameter is a means of passing a value into a method call. The method is given the data to work on.

## Types of Methods
There are basically 4 types of methods:
*  Does not return a value and has 0 paramters (a `void` method)
*  Does not return a value and has 1 or more parameters (a `void` method)
*  Returns a value and has 0 paramters
*  Returns a value and has 1 or more parameters

## Arguments and Parameters
> When you read about C# you will find the words parameter and argument used interchangeably. This is actually not quite right. Understanding the difference will make C# documentation and error messages seem more sensible and might even give you a feeling of superiority over lessor programmers who don’t know the truth.<br><b>
A parameter is the special kind of variable that is defined in the method header and used inside that method to represent the value that was fed into the method call.

> An **argument** is the value that is supplied to the method when it is called.

Given the method below, `int` is the **parameter** supplied to the method

```csharp
static int IncrementByOne(int number)
{
    number++;
    return number;
}
```

To call this method, you need to supply an **argument** such as:

```csharp
number = IncrementByOne(number);
```

Here, the `number` in parenthesis is the **argument**.



## Coding Topics
TBD...

#### [CPSC1012 Home](../)