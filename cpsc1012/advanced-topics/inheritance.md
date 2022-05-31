---
layout: page
title: Advanced Topics - OOP Inheritance
---

## Introduction
One of the cool aspect of OOP is inheritance. Inheritance is when you create a base, or parent, class and classes that inherit properties and methods from the parent class. In the class diagram below you will see that the `Person` class has a `ContactInfo` property which is represented by the solid diamond at the end of the relationship; the `Person` class cannot exist without the `ContactInfo ` class. Additionally you will see open diamonds at the end of the relationships to the `Person` class from the `Instructor` and `Student` classes. This makes the `Person` class the **parent** class.

Examining the properties and constructors of the `Instructor` and `Student` classes you will see that their constructors need all the parameters from the `Person` class in addition to the specific properties of their respective classes:<br>
![inheritance-class-diagram](files/inheritance-class-diagram.jpg)

_NOTE: For simplicity there is no validation in the classes below, but it can easily be added. Additionally, the classes are placed in a separate folder, `Classes`, to demonstrate that you can organize your classes._

### ContactInfo Class

```csharp
namespace InheritanceDemo.Classes
{
    public class ContactInfo
    {
        private string _email;
        private string _phone;

        public string Email
        {
            get { return _email; }
            set { _email = value; }
        }

        public string Phone
        {
            get { return _phone; }
            set { _phone = value; }
        }

        public ContactInfo(string email, string phone)
        {
            Email = email;
            Phone = phone;
        }

        public override string ToString()
        {
            return string.Format("Email: {0}\nPhone: {1}",Email,Phone);
        }
    }//eoc
}//eon
```

### Person Class

```csharp
namespace InheritanceDemo.Classes
{
    public class Person
    {
        private int _idNumber;
        private string _lastname;
        private string _firstName;
        private ContactInfo _contact;

        public int IDNumber
        {
            get { return _idNumber; }
            set { _idNumber = value; }
        }

        public string LastName
        {
            get { return _lastname; }
            set { _lastname = value; }
        }

        public string FirstName
        {
            get { return _firstName; }
            set { _firstName = value; }
        }

        public ContactInfo Contact
        {
            get { return _contact; }
            set { _contact = value; }
        }

        public Person()
        {
            IDNumber = 1;
            LastName = "Doe";
            FirstName = "John";
            Contact = new ContactInfo("me@here.com", "1-780-555-1212");
        }

        public Person(int idNumber, string lastname, string firstName, ContactInfo contact)
        {
            IDNumber = idNumber;
            LastName = lastname;
            FirstName = firstName;
            Contact = contact;
        }

        public override string ToString()
        {
            return string.Format("ID: {0},\nName: {1}, {2}\nContact: {3}", IDNumber, LastName, FirstName, Contact);
        }
    }//eoc
}//eon
```

### Instructor Class

```csharp
namespace InheritanceDemo.Classes
{
    public class Instructor : Person
    {
        private string _officeNumber;

        public string OfficeNumber
        {
            get { return _officeNumber; }
            set { _officeNumber = value; }
        }

        public Instructor(int idNumber, string lastName, string firstName, ContactInfo contact, string officeNumber)
        {
            IDNumber = idNumber;
            LastName = lastName;
            FirstName = firstName;
            Contact = contact;
            OfficeNumber = officeNumber;
        }

        public override string ToString()
        {
            return string.Format("ID: {0},\nName: {1}, {2}\nContact: {3}\nOffice: {4}", IDNumber, LastName, FirstName, Contact, OfficeNumber);
        }
    }//eoc
}//eon
```

### Student Class

```csharp
namespace InheritanceDemo.Classes
{
    public class Student : Person
    {
        private string _program;
        private int _semester;

        public string Program
        {
            get { return _program; }
            set { _program = value; }
        }

        public int Semester
        {
            get { return _semester; }
            set { _semester = value; }
        }

        public Student(int idNumber, string lastName, string firstName, ContactInfo contact, string program, int semester)
        {
            IDNumber = idNumber;
            LastName = lastName;
            FirstName = firstName;
            Contact = contact;
            Program = program;
            Semester = semester;
        }

        public override string ToString()
        {
            return string.Format("ID: {0},\nName: {1}, {2}\nContact: {3}\nProgram: {4}\nSemester: {5}", IDNumber, LastName, FirstName, Contact, Program, Semester);
        }
    }//eoc
}//eon
```

### Program Class
As the classes above are in a separate folder, you will need the collowing using code line:

```csharp
using InheritanceDemo.Classes;
```

In the `Main()` method you will need a collection object for all the `Person` (including `Instructor` and `Student`) objects:

```csharp
List<Person> people = new List<Person>();
```
#### LoadPersons()
This method will load data into the `List<Person>`; it will contain `Person`, `Instructor`, and `Student` objects:

```csharp
static void LoadPersons(List<Person> people)
{
    //1. Add a default person object to the List
    people.Add(new Person());

    //2. Add some Instructors
    people.Add(new Instructor(2, "Anderson", "Allan", new ContactInfo("aanderson@nait.ca", "1-780-378-5275"), "W309"));
    people.Add(new Instructor(3, "Doe", "Jane", new ContactInfo("janed@nait.ca", "1-780-333-1111"), "W309"));

    //3. Add some Students
    people.Add(new Student(1001, "Stardust", "Ziggy", new ContactInfo("ziggys@gmail.com", "1-587-555-1212"), "DMIT", 1));
    people.Add(new Student(1002, "Kenobi", "Obi-Wan", new ContactInfo("jedi-master@gmail.com", "1-999-999-9999"), "BAIST", 4));
}//end of LoadPersons
```

To call this method use:

```csharp
LoadPersons(people);
```

#### DisplayPersons()
This method will display all the `Person` objects in the list:

```csharp
static void DisplayPersons(List<Person> people)
{
    foreach(Person person in people)
    {
        Console.WriteLine(person);
    }
}//end of DisplayPersons
```

To call this method add the following:

```csharp
Console.WriteLine("All Person Objects:");
DisplayPersons(people);
```

#### DisplayStudents()
This method will **only** display the `Student` objects in the `List<Person>`:

```csharp
static void DisplayStudents(List<Person> people)
{
    foreach(Person person in people)
    {
       if (person.GetType() == typeof(Student))
       {
            Console.WriteLine(person);
        }
    }
}//end of DisplayStudents
```

Do not forget to add the following:

```csharp
Console.WriteLine("\nOnly Student Objects:");
DisplayStudents(people);
```
#### DisplayInstructors()
This method is just like the `DisplayStudents()` method:

```csharp
static void DisplayInstructors(List<Person> people)
{
    foreach(Person person in people)
    {
       if (person.GetType() == typeof(Instructor))
       {
            Console.WriteLine(person);
        }
    }
}//end of Displayinstructors
```

Do not forget to add the following:

```csharp
Console.WriteLine("\nOnly Instructor Objects:");
DisplayInstructors(people);
```

### Output

![inheritance-1](files/inheritance-1.jpg)<br>
![inheritance-2](files/inheritance-2.jpg)<br>
![inheritance-3](files/inheritance-3.jpg)

#### [Advanced Home](index.md)
#### [CPSC1012 Home](../index.md)