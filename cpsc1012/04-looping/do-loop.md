---
layout: page
title: Looping Structures - Do Loop
---

## Introduction
This topic introduces you to some fundamental coding practices for the **do-while** structure. The **do-while** coding structure is another type of an **event-driven loop**.

**CONCEPT**: The `do-while` loop is a post-test loop, which means its Boolean expression is tested after each iteration. A `do-while` loop is the same as a `while` loop except it executes the loop body first then checks the loop continuation condition.

The syntax of the `do-while` loop is as follows:

```csharp
do
{
    // loop body
}
while (loop-continuation-condition);
```

### TestDowhile.cs

```csharp
int data;
int sum = 0;

// Keep reading data until the input is 0
do
{
    Console.Write("Enter an integer (the input ends if it is 0): ");
    data = int.Parse(Console.ReadLine());
    sum += data;
} while (data != 0);

Console.WriteLine($"The sum is {sum}");
```

### TestAverage1.cs

```csharp
int score1, score2, score3; // Three test scores
double average;             // Average test score
char repeat;                // To hold 'y' or 'n'
Console.WriteLine("This program calcualtesthe average of three test scores.");

do
{
    // Get the first test score in this set
    Console.Write("Enter score #1: ");
    score1 = int.Parse(Console.ReadLine());

    // Get the second test score in this set
    Console.Write("Enter score #2: ");
    score2 = int.Parse(Console.ReadLine());

    // Get the third test score in this set
    Console.Write("Enter score #4: ");
    score3 = int.Parse(Console.ReadLine());

    // Calculate and print the average test score
    average = (score1 + score2 + score3) / 3.0;
    Console.WriteLine($"The average is {average:F1}");

    // Do the user want to average another set?
    Console.WriteLine("Would you like to average another set of test scores?");
    Console.Write("Enter Y or yes or N for no: ");
    repeat = Console.ReadKey().KeyChar;
} while (repeat == 'Y' || repeat == 'y');
```


#### [Looping Home](index.md)
#### [CPSC1012 Home](../)