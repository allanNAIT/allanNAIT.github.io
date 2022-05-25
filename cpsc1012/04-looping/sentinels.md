---
layout: page
title: Looping Structures - Totals & Sentinel Values
---

## Introduction
**CONCEPT**: A running total is a sum of numbers that accumulates with each iteration of a loop. The variable used to keep the running total is called an accumulator. A sentinel is a value that signals when the end of a list of values has been reached.

### TotalSales.cs

```csharp
int days;          // The number of days
double sales;      // A day's sales figure
double totalSales; // Accumulator

// Get the number of days.
Console.Write("For how many days do you have sales figures for? ");
days = int.Parse(Console.ReadLine());

// Set the accumulator to 0.
totalSales= 0;

// Get the sales figures and calculate a running total
for (int count = 1; count <= days; count++)
{
    Console.Write($"Enter the sales figure for day #{count}");
    sales = double.Parse(Console.ReadLine());
    totalSales+= sales;
}
```

### AverageMark.cs

```csharp
int students;       // The number of students
double mark;        // Mark for a single student
double totalMarks;  // Total marks for all students
double averageMark; // Average mark for all students
string userInput;

// Prompt and read in the number of students
Console.WriteLine("How many students?");
userInput= Console.ReadLine();
students = int.Parse(userInput);

// Set the accumulator to 0.
totalMarks= 0;

// For each student, prompt and read in their mark
// and calculate a running total.
for(int count = 1; count <= students; count += 1)
{
    Console.WriteLine($"Enter mark for student #{count}:");
    userInput= Console.ReadLine();
    mark = double.Parse(userInput);
    totalMarks+= mark;
}
// Calculate the average mark
averageMark= totalMarks/ students;
// Display the average mark
Console.WriteLine($"The average mark is {averageMark:F1}");
```

### SentinelValues.cs

```csharp
// Read an initial data
Console.Write("Enter an integer (the input ends if it is 0): ");
int data = int.Parse(Console.ReadLine());

// Keep reading until the input is 0
int sum = 0;
while (data != 0)
{
    sum += data;
    // Read the next data
    Console.Write("Enter an integer (the input ends if it is 0): ");
    data = int.Parse(Console.ReadLine());
}
Console.WriteLine("The sum is " + sum);
```


#### [Looping Home](index.md)
#### [CPSC1012 Home](../)