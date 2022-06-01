---
layout: page
title: Advanced Topics - Bitwise Operators
---

## Introduction
> Enumeration (or enum) is a value data type in C#. It is mainly used to assign the names or string values to integral constants, that make a program easy to read and maintain. For example, the 4 suits in a deck of playing cards may be 4 enumerators named Club, Diamond, Heart, and Spade, belonging to an enumerated type named Suit. Other examples include natural enumerated types (like the planets, days of the week, colors, directions, etc.). The main objective of enum is to define our own data types(Enumerated Data Types). Enumeration is declared using enum keyword directly inside a namespace, class, or structure. [GeekforGeeks](https://www.geeksforgeeks.org/c-sharp-enumeration-or-enum/){:target="_blank"}

## Enums
Add the following to the class:

```csharp
public enum SuitType
{
    Clubs = 1,
    Diamonds,
    Hearts,
    Spades
}//end of Suit

public enum CardNumber
{
    Two = 1,
    Three,
    Four,
    Five,
    Six,
    Seven,
    Eight,
    Nine,
    Ten,
    Jack,
    Queen,
    King,
    Ace
 }//end of card
 ```

 The first value in the `enum` is set to a vlaue of 1 so thatyou can get a numerical value and use it later.

 ## Program Class
 The `Main()` method should look like:

 ```csharp
 static void Main(string[] args)
{
    Setup();
    Random random = new Random();

    string suitName,
        cardNumber;
    int suit,
        card,
        suits = Enum.GetValues(typeof(SuitType)).Length,
        cards = Enum.GetValues(typeof(CardNumber)).Length;

    // get a card and its suit

    suit = random.Next(1, suits + 1);
    card = random.Next(1, cards + 1);
    suitName = Enum.GetName(typeof(SuitType), suit);
    cardNumber = Enum.GetName(typeof(CardNumber), card);

    Console.WriteLine($"You drew a {cardNumber} of {suitName}.");

    Console.ReadLine();
 }//eom

 static void Setup()
 {
    Console.Title = "Enumeration Demo";
    Console.ForegroundColor = ConsoleColor.Black;
    Console.BackgroundColor = ConsoleColor.White;
    Console.Clear();
 }//end of Setup
```

![enum-output-1](files/enum-output-1.jpg)<br>
![enum-output-2](files/enum-output-2.jpg)


#### [Advanced Home](index.md)
#### [CPSC1012 Home](../index.md)