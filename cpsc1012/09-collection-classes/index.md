---
layout: page
title: Collection Classes
---
## Introduction
**CONCEPT**: This concept is an extension to that of [Arrays](../07-arrays/). The collection class used will be the generic list, `List<T>`. This is a strongly typed list that has built-in methds for sorting, searching, and modifying the contents of the list.

## List<T>
The `<T>` is stands for any **T**ype of object.

The `List<T>` has the following properties:
*  `.Count`: allows you to display the number of _objects_ in the list.

The `List<T>` has the following methods:
*  `.Add()`: allows you to add a new _object_ to the end of the list
*  `.Clear()`: allows you to delate all the _objects_ in the list
*  `.Find()`: allows you to find the first item in the list that matches the search criteria
*  `.Remove()`: allows you remove the first occurence of the _object_ in the list
*  `.RemoveAt()`: allows you to remove an _object_ from the list at a specified index
*  `.Sort()`: allows you to sort the list; this requires a different technique from sorting an array

_Note: Adding or removing an object from a list will automatically change the `.Count` property._


## Useful Code
### Lambda Sort

```csharp
employees.Sort((e1, e2) => e1.DOB.CompareTo(e2.DOB));
```

### List<T> Demo Methods

```csharp
static void DisplayList(List<string> classNames)
{
    int row = 1;
    Console.ForegroundColor = ConsoleColor.DarkMagenta;
    Console.WriteLine(" Names List:\n ----------------");
    foreach (string name in classNames)
    {
        if (row % 2 != 0)
        {
            Console.ForegroundColor = ConsoleColor.Blue;
        }
        else
        {
            Console.ForegroundColor = ConsoleColor.DarkRed;
        }
        Console.WriteLine("{0,3}. {1}", row, name);
        row++;
    }//end foreach
    Console.ForegroundColor = ConsoleColor.DarkMagenta;
    Console.WriteLine(" ----------------\n");
    Console.WriteLine("There are {0} students in this class", classNames.Count());
}//eom

static void RemoveElement(List<string> classNames, int location)
{
    classNames.RemoveAt(location - 1); // only because the row = index + 1
}//eom

static void RemoveElement(List<string> classNames, string searchName)
{
    int index = SearchList(classNames, searchName);
    if(index >= 0)
    {
        classNames.Remove(searchName);
    }
}//eom

static int SearchList(List<string> classNames, string searchName)
{
    //If found will return a valid index, else will return -1
    //Here we are using a Lambda expression you do not need to
    // know how these work, just that they do.
    return classNames.FindIndex(item => item.Equals(searchName));
}//eom

static void AddName(List<string> classNames)
{
    string name = GetValidName("Enter your full name: ");
    classNames.Add(name);
}//eom

static void SortList(List<string> names)
{
    int minIndex;
    string minValue, temp;
    for(int startScan = 0; startScan < names.Count - 1; startScan++)
    {
        minIndex = startScan;
        minValue = names[startScan];
        for(int index = startScan; index < names.Count; index++)
        {
            if(names[index].CompareTo(minValue) < 0)
            {
                minValue = names[index];
                minIndex = index;
                // now swap
                temp = names[minIndex];
                names[minIndex] = names[startScan];
                names[startScan] = temp;
            }
        }
    }
}//eom
```

#### [CPSC1012 Home](../)