# Unit Testing and Documentation
### First of all, what is Unit Testing? 

![Image](https://testingtraveler.com/wp-content/uploads/2021/01/unit-testing.png)

**Unit test** is like a method, but it is created to test a specific functionality inside another one in isolationto check if it works properly. Developers used to write everything manually until the frameworks were created, and it made it much easier to create test units.
Unit test must be written in a proper way so it can run on a machine without failing otherwise, it's not considered as unit test.

---
### How to create a Test project?

1. Right-click on the solution file to add a project.
2. Select Templates.
3. Select Test.
4. Select Unit Test Project
5. Name it whatever you want(anything related to your test).
6. Inside the test class, create your test method and the part it's testing on your main project.
7. To run it, Click Ctrl-R.
8. On test explorer it will show you how long did it take to run and if it passed or failed.

**Tip**: always use meaningful names when naming your test methods.

---
Test example(this test was written by Erik Dietrich.): the test checks if the output of a method called Add equals the expected value of summing two numbers.


``` 
[TestClass]
public class CalculatorTests
{
    [TestMethod]
    public void Adding_4_And_3_Should_Return_7()
    {
        var calculator = new Calculator();

        int result = calculator.Add(4, 3);

        Assert.AreEqual(7, result);
    }
}
```

**Note:** Assert is a UnitTesting namespace with this Assert class in it by microsoft. 

## Steps to follow when creating a test unit:

- we arrange everything we need to run the experiment. In this case we created an object to invoke the method Add to check if the output equals the expected result. 

- Then we do something called act. In this case, we invoked the Add method and compared the result if it's as expected.

- Last step is assert, we used Assert class in the testing part.
---
![Image](https://miro.medium.com/max/1400/1*PNG3GqMvrRJXHimXeF1hlg.jpeg)
**Tip**: for every case, create a test unit, don't mix everything or create multiple tests; cause it will make it harder for you to find which one failed. Start one by one then combine them into one unit.

### Good practices:
- Think of reading the output of the test in the test runner before creating the test itself and think how it's working. 

- Avoid Test Interdependence: dont create tests that depend on each other cause at some point, they will fail and problems will occur because of the ordering.

- Make it simple and don't make things hard to understand cause it will reflect on you.

- Instead of feeling overwhelmed, relax and take to close look at you project and the methods it has.

![Image](https://mtlynch.io/good-developers-bad-tests/cover.jpg)