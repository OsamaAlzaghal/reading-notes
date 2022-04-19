# Dependency Injection & Repository Design Pattern
---

## What is a Dependency Injection?
A dependency is an object that another object depends on. Dependency Injection (or inversion) is basically providing the objects that an object needs, instead of having it construct the objects themselves. It is a useful technique that makes testing easier, as it allows you to mock the dependencies.

For example, if class A calls a method on class B, which in turn calls a method on class C, that means A depends on B and B depends on C. Using dependency injection, we can pass an instance of class C to class B, and pass an instance of B to class A, instead of having these classes to construct the instances of B and C. [Source](https://www.tutorialspoint.com/explain-dependency-injection-in-chash#:~:text=Dependency%20Injection%20(or%20inversion)%20is,you%20to%20mock%20the%20dependencies.)

```
using System;
class Program{
   static void Main(string[] args){
      var runner = new Runner();
      runner.Run();
   }
}
class Runner{
   private Logger _logger;
   public Runner(){
      _logger = new Logger();
   }
   public void Run(){
      // Do some work
      _logger.Log("Message to be logged");
   }
}
class Logger{
   public void Log(string message){
      Console.WriteLine(message);
   }
}
```
---
## What is a Repository Pattern?
 
By definition, the Repository Design Pattern in C# mediates between the domain and the data mapping layers using a collection-like interface for accessing the domain objects. Repository Design Pattern separates the data access logic and maps it to the entities in the business logic.
### Advantages of Repository Design Pattern:
+ Testing controllers becomes easy because the testing framework need not run against the actual database access code.
+ Repository Design Pattern separates the actual database, queries and other data access logic from the rest of the application.
+ Business logic can access the data object without having knowledge of the underlying data access architecture.
+ Business logic is not aware of whether the application is using LINQ to SQL or ADO.NET. In the future, underlying data sources or architecture can be changed without affecting the business logic.
+ Caching strategy for the data source can be centralized.
+ Centralizing the data access logic, so code maintainability is easier. [Source](https://www.c-sharpcorner.com/article/repository-design-pattern-in-asp-net-mvc/#:~:text=What%20is%20a%20Repository%20Design,entities%20in%20the%20business%20logic.)

![img](https://dotnettutorials.net/wp-content/uploads/2018/07/Using-Repository-Design-Pattern-in-C.png)

---
## SOLID Principles
![img](https://miro.medium.com/max/1400/1*wrxj0oBKpA_GXb8LPhXOeg.png)

SOLID principles are the design principles that enable us to manage most of the software design problems. SOLID is an acronym of the following:
+ S: Single Responsibility Principle (SRP): A class should have a single responsibility.
	![img](https://miro.medium.com/max/1400/1*P3oONz9Da3Tc1w97fMV73Q.png)

+ O: Open closed Principle (OCP): Classes should be open for extension, but closed for modification.
	![img](https://miro.medium.com/max/1400/1*0MtFBmm6L2WVM04qCJOZPQ.png)

+ L: Liskov substitution Principle (LSP): If S is a subtype of T, then objects of type T in a program may be replaced with objects of type S without altering any of the desirable properties of that program.
	![img](https://miro.medium.com/max/1400/1*yKk2XKJaCLNlDxQMx1r55Q.png)

+ I: Interface Segregation Principle (ISP): Clients should not be forced to depend on methods that they do not use.
	![img](https://miro.medium.com/max/1400/1*2hmyR9L43Vm64MYxj4Y89w.png)

+ D: Dependency Inversion Principle (DIP): High-level modules should not depend on low-level modules. Both should depend on the abstraction. Abstractions should not depend on details. Details should depend on abstractions.
	![img](https://miro.medium.com/max/1400/1*Qk8tDmjQlyvwKxNTfXIo0Q.png)

[Source](https://medium.com/backticks-tildes/the-s-o-l-i-d-principles-in-pictures-b34ce2f1e898)

---
## Why SOLID Matters?
SOLID Principles is a coding standard that all developers should have a clear concept for developing software properly to avoid a bad design. They are to help you make your code easy to adjust, extend and test with little to no problems.