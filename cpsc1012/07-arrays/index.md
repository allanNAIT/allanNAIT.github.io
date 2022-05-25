---
layout: page
title: Arrays
---
## Introduction
This section will introduce you to the most basic of _collection classes_, an **Array**. The objectives of this section are:
1. Declare an array
2. Load an array
3. Display the data in an array

## What is an Array?
* An array is a simple collection of common data (all the elements have the same data type)
* Think of how you store all email or phone contacts. You can add, delete, or edit the list, but this list is very much like an array

## Arrays in Computer Memory
![array-in-memory](files/array-in-memory.jpg)

An array takes up a contiguous block of computer memory.

## Array Indexing
![array-indexing](files/array-indexing.jpg)

In **C#** arrays will **always** use zero-based indexing. This means the first element of the array will be `index = 0`.

## Coding Topics
* [1D Arrays](1d-array.md)
* [Parallel Arrays](parallel.md)
* [2D Arrays](2d-array.md)

## Searching the Array
There are two types of searches:
*  Sequential: Start at the beginning of the array and examine each element, one after the other, to locate a value
*  Binary: Requires a sorted array [covered later]. Does a _Divide & Conquer_ approach; splits the array in halves until the value is found

A search can return:
*  The value
*  A Boolean
*  The location in the array
*  The count of how many matching items are in the array

### Sequential Search - Boolean
![sequential-search-boolean](files/sequential-search-boolean.jpg)

### Sequential Search - Location
![sequential-search-location](files/sequential-search-location.jpg)

### Sequential Search - Count
![sequential-search-count](files/sequential-search-count.jpg)

### NOTE
Before coding it is important to remember that the comparison of strings is different from numerical values.
*  Numbers: `if(a == b)` is a valid test
*  Strings: `if("Allan" == "allan")` is not always valid, instead use `if("Allan".Equals("allan"))`


#### [CPSC1012 Home](../)

