# Collections & Enums
## What are collections?
Collection classes are specialized classes for data storage and retrieval. These classes provide support for stacks, queues, lists, and hash tables, so you must declare an instance of the class before you can add elements to that collection. Most collection classes implement the same interfaces. These classes made the life of developers easier.

### There are two ways to create and manage a group of related objects:
1. Create an array of objects.
2. Creating a collection of objects.

Code examples from [Microsot docs](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/concepts/collections):
```
 Library<string> secondLib = new Library<string>
 {
   "The Great Gatsby",
   "Where the Red Fern Grows",
   "Of Mice and Men"
 };
 ```
 ```
     var princesses = new List<string>();
    princesses.Add("Snow White");
    princesses.Add("Cinderella");
    princesses.Add("Aurora");
    princesses.Add("Repunzel");
    princesses.Add("Ariel");
 ```
 ---
## Generics vs. Non-Generics
---
### Generics
+ List< T>
+ Dictionary< T>
+ SortedList< T>
+ Queue< T>
+ IEnumerable< T>
+ IList< T>
+ Collection< T>
+ LinkedList< T>

---
## Non-Generics
+ ArrayList
+ HashTable
+ SortedList
+ Queue
+ Stack
+ IEnumerable
+ ICollection

**Note:** they are not really used much anymore.

---
## What are enums?
Enums(enumeration type) are lists of constants and a data type that consists of predefined values, it also provides efficient way to assign multiple constant integral values to a single variable. To define an enumeration type, use the enum keyword and specify the names of enum members:
```
enum Days
{
   Sunday,
   Monday,
   Tuesday,
   Wednesday,
   Thursday,
   Friday,
   Saturday
};

enum Months : byte
{
   Jan,
   Feb,
   Mar,
   Apr,
   May,
   Jun,
   Jul,
   Aug,
   Sep,
   Oct,
   Nov,
   Dec
};
```
### Things to consider:
+ Count starts at 0, if you do not specify a value.
+ Default type of enum is int, but you can specify alt with a :type (such as byte).

Below is a code sample from [Microsot docs](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/concepts/collections):
```
 Days today = Days.Monday;
 int dayNumber =(int)today;
 Console.WriteLine("{0} is day number #{1}.", today, dayNumber);

 Months thisMonth = Months.Dec;
 byte monthNumber = (byte)thisMonth;
 Console.WriteLine("{0} is month number #{1}.", thisMonth, monthNumber);

 // Output:
 // Monday is day number #1.
 // Dec is month number #11.
```
Also you can create and set your custom values, for an example:
```
enum MachineState
{
    PowerOff = 0,
    Running = 5,
    Sleeping = 10,
    Hibernating = Sleeping + 5
}
```
---
### What are the benefits of using enums?
The benefits of using enumerations include:
+ Reduces errors caused by transposing or mistyping numbers.
+ Makes it easy to change values in the future.
+ Makes code easier to read, which means it is less likely that errors will creep into it.
+ Ensures forward compatibility.