---
layout: page
title: Generics - ArrayList
--- 

## Introduction
An `ArrayList` works like an `Array` and is similar, but not as _powerful_ as a `List<T> `; it is an improvment on an array.

The code below demonstrates an ArrayList:

You will need to add `using Systems.Collections` before the `namespace`.

```csharp
namespace ArrayListDemo
{
    internal class Program
    {
        static void Main(string[] args)
        {
            ArrayList names = new ArrayList();
            int element;
            LoadArrayList(names);
            Console.WriteLine("Original ArrayList");
            DisplayNames(names);
            Console.Write($"\nEnter element to inspect (0 to {names.Count - 1}): ");
            element = int.Parse(Console.ReadLine());
            DisplayElement(names, element);
            SortArrayList(names);
            Console.WriteLine("\nSorted ArrayList");
            DisplayNames(names);
            Console.Write($"\nEnter element to inspect (0 to {names.Count - 1}): ");
            element = int.Parse(Console.ReadLine());
            DisplayElement(names, element);

            Console.ReadLine();
        }//eom

        static void LoadArrayList(ArrayList names)
        {
            string name;
            Console.Write("Enter name to add to the ArrayList, or zzz to quit: ");
            name = Console.ReadLine();
            while (!name.Equals("zzz"))
            {
                names.Add(name);
                Console.Write("Enter name to add to the ArrayList, or zzz to quit: ");
                name = Console.ReadLine();
            }
        }//eom

        static void DisplayNames(ArrayList names)
        {
            Console.WriteLine("Names");
            foreach (string name in names)
            {
                Console.WriteLine(name);
            }
        }//eom

        static void DisplayElement(ArrayList names, int element)
        {
            Console.WriteLine($"\nName at {element} is {names[element]}");
        }//eom

        static void SortArrayList(ArrayList names)
        {
            names.Sort();
        }//eom
    }//eoc
}//eon
```

![array-list-1](files/array-list-outout.jpg)


#### [Generics Home](index.md)
#### [CPSC1012 Home](../index.md)