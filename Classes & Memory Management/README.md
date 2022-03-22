# Classes & Memory Management
---
## What is a class?
A class is a user-defined blueprint or prototype from which objects are created. A class contains methods and properties that can be accessed by creating an object of that class.

---
## Introduction to classes:
Classes are known as reference types, but what does reference types mean? A reference type doesn't store its value directly. Instead, it stores the address where the value is being stored. So a reference type contains a pointer to another memory location that holds the data. 

Below is a code sample from [Microsoft docs](https://docs.microsoft.com/en-us/dotnet/csharp/fundamentals/types/classes):


```
/Declaring an object of type MyClass.
MyClass mc = new MyClass();

//Declaring another object of the same type, assigning it the value of the first object.
MyClass mc2 = mc;
```

---
## Declaring Classes
We can declare a class by using **class** word followed by the class's name.

Below is a code sample from [Microsoft docs](https://docs.microsoft.com/en-us/dotnet/csharp/fundamentals/types/classes):

```
//[access modifier] - [class] - [identifier]
public class Customer
{
   // Fields, properties, methods and events go here...
}
```
When we say that our class is public, it means that anyone can create instances of this class. The class body can contain fields, properties, methods and events and they are called class members.

---
## Creating objects


### What does object mean?
First, object is an instance of a class. An object is an entity of the class. So the object type is the same as the class's name. 


### How to create object?
Objects can be created by using the new keyword followed by the name of the class. So for an example, 
```
// We created an object called sportCar of type class Car. 
// So sportCar holds an address of the actual object,
// In other words, it is a reference to an object.
Car sportCar = new Car();

// This is an object reference, but it doesn't refer to an object.
Car raceCar;

// In this line, sportCar is a reference to a Car object,
// Both objects refer to the same object.
Car sportCar = new Car();
Car deliveryCar = sportCar;
```
---
## Class inheritance
If we want classes to get fields and methods from one class to another, we can inherit it. So we will have a base class which we will get our fields and methods from, and a child class which inherits them.
```
public class BaseClass : ChildClass
{
	// BaseClass fields, properties, methods and events are inherited.
	// ChildClass fields, properties, methods and events. 
}
```
*Note: you can have multiple inheritance, and When a class declares a base class, it inherits all the members of the base class except the constructors.*

---
## Constructors
### What is a Constructor?
"A constructor is a special method of the class which gets automatically invoked whenever an instance of the class is created. Like methods, a constructor also contains the collection of instructions that are executed at the time of Object creation." [Soruce](https://www.geeksforgeeks.org/c-sharp-constructors/#:~:text=A%20constructor%20is%20a%20special,the%20time%20of%20Object%20creation.).
### Constructor syntax
The constructor have the same name as the class type, and you can add the signature but it's optional and it doesn't have a return type.

Here I used the example which Microsoft provided in their [docs](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/constructors), since it's the most simple code I found.

So the constructor Person is created, and it takes two arguments to set the properties which the user send when he/her declare an object.
```
public class Person
{
   private string last;
   private string first;

   public Person(string lastName, string firstName)
   {
      last = lastName;
      first = firstName;
   }

   // Remaining implementation of Person class.
}
```
### Static constructors
It is used to initialize static members of the class and it takes no prameters, so if the user didn't create one, the compiler will give them a default values.

Code [example](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/constructors):

```public class Adult : Person
{
   private static int minimumAge;

   public Adult(string lastName, string firstName) : base(lastName, firstName)
   { }

   static Adult()
   {
      minimumAge = 18;
   }

   // Remaining implementation of Adult class.
}

```

---
## Properties 
![Image](https://uj2y8f97.cdn.imgeng.in/wp-content/uploads/2020/08/C-Properties.png)

---
## What does it mean?
Properties are class members, and if the user wants to get the data or edit them, he/she should use the set and get which are special methods called accessors. 
## Why do we use it?
This enables data to be accessed easily and still helps promote the safety and flexibility of methods.

**Note**: "Properties can be read-write (they have both a get and a set accessor), read-only (they have a get accessor but no set accessor), or write-only (they have a set accessor, but no get accessor). Write-only properties are rare and are most commonly used to restrict access to sensitive data."
[Source](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/properties).

 ## Properties with backing fields
Backing fields support the concept of encapsulation. Encapsulation allows you to later change the implementation details of the class without changing its interface.

## Auto-implemented properties
To make your code easier and set/get the data automatically from a backing field by using auto-implemented properties.

**Note:** if the property has get and set, both of them must be auto implemented.
```
public string Name
   { get; set; }

   public decimal Price
   { get; set; }
   
// To get the data after creating an object, 
// Use objectName.Price or objectName.Name  
```
Since the topic is branched, I mentioned the basic concepts but you can view the full topic by clicking [here](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/properties).

---
## Stack vs. Heap: What's the difference?
Stack: stack a temporary place(static) where we save our data that behaves first-in-last-out, so we have an order and it is used for storing order of method execution and local variables. 

Heap: heap is a temporary area of memory used for dynamic memory allocation. The blocks of memory have no specific order and it is used for certain types of data objects.

"The stack is a place in the computer memory where all the variables that are declared and initialized before runtime are stored. The heap is the section of computer memory where all the variables created or initialized at runtime are stored.". [Source](http://www.maxi-pedia.com/what+is+heap+and+stack#:~:text=%EF%BB%BF,initialized%20at%20runtime%20are%20stored.)
### Stack:
+ It is an array of memory.
+ It is a LIFO (Last In First Out) data structure.
+ In it data can be added to and deleted only from the top of it.
+ Memory allocation is Static.
+ It is stored Directly.
+ Variables can’t be Resized.
+ Its access is fast.	
+ .NET Runtime throws exception “StackOverflowException” when stack space is exhausted.
+ Local variables get wiped off once they lose the scope
+ It contains values for Integral Types, Primitive Types and References to the Objects.

### Heap:
+ It is an area of memory where chunks are allocated to store certain kinds of data objects.
+ In it data can be stored and removed in any order.
+ Memory allocation is Dynamic.
+ It is stored indirectly.
+ Variables can be Resized.
+ Its access is Slow.
+ It has Garbage Collector to monitor allocations of heap space.
---
## Fundamentals of garbage collection
Garbage Collector manages the allocation and release of memory, so you don't need to worry about managing the memory when writing your code.


## Benefits

+ You don't worry about memory releasing.
+ Deals with objects on heap.
+ Reclaims objects that are no longer being used, clears their memory, and keeps the memory available for future allocations.
+ Provides memory safety so every object has it's own memory.

### Virtual memory can be in three states:
1. Free: the block is empty and available for allocation.
2. Reserved: ready for your use and not for allocation by other request unless it's committed.
3. Committed: The block of memory is assigned to physical storage.

## Fundamentals of memory:
+ Each process has it's part of memory.
+ By default, on 32-bit computers, each process has a 2-GB user-mode virtual address space.
+ If you only deal with virtual memory, the garbage collector allocates and frees virtual memory for you on the managed heap.


## Memory allocation
Memory allocation is the process of reserving a partial or complete portion of computer memory for the execution of programs and processes, so there are steps to allocate memory and you can view them [here](https://docs.microsoft.com/en-us/dotnet/standard/garbage-collection/fundamentals).

## Memory release
Memory release is the process of emptying the reserved space of computer memory after the programs finish executing or not needed, so it saves space and allows other program code to allocate memory if needed, so there are steps too to release memory and you can view them [here](https://docs.microsoft.com/en-us/dotnet/standard/garbage-collection/fundamentals).

## Conditions for a garbage collection:
+ The system has low physical memory.
+ If the memory used by allocated objects on the managed heap surpasses an acceptable threshold, you can change the threshold as you want.
+ If you call the  GC.Collect method.

## The managed heap
It is the part of memory that the garbage collector allocates to store and manage objects, so there is a managed heap for each managed process and all 
threads in the process allocate memory for objects on the same heap.

## Generations
The managed heap is divided into three generations, 0, 1, and 2, so it can handle long-lived and short-lived objects separately. 
+ Generation 0: contains short-lived objects.
+ Generation 1: contains short-lived objects and serves as a buffer between short-lived objects and long-lived objects.
+ Generation 2: contains long-lived objects.

### Examples for each generation:
+ Generation 0: a temporary variable.
+ Generation 1: objects that are promoted to generation 1 after generation 0 is collected since they have longer lifetimes.
+ Generation 2: an object in a server application that contains static data that's live for the duration of the process.

## Survival and promotions
When objects survive, they get promoted to a higher generation, so each one gets promoted to the next generation until it reaches last generation which is 2.
When the garbage collector detects that the survival rate is high in a generation, it increases the threshold of allocations for that generation. 

## Unmanaged resources
Unmanaged resources require explicit cleanup, so you have to use Dispose method to free your used memory when you finish you task.

For more information about cleaning up unmanaged resources, see [Clean up unmanaged resources](https://docs.microsoft.com/en-us/dotnet/standard/garbage-collection/unmanaged).




