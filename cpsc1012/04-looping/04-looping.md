---
layout: page
title: Looping Structures
---

## Introduction
This section builds on the concepts of the **[Simple Sequence Structure](../02-sequence/02-sequence.md)** and **[Decision Structures](../03-decisions/03-decisions.md)**. Like Decision Structures, a **Looping Structure** relies on a **boolean test**. Unlike Decision Structures, the **boolean test** is used as an entry or exit condition of the Looping Structure, i.e., a repeating block of code. The Looping Structure is used to surround code that needs to run repeatedly until the exit condition is met. These concepts will be used throughout this course.

There are only 2 logic, flowchart, structures for loops, **Pre-test** and **Post-test**. These will be explored in the [coding topics](#topics) below.

### Pre-test Loop
![pre-test-loop](files/pre-test-loop.png)

```csharp
while(test)
{
    Process1;
    Process2;
}
```
A pre-test loop (While loop) has the test before the process. This means that the process executes 0 or more times. In the factorial example, if the user enters a 0 or 1 the process never executes.  

### Post-test Loop
![post-test-loop](files/post-test-loop.png)

```csharp
do
{
    Process1;
    Process2;
}
while(test);
```

A post-test loop (sometimes called a do-until loop) has the test after the process. This means that the process executes 1 or more times. 


## <a ID="topics">Coding Topics</a>
* [While Loop](while.md)
* [Do Loop](do-loop.md)
* [For Loop](for-loop.md)
* [Nested Loops](nested.md)

### [CPSC1012 Home](../)