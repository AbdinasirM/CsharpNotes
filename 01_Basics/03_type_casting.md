# C# Basics - Type Casting

Welcome to this introduction to type casting in C#! This guide explains the concept of type casting, why it's important, and provides easy-to-understand examples.

## Table of Contents
- [C# Basics - Type Casting](#c-basics---type-casting)
  - [Table of Contents](#table-of-contents)
  - [Introduction](#introduction)
  - [What is Type Casting?](#what-is-type-casting)
  - [Implicit vs. Explicit Casting](#implicit-vs-explicit-casting)
    - [Implicit Casting](#implicit-casting)
    - [Explicit Casting](#explicit-casting)
  - [Using the `Convert` Class](#using-the-convert-class)
    - [Example of Using `Convert`](#example-of-using-convert)
  - [Example Code](#example-code)
  - [Explanation of `Console.ReadKey()`](#explanation-of-consolereadkey)
  - [Key Takeaways](#key-takeaways)

---

## Introduction
Type casting is the process of converting a value from one data type to another. This is essential when you need to perform operations on different types of data or when you want to store values in specific formats.

---

## What is Type Casting?
Type casting allows you to convert a variable of one type to another. This is useful when you want to:
- Perform arithmetic operations between different data types.
- Store floating-point values as integers.
- Convert numeric values to strings or vice versa.

---

## Implicit vs. Explicit Casting

### Implicit Casting
Implicit casting happens automatically when there is no risk of losing data.

**Example:**
```csharp
int number = 10;
double result = number;  // Implicit casting from int to double
Console.WriteLine(result);  // Outputs: 10.0
```

### Explicit Casting
Explicit casting must be done manually when there is potential data loss.

**Example:**
```csharp
double pi = 3.14;
int piInt = (int)pi;  // Explicit casting from double to int
Console.WriteLine(piInt);  // Outputs: 3
```

---

## Using the `Convert` Class
C# provides the `Convert` class to facilitate type conversions between different types.

### Example of Using `Convert`
```csharp
double pi = 3.14;
int pi_numb = Convert.ToInt32(pi);  // Convert double to int
Console.WriteLine(pi_numb);  // Outputs: 3
```

You can also use the `GetType()` method to check the resulting data type:
```csharp
Console.WriteLine(pi_numb.GetType());  // Outputs: System.Int32
```

---

## Example Code
```csharp
using System;

namespace consoleApp1
{
    class Program
    {
        static void Main(string[] arg)
        {
            // Type casting: converting a value to a different data type
            double pi = 3.14;
            Console.WriteLine(pi);

            int pi_numb = Convert.ToInt32(pi);  // Explicit casting using Convert class
            Console.WriteLine(pi_numb);

            Console.WriteLine(pi_numb.GetType());  // Check resulting type

            Console.ReadKey();  // Waits for a key press
        }
    }
}
```

---

## Explanation of `Console.ReadKey()`
`Console.ReadKey()` waits for the user to press any key before the console window closes. This helps keep the console window open so you can view the output.

**Example:**
```csharp
Console.WriteLine("Press any key to continue...");
Console.ReadKey();  // Pauses until a key is pressed
```

---

## Key Takeaways
- Type casting allows conversion between data types.
- Implicit casting is automatic, while explicit casting must be performed manually.
- Use the `Convert` class for easy and reliable type conversions.
- `Console.ReadKey()` prevents the console from closing immediately after execution.
