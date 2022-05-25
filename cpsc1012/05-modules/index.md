---
layout: page
title: Modularization
---
## Introduction
**CONCEPT**: Methods are required too be able to write, and maintain, larger programs. A method is a reusable block of code to do _something_. Methods also help with code organization and readability. Each method in a program has a unique signature:
*  Method name, and
*  Data type order of 0 or more parameters.

_Note 1: Two, or more, methods can have the same name and still be unique if their individual data type paramter lists are different; this is called **overloading**._

_Note 2: For each parameter present in a method's signature, it is the data type that matters, **not** the parameter name assigned to the data type._

> A parameter is a means of passing a value into a method call. The method is given the data to work on.

## Types of Methods
There are basically 4 types of methods:
*  Does not return a value and has 0 paramters (a `void` method)
*  Does not return a value and has 1 or more parameters (a `void` method)
*  Returns a value and has 0 paramters
*  Returns a value and has 1 or more parameters

## Arguments and Parameters
> When you read about C# you will find the words parameter and argument used interchangeably. This is actually not quite right. Understanding the difference will make C# documentation and error messages seem more sensible and might even give you a feeling of superiority over lessor programmers who don’t know the truth.<br><br>
A **parameter** is the special kind of variable that is defined in the method header and used inside that method to represent the value that was fed into the method call.<br><br>
An **argument** is the value that is supplied to the method when it is called.

Given the method below, `int` is the **parameter** supplied to the method

```csharp
static int IncrementByOne(int number)
{
    number++;
    return number;
}
```

To call this method, you need to supply an **argument** such as:

```csharp
number = IncrementByOne(number);
```

Here, the `number`, in parenthesis, is the **argument**.

## Method Signatures
As each method in a program must be unique, the following examples show both valid and invalid **method overloading**.

### Invalid Method Overloading

```csharp
static int AddNumbers(int number1, int number2)
{
    int sum = number1 + number2;
    return sum;
}//eom

static int AddNumbers(int number2, int number1)
{
   int sum = number2 + number1;
   return sum;
}//eom
```

Having both these method in your program will cause a compile error as both methods have the same name, `AddNumbers`, and have the same parameter list, `(int, int)`.

### Valid Method Overloading

```csharp
static int AddNumbers(int number1, int number2)
{
    int sum = number1 + number2;
    return sum;
}//eom

static int AddNumbers(int number1, int number2, int number3)
{
   int sum = number1 + number2 + number3;
   return sum;
}//eom
```

Having both these method in your program will compile without error. The two methods have the same name but different paramter lists `(int, int)` vs. `(int, int, int)`.


## Example
The example below is an improvement on the `AddNumbers()` methods. It will demonstrate how to reuse methods. The program will prompt the user for threee positive integers. The prompt for the numbers will use a validation method. Once all the numbers are entered, the `AddNumbers()` method will add the three numbers, return the sum to be displayed from the `Main()` method.

```csharp
class program
{
    static void Main(string[] args)
    {
        // declare variables
        int number1,
            number2,
            number3,
            sum;
        
        // user input
        number1 = GetSafeInt("Enter the 1st number: ");
        number2 = GetSafeInt("Enter the 2nd number: ");
        number3 = GetSafeInt("Enter the 3rd number: ");

        // process
        sum = AddNumbers(number1, number2, number3);

        // output
        Console.WriteLine("{0} + {1} + {2} = {3}", number1, number2, number3, sum);

        Console.ReadLine();
    }//eom

    static int GetSafeInt(string prompt)
    {
        bool isValid = false;
        int number = 0;
        do
        {
            try
            {
                Console.Write(prompt);
                number = int.Parse(Console.ReadLine());
                if (number > 0)
                {
                    isValid = true;
                }
                else
                {
                    Console.WriteLine("The number, {0}, is not a positive integer ... try again", number)
                }
            }
            catch(Exception)
            {
                Console.WriteLine("Invalid input ... try again\n");
            }
        } while(!isValid);
        return number;
    }//eom

    static int AddNumbers(int number1, int number2, int number3)
    {
        return number1 + number2 + number3;
    }//eom
}
```

_Note: the `GetSafeInt()` method gets called 3 times, each time with a different **argument** value._

#### [CPSC1012 Home](../)