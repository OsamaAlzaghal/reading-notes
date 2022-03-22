# File and Stream I/O
---
![Image](https://i.pinimg.com/originals/bf/fc/bb/bffcbb3c0a5f66158141ae3e6c89bf11.jpg)
## What does I/O mean?  
I/O refers to Input/Output, and it means to transfer of data either to or from a storage medium.

---
## How do we read and write using C# language?  
"In .NET, the System.IO namespaces contain types that enable reading and writing, both synchronously and asynchronously, on data streams and files. These namespaces also contain types that perform compression and decompression on files, and types that enable communication through pipes and serial ports."
([Microsoft docs](https://docs.microsoft.com/en-us/dotnet/standard/io/)).

---
## What is a file?
A file is the common storage unit in a computer, and all programs and data(ordered and named) are written into and read from a file.  We can hold one or more files using something called folder, it also can contain other folders or can just be empty.

---

## What is the basic unit of a file?
Byte, the basic unit of information in computer storage and processing. A byte consists of 8 bits, which is the smallest unit of data on a computer.

---
## Some of the commonly used file and directory classes:
+ File.
+ FileInfo.
+ Directory.
+ DirectoryInfo.
+ Path.

*Note:* you can visit Microsoft Docs using [this](https://docs.microsoft.com/en-us/dotnet/standard/io/) link for more details.

---
## Exception handling in I/O operations:
Even the files can have exceptions! We can handle them using try, catch, finally, and throw.

---
## What is stream?

Streams are used to read and write to files. It is a layer between applications and files. The stream is used to ensure smooth read and write operations to the file.

---
## What is async and await in C# ?
An async method runs synchronously until it reaches its first await expression, so the method will wait until the task is complete, then it will continue executing. They are used in reading and writing files to keep our application remain responsive to the user and not cause problems since there are usually large amounts of data.

---
## What is Compression and why it is used ?
Compression is a reduction in the number of bits needed to represent data. It is used to reduce the size of one or more files. When a file is compressed, it takes up less disk space than an uncompressed version and can be transferred to other systems more quickly.

---
## How write text to a file ?
We can use the built-in classes and methods such as StreamWriter, File and Path.
### Steps on how to write lines to a text file:
1. Prepare the string you want to write.
2. Set the path of the desired file to a variable.
3. Use StreamWriter class to write on your file.

Below is a simple code of writing on a file from Microsoft Docs:
```
using System;
using System.IO;

class Program
{
    static void Main(string[] args)
    {

        // Create a string array with the lines of text
        string[] lines = { "First line", "Second line", "Third line" };

        // Set a variable to the Documents path.
        string docPath =
          Environment.GetFolderPath(Environment.SpecialFolder.MyDocuments);

        // Write the string array to a new file named "WriteLines.txt".
        using (StreamWriter outputFile = new StreamWriter(Path.Combine(docPath, "WriteLines.txt")))
        {
            foreach (string line in lines)
                outputFile.WriteLine(line);
        }
    }
}
// The example creates a file named "WriteLines.txt" with the following contents:
// First line
// Second line
// Third line
```
---
## Can you create a new file and write to it ?
Yes you can, but first you have to check if the file already exists to avoid exceptions or you can create a new one using file mode option FileMode.Create rather than FileMode.CreateNew to always create a new file without throwing an exception.

---
*Below is a sample of code that creates a new file an writes to it.*
```
using System;
using System.IO;
using System.Threading.Tasks;

namespace WriteAppTest
{
    class Program
    {
        public static async Task ExampleAsync()
        {
            string[] lines =
            {
            "First line 1", "Second line 2", "Third line 3"
        };

            await File.WriteAllLinesAsync("C:/Users/acer/Desktop/test.txt", lines);
        }
        static void Main(string[] args)
        {
            Console.WriteLine("Hello World!");
            string path = @"C:\Users\acer\Desktop\test.txt";
            using (StreamWriter sw = File.CreateText(path));
            _ = ExampleAsync();

        }
    }
}

// Output:
// A new file called test.txt and it has three lines:
// First line 1
// Second line 2
// Third line 3
```
