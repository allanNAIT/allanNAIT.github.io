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
Ziggy Stardust,45
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

### Variables
You will need variables to hold the data from the file and to aid in reading the file:

```csharp
string input; //used to hold the text from one line of the file
string name;
int grade;
```

### Check if the File Exists
Before you can attempt to read the file you need to see if it exists in the declared constant `PathAndFile`; if the file does not exist, you cannot read it. This accomplisged with a simple decision structure:

```csharp
//1. Test if the file exists
if (File.Exists(PathAndFile))
{
    
}
else
{
    
}
```

### Reading & Exception Handling
You will need to use the `StreamReader` class to read the file. As there may be unexpected errors when reading the file, you will need to use a `try-catch-finally` coding structure. Modify your code to now have the following:

```csharp
//1. Test if the file exists
if (File.Exists(PathAndFile))
{
    //2. Setup the StreamReader
    StreamReader reader = null;

    //3. Use a try-catch to read and display the file contents
    try
    {
        //4. Open the file for reading
        reader = File.OpenText(PathAndFile);

        //5. Display column headers
        Console.WriteLine("Name            Mark");
        Console.WriteLine("==============  ====");

        //6. Use a while loop to loop through the file
        while((input = reader.ReadLine()) != null) //read until the end of the file
        {
            //7. Split the line of the file on the delimeter, i.e., the comma
            string[] parts = input.Split(',');

            //8. Read and display the data from the line of the file
            name = parts[0];
            grade = int.Parse(parts[1]);
            Console.WriteLine("{0,-15} {1,3}", name, grade);
        }
    }
    catch (Exception ex)
    {
        //9. Display and Exceptions
        Console.WriteLine(ex.Message);
    }
    finally
    {
        //10. Close the StreamReader
        reader.Close();
    }
}
else
{
    //11. Information message if the file does not exist
    Console.WriteLine($"The file {PathAndFile} does not exist");
}
```




## Coding Topics
TBD...

#### [CPSC1012 Home](../)