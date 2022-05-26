---
layout: page
title: Arrays - Searching
---

## Introduction
There are two types of searches:
*  Sequential: Start at the beginning of the array and examine each element, one after the other, to locate a value
*  Binary: Requires a sorted array does a _Divide & Conquer_ approach; splits the array in halves until the value is found

A search can return:
*  The value
*  A Boolean
*  The location in the array
*  The count of how many matching items are in the array

## Sequential Searches
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

## Binary Search
![selection-sort](files/selection-sort.jpg)
![binary-search](files/binary-search.jpg)

#### [Arrays Home](index.md)
#### [CPSC1012 Home](../)