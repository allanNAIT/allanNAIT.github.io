---
layout: page
title: Arrays - Searching
---

## Introduction
There are two types of searches:
*  [Sequential](#sequesntial): Start at the beginning of the array and examine each element, one after the other, to locate a value
*  [Binary](#binary): Requires a sorted array and does a _Divide & Conquer_ approach; splits the array in halves until the value is found

A search can return:
*  The value
*  A Boolean
*  The location in the array
*  The count of how many matching items are in the array

## <a id="sequential">Sequential Searches</a>
Although the code examples below are for integer arrays, the logic is similar for an array of strings.
### Sequential Search - Boolean
![sequential-search-boolean](files/sequential-search-boolean.jpg)

```csharp
static bool SearchArrayBoolean(int[] grades, int size, int searchValue)
{
    bool found = false;
    for (int index = 0; index < size; index++)
    {
        if (searchValue == grades[index])
        { 
            found = true;
            index = size;
        }
    }
    return found;
}//end of SearchArrayBoolean
```

### Sequential Search - Location
![sequential-search-location](files/sequential-search-location.jpg)

```csharp
static int SearchArrayLocation(int[] grades, int size, int searchValue)
{
    int location = -1; //-1 is NOT a valid index number of an array
    for (int index = 0; index < size; index++)
    {
        if (searchValue == grades[index])
        {
            location = index;
            index = size;
        }
    }
    return location;
}//end of SearchArrayLocation
```

### Sequential Search - Count
![sequential-search-count](files/sequential-search-count.jpg)

```csharp
static int SearchArrayCount(int[] grades, int size, int searchValue)
{
    int count = 0;
    for (int index = 0; index < size; index++)
    {
        if (searchValue == grades[index])
        {
            count++;
        }
    }
    return count;
}//end of SearchArrayCount
```

### NOTE
Before coding it is important to remember that the comparison of strings is different from numerical values.
*  Numbers: `if(a == b)` is a valid test
*  Strings: `if("Allan" == "allan")` is not always valid, instead use `if("Allan".Equals("allan"))`

## <a id="binary">Binary Search</a>
### Selection Sort
![selection-sort](files/selection-sort.jpg)

```csharp
static void SelectionSort(int[] numbers, int size)
{
    int minIndex, minValue;
    int temp;
    for (int startScan = 0; startScan < size - 1; startScan++)
    {
        //assume, for now, the first element has the smallest value
        minValue = numbers[startScan];
        //now look at the rest of the array
        for (int index = startScan; index < size; index++)
        {
           if (numbers[index] < minValue)
           {
                minValue = numbers[index];
                minIndex = index;
                //now swap
                temp = numbers[minIndex];
                numbers[minIndex] = numbers[startScan];
                numbers[startScan] = temp;
            }//end if
        }//end inner for
    }//end outer for
}//end of SelectionSort
```

To apply this to an array of strings you could have:

```csharp
static void SelectionSort(string[] names, int size)
{
    int minIndex;
    string temp,
    minValue;
    for (int startScan = 0; startScan < size - 1; startScan++)
    {
        //assume, for now, the first element has the smallest value
        minValue = names[startScan];
        //now look at the rest of the array
        for (int index = startScan; index < size; index++)
        {
            if (names[index].ToUpper().CompareTo(minValue.ToUpper()) < 0)
            {
                minValue = names[index];
                minIndex = index;
                //now swap
                temp = names[minIndex];
                names[minIndex] = names[startScan];
                names[startScan] = temp;
            }//end if
        }//end inner for
    }//end outer for
}//end of SelectionSort
```

### Binary Search
![binary-search](files/binary-search.jpg)

```csharp
static int BinarySearch(int[] numbers, int size, int searchNumber)
{
    //Ensure the array is sorted!
    SelectionSort(numbers, size);
    //local variables
    int first = 0, 
        last = size - 1;
    int middle = (first + last + 1) / 2;
    int location = -1;
    //loop 
    while (first <= last && location == -1)
    {
        if (searchNumber > numbers[middle])
        {
            first = middle + 1;
        }
        else if (searchNumber < numbers[middle])
        {
            last = middle - 1;
        }
        else
        {
            location = middle;
        }
         middle = (first + last + 1) / 2;
    }
    return location;
}//end of BinarySearch
```

Applying this technique to serach through an array of strings you could have:

```csharp
static int BinarySearch(string[] names, int size, string searchName)
{
    //1. Ensure the array is sorted
    SelectionSort(names, size);
    //2. Local scope variables
    int first = 0,
        last = size -1,
        middle = (first + last + 1) / 2,
        location = -1;
    
    //3. Loop
    while (first <= last && location == -1)
    {
        if (searchName.ToUpper().CompareTo(names[middle].ToUpper()) > 0)
        {
            first = middle + 1
        }
        else if (searchName.ToUpper().CompareTo(names[middle].ToUpper()) < 0)
        {
            last = middle -1;
        }
        else
        {
            location = middle
        }
        middle = (first + last + 1) / 2;
    }
    return location;
}//end of BinarySearch
```

## Coding Example
For this demo the array will be manually filled with values.

```csharp
const int PhysicalSize = 10;
int[] numbers = { 25, 17, 4, 13, 45, 10, 17, 26, 9, 19 };

DisplayArray(numbers, PhysicalSize);
```

```csharp
static void DisplayArray(int[] numbers, int size)
{
    for(int index = 0; index < size; index++)
    {
        Console.Write($"{numbers[index]}\t");
    }
    Console.WriteLine();
}//end of DisplayArray
```

![search-sort-original](files/search-sort-original.jpg)

Testing the boolean search:

```csahrp
//Boolean search
Console.WriteLine($"Searching for 7 is {SearchArrayBoolean(numbers, PhysicalSize, 7)}");
Console.WriteLine($"Searching for 17 is {SearchArrayBoolean(numbers, PhysicalSize, 17)}");
```

![boolean-search](files/boolean-search.jpg)

Testing the location search:

```csharp
//Location Search
Console.WriteLine($"Searching for 7's location is: {SearchArrayLocation(numbers,PhysicalSize,7)}");
Console.WriteLine($"Searching for 17's location is: {SearchArrayLocation(numbers, PhysicalSize, 17)}");
```

![location-search](files/location-search.jpg)

Testing the count search:

```csharp
//Count Search
Console.WriteLine($"Count of how many 7's is {SearchArrayCount(numbers,PhysicalSize, 7)}");
Console.WriteLine($"Count of how many 17's is {SearchArrayCount(numbers, PhysicalSize, 17)}");
```

Test sorting the array:

```csharp
DisplayArray(numbers, PhysicalSize);
//Sort the Array
SelectionSort(numbers, PhysicalSize);
Console.WriteLine("\nAfter the sort ...");
DisplayArray(numbers, PhysicalSize);
```

![sorting](files/sorting.jpg)

Test the Binary Search

```csharp
//Binary Search
SelectionSort(numbers, PhysicalSize);
DisplayArray(numbers, PhysicalSize);
Console.WriteLine($"Binary search for 7's location is {BinarySearch(numbers,PhysicalSize, 7)}");
Console.WriteLine($"Binary search for 17's location is {BinarySearch(numbers, PhysicalSize, 17)}");
```

![binary-search-result](files/binary-search-result.jpg)


#### [Arrays Home](index.md)
#### [CPSC1012 Home](../)