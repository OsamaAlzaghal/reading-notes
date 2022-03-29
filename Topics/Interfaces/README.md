# Interfaces 
---

## What Does Interface Mean?
Interface is an abstract base class with only abstract members. Interface in C# is a blueprint of a class. It is like abstract class because all the methods which are declared inside the interface are abstract methods. It cannot have method body and cannot be instantiated. It is used to achieve multiple inheritance which can't be achieved by class, so abstraction can also be achieved with interfaces.

![Interfaces](https://www.oreilly.com/library/view/essential-c-70/9781509303595/graphics/353fig01.jpg)

---

## Why And When To Use Interfaces?
1. To achieve security - hide certain details and only show the important details of an object (interface).
2. C# does not support "multiple inheritance" (a class can only inherit from one base class).
---
## Important notes: 
+ An interface can inherit from one or more base interfaces. When an interface overrides a method implemented in a base interface, it must use the explicit interface implementation syntax.
+ Interfaces cannot be used to create objects.
+ When a base type list contains a base class and interfaces, the base class must come first in the list.
+ Interfaces are always implemented by more than one class.
+ An interface can't be instantiated directly. Its members are implemented by any class or struct that implements the interface.
+ A class or struct can implement multiple interfaces. A class can inherit a base class and also implement one or more interfaces.
---
Example interface from **[Microsoft docs](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/interface)**:
```
interface ISampleInterface
{
    void SampleMethod();
}

class ImplementationClass : ISampleInterface
{
    // Explicit interface member implementation:
    void ISampleInterface.SampleMethod()
    {
        // Method implementation.
    }

    static void Main()
    {
        // Declare an interface instance.
        ISampleInterface obj = new ImplementationClass();

        // Call the member.
        obj.SampleMethod();
    }
}
```
---
**Note:** In an interface declaration, the code does not declare an auto-implemented property as it does in a class or struct. Instead, it declares a property that doesn't have a default implementation but must be implemented in any type that implements the interface. So when we declare the interface, we write the property signatures but we have to do the implementation in the child class as below:

```
interface IPoint
{
   // Property signatures:
   int X
   {
      get;
      set;
   }

   int Y
   {
      get;
      set;
   }

   double Distance
   {
       get;
   }
}

class Point : IPoint
{
   // Constructor:
   public Point(int x, int y)
   {
      X = x;
      Y = y;
   }

   // Property implementation:
   public int X { get; set; }

   public int Y { get; set; }

   // Property implementation
   public double Distance =>
      Math.Sqrt(X * X + Y * Y);

}

class MainClass
{
   static void PrintPoint(IPoint p)
   {
      Console.WriteLine("x={0}, y={1}", p.X, p.Y);
   }

   static void Main()
   {
      IPoint p = new Point(2, 3);
      Console.Write("My Point: ");
      PrintPoint(p);
   }
}
// Output: My Point: x=2, y=3
```
---
