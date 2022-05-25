---
layout: page
title: Looping Structures - Nested Loops
---

## Introduction
**CONCEPT**: A loop that is inside another loop is called a nested loop. A loop can be nested inside another loop.

### RectangularPattern.cs

```csharp
int rows = 6;
int columns = 8;
char symbol = '*';
// print one row at a time
for (int currentRow= 1; currentRow<= rows; currentRow++)
{
    // print a single symbol for each column of the current row
    for (int currentColumn= 1; currentColumn<= columns; currentColumn++)
    {
        Console.Write(symbol);
    }
    // start a new line for each row
    Console.WriteLine();
}
```

### TriangularPattern.cs

```csharp
int baseSize= 8;
char symbol = '*';
for (int currentRow= 1; currentRow<= baseSize; currentRow++)
{
    for (int currentColumn= 1; currentColumn<= currentRow; currentColumn++)
    {
        Console.Write(symbol);
    }
    Console.WriteLine();
}
```

### StairStep.cs

```csharp
int steps = 6;
char symbol = '#';
for (int currentRow= 1; currentRow<= steps; currentRow++)
{
    for (int currentColumn= 1; currentColumn< currentRow; currentColumn++)
    {
        Console.Write(' ');
    }
    Console.WriteLine(symbol);
}
```

#### [Looping Home](index.md)
#### [CPSC1012 Home](../)