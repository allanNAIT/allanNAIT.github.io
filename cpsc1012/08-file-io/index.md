---
layout: page
title: File I/O
---
## Introduction
**CONCEPT**: The .NET framework provides several classes that you can use for writing data to a file and reading data from a file. To write data to a file, you can use the `StreamWriter` class. To read data from a file, you can use the `StreamReader` class.

## Reading a File
There are two basic types of files that you will learn how to read and display their data: `*.txt` and `*.csv`. Although the files types are different, the composition of the file is the same, i.e., they both use comma separated data. A sample is shown below:

```
John Doe,55
Jane Doe,65
Zack Zylenko,45
```

### System.IO
You will need to add the following code line above the `namespace` code line (preferrably above the comment block):

```csharp
//add the following namespace for reading/writing from/to a file
using System.IO;
```

### Filename & Path
In your `Main()` method you will normally need to tell your program the name and location of the file you wish to read. This can be accomplished several ways, the easiest is to decalre a constant:

```csharp
const string PathAndFile = @"C:\Work\Students.txt"; //preferred version
```

OR

```csharp
const string PathAndFile = "C:\\Work\\Students.txt"; // alternate version
```

### Check if the File Exists
Before you can attempt to read the file you need to see if it exists in the declared constant `PathAndFile`; if the file does not exist, you cannot read it. This accomplisged with a simple decision structure:

```csharp
//1. Test if the file exists
if (File.Exists(PathAndFile))
{
    
}
```



## Coding Topics
TBD...

#### [CPSC1012 Home](../)