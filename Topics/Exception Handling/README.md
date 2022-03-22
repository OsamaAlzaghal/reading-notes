## What is Debugging?
Debugging means to run your code step by step in a debugging tool like Visual Studio, to find the exact point where you made a programming mistake.

![Image](https://cdn.deliciousbrains.com/content/uploads/2017/08/21091516/xdebug-php-debugging-featured-img.jpg)

---
## Questions you must ask yourself before you start debugging:
- What did you expect your code to do?
- What happened instead?
- Are you using the right method?
- Are you using it correctly?
- Does your code contain any typos?
- Did you expect an object or variable to contain a certain value (or a certain type of value) that's different from what really happened?
---

**Tip: When writing code, start small, and start with code that works!**

---

## How to start debugging?
- In Visual Studio, you can quickly set a breakpoint by clicking in the left margin next to a line of code. Or place the cursor on a line and press F9.
- A breakpoint indicates where Visual Studio should pause your running code so you can take a look at the values of variables, or the behavior of memory, or the sequence in which code runs.
- The debugger pauses on the line of code where you set the breakpoint.

To view full steps, click [Here](https://docs.microsoft.com/en-us/visualstudio/debugger/debugging-absolute-beginners?view=vs-2019&tabs=csharp) .

---

## Try/Catch Blocks
Sometimes when we write code, errors occur, and because of that we need to catch these errors and fix them. Catching the error can help the developers to know where things went wrong. Errors lead to failures and system crashes, but what if it was in embedded and real-time computer systems (rockets, planes, cars, etc...) ? 

---

## Exceptions
An exception is defined as an event that occurs during the execution of a program that is unexpected by the program code. Programming languages allow developers to include try…catch statements to handle exceptions and apply a sequence of logic to deal with the situation instead of crashing. The **try** statement allows you to define a block of code to be tested for errors while it is being executed. The **catch** statement allows you to define a block of code to be executed, if an error occurs in the try block.

```
using System;
public class Example {
	public static void Main() 
	{ 
		int number1 = 10;
  		int number2 = 0;
		try {
			// Code we want to test 
			Console.WriteLine(number1 / number2); }
			
		catch (DivideByZeroException) {
			// If an error occurs, It will throw an exception and It
			//will get catched in the catch block.
			Console.WriteLine("Division of {0} by zero.", number1);
	}
			} 	
}
// The example displays the following output: 
// Division of 10 by zero.
```
**Important note:** parameterless catch block catch{ } or general catch block catch(Exception ex){ } must be the last block. The compiler will give an error if you have other catch blocks after a catch{ } or catch(Exception ex) block.

You can find more types of **Exceptions** when dividing two numbers in this [example](https://www.tutorialsteacher.com/codeeditor?cid=cs-H1WMXT). Try it yourself!
