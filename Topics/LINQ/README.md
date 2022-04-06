# Class 09:
---
## LINQ
LINQ stands for Language Integrated Query, it offers a common syntax for querying any type of data sources. LINQ applies the principles of object-oriented programming to relational data so it binds the gap between relational and object-oriented approachs. Compared to SQL, LINQ is simpler, tidier, and higher-level.

![LINQ2](https://www.ezzylearning.net/wp-content/uploads/2020/07/LINQ.gif)

---
## Why do we use LINQ?
If we want to traverse a collection to find a particular object, we have to use a 'foreach' or a 'for' loop in order to access every object and check for the values we want.

![LINQ](https://www.codeproject.com/KB/linq/UnderstandingLINQ/UnderstandingLINQ2.png)

Below is an example of student class and objects and we want to find all Student objects from an array of Students where the age is between 12 and 20.

```
class Student
{
    public int StudentID { get; set; }
    public String StudentName { get; set; }
    public int Age { get; set; }
}

class Program
{
    static void Main(string[] args)
    {
        Student[] studentArray = { 
            new Student() { StudentID = 1, StudentName = "John", Age = 18 },
            new Student() { StudentID = 2, StudentName = "Steve",  Age = 21 },
            new Student() { StudentID = 3, StudentName = "Bill",  Age = 25 },
            new Student() { StudentID = 4, StudentName = "Ram" , Age = 20 },
            new Student() { StudentID = 5, StudentName = "Ron" , Age = 31 },
            new Student() { StudentID = 6, StudentName = "Chris",  Age = 17 },
            new Student() { StudentID = 7, StudentName = "Rob",Age = 19  },
        };

        Student[] students = new Student[10];

        int i = 0;

        foreach (Student std in studentArray)
        {
            if (std.Age > 12 && std.Age < 20)
            {
                students[i] = std;
                i++;
            }
        }
    }
}
```

### Example: LINQ

```
class Program
{
    static void Main(string[] args)
    {
        Student[] studentArray = { 
                    new Student() { StudentID = 1, StudentName = "John", age = 18 } ,
                    new Student() { StudentID = 2, StudentName = "Steve",  age = 21 } ,
                    new Student() { StudentID = 3, StudentName = "Bill",  age = 25 } ,
                    new Student() { StudentID = 4, StudentName = "Ram" , age = 20 } ,
                    new Student() { StudentID = 5, StudentName = "Ron" , age = 31 } ,
                    new Student() { StudentID = 6, StudentName = "Chris",  age = 17 } ,
                    new Student() { StudentID = 7, StudentName = "Rob",age = 19  } ,
                };

        // Use LINQ to find teenager students
        Student[] teenAgerStudents = studentArray.Where(s => s.age > 12 && s.age < 20).ToArray();
       
        // Use LINQ to find first student whose name is Bill 
        Student bill = studentArray.Where(s => s.StudentName == "Bill").FirstOrDefault();
        
        // Use LINQ to find student whose StudentID is 5
        Student student5 = studentArray.Where(s => s.StudentID == 5).FirstOrDefault();
    }
}
```
**Source: [here](https://www.tutorialsteacher.com/linq/why-linq).**

---
## Three Parts of a Query Operation
+ Obtain the data source.
+ Create the query.
+ Execute the query.
---
## Basic LINQ Query Operations (C#)
+ Obtaining a Data Source.
+ Filtering.
+ Ordering.
+ Grouping.
+ Joining.
+ Selecting (Projections).

**Note:** you can view each operation with an example by clicking on this [link](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/concepts/linq/basic-linq-query-operations).

---
## Advantages of LINQ
+ Familiar language: Developers don't have to learn a new query language for each type of data source or data format.
+ Less coding: It reduces the amount of code to be written as compared with a more traditional approach.
+ Readable code: LINQ makes the code more readable so other developers can easily understand and maintain it.
+ Standardized way of querying multiple data sources: The same LINQ syntax can be used to query multiple data sources.
+ Compile time safety of queries: It provides type checking of objects at compile time.
+ IntelliSense Support: LINQ provides IntelliSense for generic collections.
+ Shaping data: You can retrieve data in different shapes.
---