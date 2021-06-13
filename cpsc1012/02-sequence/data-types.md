---
layout: page
title: Sequence - Data Types
---

## Introduction
There are many data types in the C# programming language. The **bolded** ones in the tables and sections below are the ones that will be used in this course.

### Integral Numeric Types

C# Type | Range	 | Size	 | .NET type
--------|--------|-------|----------
sbyte | -128 to 127 | Signed 8-bit integer | System.SByte
byte | 0 to 255 | Unsigned 8-bit integer | System.Byte
short | -32,768 to 32,767 | Signed 16-bit integer | System.Int16
ushort | 0 to 65,535 | Unsigned 16-bit integer | System.UInt16
**int** | **-2,147,483,648 to 2,147,483,647** | **Signed 32-bit integer** | **System.Int32**
uint | 0 to 4,294,967,295 | Unsigned 32-bit integer | System.UInt32
long | -9,223,372,036,854,775,808 to<br>9,223,372,036,854,775,807 | Signed 64-bit integer | System.Int64
ulong | 0 to 18,446,744,073,709,551,615 | Unsigned 64-bit integer | System.UInt64

### Floating-point Numeric Types

C# Type | Range	 | Precision | Size	 | .NET type
--------|--------|-----------|-------|----------
float | ±1.5 x 10<sup>−45,</sup> to ±3.4 x 10<sup>38</sup> | ~6-9 digits | 4 bytes | System.Single
**double** | **±5.0 × 10<sup>-324</sup> to ±1.7 × 10<sup>308</sup>** | **~15-17 digits** | **8 bytes** | **System.Double**
decimal | ±1.0 x 10<sup>-28</sup> to ±7.9228 x 10<sup>28</sup> | 28-29 digits | 16 bytes | System.Decimal

### Boolean
**bool** = 1 byte: True (1) or False (0)

### The String Type
The **`string`** type represents a sequence of zero or more Unicode characters. `string` is an alias for `System.String` in .NET. The maximum size of a String object in memory is 2 GB, or about 1 billion characters.

### [Sequence Home](02-sequence.md)
### [CPSC1012 Home](../)