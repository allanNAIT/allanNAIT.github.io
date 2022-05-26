---
layout: page
title: Arrays - 2D Arrays
---

## Introduction
**CONCEPT**: 2D arrays store data in _rows_ and _columns_ much like a spreadsheet. Accessing the data can be done in several ways:
*  Access all the data in a given _row_
*  Access all the data in a given _column_
*  Access a sigle data item by specifying its _row_ and _column_

## Sample Code

```csharp
namespace TwoDArrayDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            Setup();
            //variables
            string[,] data = { { "row0 - col0", "row0 - col1", "row0 - col2" },
                               { "row1 - col0", "row1 - col1", "row1 - col2" },
                               { "row2 - col0", "row2 - col1", "row2 - col2" },
                               { "row3 - col0", "row3 - col1", "row3 - col2" }};

            const int Rows = 5;
            const int Columns = 10;
            int[,] numbers = new int[Rows, Columns];

            int columnSum,
                rowSum,
                columnTotal= 0,
                rowTotal = 0;

            //Load the 2D int array
            LoadArrayRandom(numbers, Rows, Columns);

            //Dispaly the string 2D array
            DisplayArray(data, data.GetLength(0), data.GetLength(1));

            //Display the int 2D array
            DisplayArray(numbers, Rows, Columns);

            Console.WriteLine();
            //Add up the Column numbers
            for (int column = 0; column < Columns; column++)
            {
                columnSum = SumColumns(numbers, Rows, column);
                Console.WriteLine("The sum of numbers in column {0} is {1}", column, columnSum);
                columnTotal += columnSum;
            }//end for
            

            Console.WriteLine();
            //Add up the Row numbers
            for(int row = 0; row < Rows; row++)
            {
                rowSum = SumRows(numbers, row, Columns);
                Console.WriteLine("   The sum of numbers in row {0} is {1}", row, rowSum);
                rowTotal += rowSum;
            }//end for

            Console.WriteLine();
            Console.WriteLine("Column Total is {0}", columnTotal);
            Console.WriteLine("   Row Total is {0}", rowTotal);


            Console.ReadLine();
        }//eom

        static void DisplayArray(string[,] data, int rows, int columns)
        {
            Console.WriteLine("\nString Data:");
            for (int row = 0; row < rows; row++)
            {
                for(int col = 0; col < columns; col++)
                {
                    Console.Write("{0}\t", data[row, col]);
                }
                Console.WriteLine();
            }
        }//end of DisplayArray

        static void DisplayArray(int[,] numbers, int rows, int columns)
        {
            Console.WriteLine("\nInteger Data:");
            for (int row = 0; row < rows; row++)
            {
                for (int col = 0; col < columns; col++)
                {
                    Console.Write("{0,2}\t", numbers[row, col]);
                }
                Console.WriteLine();
            }
        }//end of DisplayArray

        static void LoadArrayRandom(int[,] numbers, int rows, int cols)
        {
            Random rnd = new Random();
            for (int row = 0; row < rows; row++)
            {
                for (int col = 0; col < cols; col++)
                {
                    numbers[row, col] = rnd.Next(1, 101);
                }//end inner for
            }//end outer for
        }//end LoadArrayRandom

        static int SumColumns(int[,] numbers, int rows, int column)
        {
            int sum = 0;
            for (int row = 0; row < rows; row++)
            {
                sum += numbers[row, column];
            }
            return sum;
        }//end SumColumns

        static int SumRows(int[,] numbers, int row, int columns)
        {
            int sum = 0;
            for (int col = 0; col < columns; col++)
            {
                sum += numbers[row, col];
            }
            return sum;
        }//end of SumRows

        #region Provided Methods - DO NOT MODIFY
        static void Setup()
        { 
            Console.Title = "2D Array Demo";
            Console.ForegroundColor = ConsoleColor.Black;
            Console.BackgroundColor = ConsoleColor.White;
            Console.Clear();
        }//end of Setup
        #endregion

    }//eoc
}//eon
```

#### [Arrays Home](index.md)
#### [CPSC1012 Home](../)