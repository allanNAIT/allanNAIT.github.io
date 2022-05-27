---
layout: page
title: CPSC1012 - Advanced Topics - Tuple
---

## Introduction
As a method can normally only return one value it puts a restriction on somethings programmers would like to do, i.e., return multiple values from a method. In this course the options so far are:
*  An Array
*  An Object
*  A List<T>

This advanced topic intoduces you to another _object_ that returns multiple values. Unlike an array, which all data must me the same data type, and a List<T> which can hold multiple types of data as long as they are of type `Object`, the Tuple can return different data types in a single Tuple.

## Demo Code
The code below demonstrates creating and using a Tuple:

```csharp
namespace TupleDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            Setup();

            double length = GetSafeDouble("Enter the length of the rectangle: ");
            double width = GetSafeDouble(" Enter the width of the rectangle: ");

            Tuple<double, double> result = RectangleDimensions(length, width);

            Console.WriteLine($"Area = {result.Item1}, Perimeter = {result.Item2}");

        }//eom

        static Tuple<double,double> RectangleDimensions(double length, double width)
        {
            double area = length * width;
            double perimeter = (length + width) * 2;
            return Tuple.Create(area, perimeter);
        }//end of RectangleDimensions

        static void Setup()
        {
            Console.Title = "Tuple Demo";
            Console.ForegroundColor = ConsoleColor.Black;
            Console.BackgroundColor = ConsoleColor.White;
            Console.Clear();
        }//end of Setup

        static double GetSafeDouble(string prompt)
        {
            double number = 1;
            bool isValid = false;
            do
            {
                try
                {
                    Console.Write("{0,20}", prompt);
                    number = double.Parse(Console.ReadLine());
                    if (number >= 0)
                    {
                        isValid = true;
                    }
                    else
                    {
                        Console.WriteLine("ERROR: Invalid number ... try again");
                    }
                }
                catch (Exception)
                {
                    Console.WriteLine("ERROR: Invalid number ... try again");
                }
            } while (!isValid);
            return number;
        }//end of GetSafeDouble
    }//eoc
}//eon
```

![tuple-demo](files/tuple-demo.jpg)

#### [Advanced Home](index.md)
#### [CPSC1012 Home](../index.md)