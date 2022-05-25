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

For example:

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

## Increment & Decrement Operators
**CONCEPT**: `++` and `–-` are operators that add and subtract one from their operands. To increment a value means to increase it by one.

The following statements increment the variable `number`:

```csharp
number = number + 1;
number += 1;
number++;
```

To decrement a value means to decrease it by one. The following statements decrement the variable `number`:

```chsarp
number = number -1;
number -= 1;
number--;
```

### Prefix vs. Pstfix Modes
When the increment and decrement operator are used in statements that do more than just increment or decrement. For example:

```csharp
number = 4;
Console.WriteLine(number++); // 4
```

When the increment and decrement operator are used in statements that do more than just increment or decrement. For example:

```csharp
number = 4;
Console.WriteLine(++number); // 5
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