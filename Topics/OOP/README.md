# Object-Oriented programming (C#)

## What is OOP(Object-Oriented programming)?
It is a method of writing computer programs using "classes" and "objects" to stand for data and methods. Objects are defined, each with its own properties or attributes. A derived class can have only one direct base class, but you can have multi level inheritance. For example, if you have a base class Zoo, you might have one derived class that is named Animal, then you can have another class derived of the Animal class like Lion and Tiger. A Lion is an Animal and an Animal is derived from Zoo class, and both Tiger and Lion represent different specializations of the base class. There are four fundamental concepts of Object-oriented programming – Inheritance, Encapsulation, Polymorphism, and Data abstraction.


![Example](https://media.geeksforgeeks.org/wp-content/cdn-uploads/20190501121513/inheritance.png)

---
## Abstract class and sealed key word
You can use abstract keyword enables you to create classes and class members that are incomplete and must be implemented in a derived class. The purpose of an abstract class is to provide a common definition of a base class that multiple derived classes can share. There is also another key word which is sealed, it prevents the inheritance of a class or certain class members that were previously marked virtual.

For example: 
```
public abstract class A
{
    // Class members here.
}
```
```
public sealed class D
{
    // Class members here.
}
```
## Abstract Method
+ Abstract Method resides in abstract class and it has no body.
+ Abstract Method must be overridden in non-abstract child class.
+ If an abstract method is defined in a class, then the class should declare as an abstract class.

For example: 
```
public abstract class A
{
    public abstract void DoWork(int i);
}
```

## Virtual Method
+ Virtual Method can reside in abstract and non-abstract class.
+ It is not necessary to override virtual method in derived but it can be.
+ Virtual method must have body ....can be overridden by "override keyword".

**Note:** "A derived class can override a base class member only if the base class member is declared as virtual or abstract. The derived member must use the override keyword to explicitly indicate that the method is intended to participate in virtual invocation."
-Mirosoft Docs.

For example: 

```
public class BaseClass
{
    public virtual void DoWork() { }
    public virtual int WorkProperty
    {
        get { return 0; }
    }
}
public class DerivedClass : BaseClass
{
    public override void DoWork() { }
    public override int WorkProperty
    {
        get { return 0; }
    }
}
```

---

## Inheritance
Inheritance is the procedure in which one class inherits the attributes and methods of another class. We have two key words which are:

+ Base class: The class that inherits properties from another class is called Sub class or Derived Class. 

+ Derived class: The class whose properties are inherited by sub class is called Base Class or Super class. 


For example:

```
public class Animal : Zoo
{
	// Class Zoo is a Base class.
}

public class Lion : Animal
{
	// Class Animal is a Base class
	// and a Derived class from class Zoo.
	// Class Lion is Derived from Animal class.
}

public class Tiger : Animal
{
	// Class Animal is a Base class
	// and a Derived class from class Zoo.
	// Class Tiger is Derived from Animal class.
}
```

---

## Encapsulation
Encapsulation hides the data from the access of outsiders to make the data secure. So we use it when we want to keep many details private in each class. For example We can create a fully encapsulated class in C# by making all the data members of the class private so that it prevents the data from being accessed by the code outside.

---

## Polymorphism
Polymorphism means many forms. In OOP it refers to the functions having the same names but carrying different functionalities. We use Polymorphism when we create virtual methods that derived classes could override to create specific behavior.

---

## Data abstraction
We use data abstraction for hiding the internal details or implementations of a function and showing its functionalities only to make it more simple and easy to use. This is similar to the way you know how to drive a car without knowing the background mechanism. Or you know how to turn on or off a light using a switch but you don’t know what is happening behind the socket.

