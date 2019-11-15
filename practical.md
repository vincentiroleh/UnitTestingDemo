# Writing Unit Test for your Code

- Open Visual Studio
- Create a new console application with the name `UnitTestingDemo`
- Add a new class `MathOperation.cs` Which will be used to perform basic maths  
- Copy and Paste this code inside it:
```csharp

namespace UnitTestingDemo
{
    public static class MathOperation
    {
        public static double Add(double number1, double number2)
        {
            return (number1 + number2);
        }
        public static double Subtract(double number1, double number2)
        {
            return (number1 - number2);
        }
        public static double Multiply(double number1, double number2)
        {
            return (number1 * number2);
        }
        public static double Divide(double number1, double number2)
        {
            return (number1 / number2);
        }
    }
}

```

## Time to create a project for Unit Testing

- Right click on the solution "UnitTestingDemo" and choose `Add` and then `New Project`
- Choose `xUnit Test Project(.NET Core)` and give it the name `XunitTestDemo` and click OK

### Let's get the reference of the main project

- Right click on Dependencies of the testing project and click on `Add Reference`
- From the `Reference Manager dialog` click on solution inside Projects and select the main project and click OK
- Create a class in `XUnitTestDemo` project named `MathOperationTest.cs` and paste the following tests:

```csharp

using UnitTestingDemo;  
using Xunit;  
  
namespace XUnitTestDemo  
{  
    public class MathOperationTest  
    {  
        [Fact]  
        public void Task_Add_TwoNumber()  
        {  
            // Arrange  
            var num1 = 2.9;  
            var num2 = 3.1;  
            var expectedValue = 6;  
  
            // Act  
            var sum = MathOperation.Add(num1, num2);  
  
            //Assert  
            Assert.Equal(expectedValue, sum, 1);  
        }  
  
        [Fact]  
        public void Task_Subtract_TwoNumber()  
        {  
            // Arrange  
            var num1 = 2.9;  
            var num2 = 3.1;  
            var expectedValue = -0.2;  
  
            // Act  
            var sub = MathOperation.Subtract(num1, num2);  
  
            //Assert  
            Assert.Equal(expectedValue, sub, 1);  
        }  
  
        [Fact]  
        public void Task_Multiply_TwoNumber()  
        {  
            // Arrange  
            var num1 = 2.9;  
            var num2 = 3.1;  
            var expectedValue = 8.99;  
  
            // Act  
            var mult = MathOperation.Multiply(num1, num2);  
  
            //Assert  
            Assert.Equal(expectedValue, mult, 2);  
        }  
  
        [Fact]  
        public void Task_Divide_TwoNumber()  
        {  
            // Arrange  
            var num1 = 2.9;  
            var num2 = 3.1;  
            var expectedValue = 0.94; //Rounded value  
  
            // Act  
            var div = MathOperation.Divide(num1, num2);  
  
            //Assert  
            Assert.Equal(expectedValue, div, 2);  
        }  
    }  
}  

```

- Finally Click on Test, Test Explorer, click to `Run All` and it will execute the test case


