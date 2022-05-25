---
layout: page
title: Looping Structures - While Loop
---

## Introduction
This topic introduces you to some fundamental coding practices for the **while** structure. The **while** coding structure is often referred to as an **event-driven loop**. This coding structure is an _repetition structure_ that allows a programmer to specify some actions are to be repeated while a condition remains true. 

The syntax for the **while** loop is:

    ```csharp
    while (loop-continutation-condition)
    {
        //loop body
    }
    ```

For eaxmple:

    ```csharp
    static void Main(string[] args)
    {
        int number = 1;

        while (number <= 5)
        {
            Console.WriteLine("Hello");
            number++;
        }
    }
    ```
## Loop Design Strategies
The key to designing a loop is to identify the code that needs to be repeated and write a condition for terminating the loop.

### Steps
1. Identify the statements to be repeated
2. Wrap these statements in a loop as follows:

    ```csharp
    while (true)
    {
        // Statements
    }
    ```
3. Code the ***loop-continuation-condition*** and add appropriate statements for controlling the loop:

    ```csharp
    while (loop-continuation-conditions)
    {
        // Statements

        // Additional statements for controlling the loop
    }
    ```

## Input Validation
**CONCEPT**: The `while` loop can be used to create input routines that repeat until acceptable data is entered.

#### [Looping Home](index.md)
#### [CPSC1012 Home](../)