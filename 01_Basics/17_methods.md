# C# Methods Example

This project demonstrates the use of methods in C#. Methods allow for code reusability and better organization by encapsulating a section of code that can be executed whenever called (invoked). 

## Code Overview
```csharp
using System;

namespace consoleApp1
{
    class Program
    {
        static void Main(string[] arg)
        {
            // Method: Performs a section of code when invoked
            // Benefits: Code reusability, structure, and readability

            wish("John");  // Method invocation with argument
            int sum = Add(5, 10);
            string greeting = Greet("Alice");
            bool isEven = CheckEven(8);
            double area = CalculateArea(4.5);

            Console.WriteLine($"Sum: {sum}");
            Console.WriteLine(greeting);
            Console.WriteLine($"Is Even: {isEven}");
            Console.WriteLine($"Area: {area}");

            Console.ReadKey(); 
        }

        // Method Definition with Parameter (void)
        static void wish(string name)
        {
            Console.WriteLine($"Happy Birthday to you, {name}!");
        }

        // Method that returns int
        static int Add(int a, int b)
        {
            return a + b;
        }

        // Method that returns string
        static string Greet(string name)
        {
            return $"Hello, {name}!";
        }

        // Method that returns bool
        static bool CheckEven(int number)
        {
            return number % 2 == 0;
        }

        // Method that returns double
        static double CalculateArea(double radius)
        {
            return Math.PI * radius * radius;
        }
    }
}
```

## How It Works
1. **Method Definition**:
   - A variety of methods are defined, each demonstrating different return types (`void`, `int`, `string`, `bool`, `double`).
   - These methods perform specific tasks, such as adding numbers, greeting users, or calculating area.

2. **Method Invocation**:
   - Each method is called from the `Main` method, and their results are stored in variables or directly printed.
   
3. **Purpose of Methods**:
   - **Reusability**: The same method can be invoked multiple times with different arguments.
   - **Organization**: Separating code into methods makes the program more readable and easier to manage.
   - **Flexibility**: Methods with return types allow for computations and logic handling.

## Example Output
```
Happy Birthday to you, John!
Sum: 15
Hello, Alice!
Is Even: True
Area: 63.61725123519331
```

## Key Concepts
- **Method**: A block of code designed to perform a specific task whenever it is invoked. Methods enhance modularity and reduce code duplication.
- **Parameters and Arguments**:
   - **Parameters**: Placeholders in method definitions that accept input values.
   - **Arguments**: The actual values passed to the method during invocation.
- **Void**: A keyword that specifies a method does not return any value. The method performs an action but doesn't send data back.
- **Return Types**: Methods can return different data types, including:
   - **`int`**: Returns integer values.
   - **`string`**: Returns text values.
   - **`bool`**: Returns true/false.
   - **`double`**: Returns floating-point numbers.
- **Invocation**: Methods are executed by calling their name and passing required arguments. This reduces repetition and makes the code cleaner.
- **Encapsulation**: Methods encapsulate specific tasks, promoting better organization and separation of concerns.

## Advantages of Methods
- **Code Reusability**: Write once, use multiple times.
- **Improved Readability**: Simplifies the `Main` method by delegating tasks to other methods.
- **Maintainability**: Easier to update or modify specific parts of the code without affecting the entire program.
- **Customizable**: Parameters allow methods to handle various inputs dynamically.

Methods are a fundamental part of C# programming, allowing developers to create more modular, efficient, and organized code.

