---
layout: page
title: List<T> - Reading From File
--- 

## Intr5oduction
To tap into the power of the `List<T>`, you can store objects in the list. For this lesson, you will use the following class:

![class-diagram](files/class-diagram.jpg)

This class has the following code (_note that there is no validation for the `set` methods - you can add these later_):

```csharp
public class StudentData
{
   private string _name;
   private int _grade;

   public string Name
   {
       get { return _name; }
       set { _name = value; }
   }//end of Name

   public int Grade
   {
       get { return _grade; }
       set { _grade = value; }
   }//end of Grade

   public StudentData()
   {
       Name = "";
       Grade = 0;
   }

   public StudentData(string name, int grade)
   {
       Name = name;
       Grade = grade;
   }

   public override string ToString()
   {
       return string.Format("{0,-20} {1,3}", Name, Grade));
   }//end of ToString
}//eoc
```

### Display List
Once you read the file data, and store it in the `List<T>`, yoy will need to display the contents of the list as follows:

In your `Main()` method you could have something like:

```csharp
DisplayList(studentData);
```

And in your code file you could have something like:

```csharp
static void DisplayList(List<StudentData> studentData)
{
    Console.WriteLine("{0,-20} {1,3}", "Name", "Grade");
    foreach(StudentData student in studentData)
    {
      Console.WriteLine(student); // calls the ToString() method
    }
}//end of DisplayList
```



#### [Generics Home](index.md)
#### [CPSC1012 Home](../index.md)