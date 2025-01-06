# C# Basics - Math Class

Welcome to this introduction to the Math class in C#! This guide explains how to use the Math class to perform common mathematical operations.

## Table of Contents
- [C# Basics - Math Class](#c-basics---math-class)
  - [Table of Contents](#table-of-contents)
  - [Introduction](#introduction)
  - [Commonly Used Math Methods](#commonly-used-math-methods)
  - [Example Code](#example-code)
  - [Explanation of `Console.ReadKey()`](#explanation-of-consolereadkey)
  - [Key Takeaways](#key-takeaways)

---

## Introduction
The Math class in C# provides a collection of methods for performing mathematical operations such as rounding, exponentiation, and trigonometry. These methods are static, meaning they can be called directly from the class without creating an instance.

---

## Commonly Used Math Methods
Here are some of the most frequently used methods in the Math class:

- **`Math.Abs(x)`** – Returns the absolute value of `x`.
- **`Math.Sqrt(x)`** – Returns the square root of `x`.
- **`Math.Pow(x, y)`** – Returns `x` raised to the power of `y`.
- **`Math.Max(x, y)`** – Returns the larger of `x` and `y`.
- **`Math.Min(x, y)`** – Returns the smaller of `x` and `y`.
- **`Math.Round(x)`** – Rounds `x` to the nearest integer.
- **`Math.Ceiling(x)`** – Rounds `x` up to the nearest integer.
- **`Math.Floor(x)`** – Rounds `x` down to the nearest integer.
- **`Math.PI`** – Returns the value of π (pi).

**Example:**
```csharp
Console.WriteLine(Math.Abs(-10));      // Outputs: 10
Console.WriteLine(Math.Sqrt(25));      // Outputs: 5
Console.WriteLine(Math.Pow(2, 3));     // Outputs: 8
Console.WriteLine(Math.Max(5, 10));    // Outputs: 10
Console.WriteLine(Math.Min(5, 10));    // Outputs: 5
Console.WriteLine(Math.Round(4.6));    // Outputs: 5
Console.WriteLine(Math.Ceiling(4.3));  // Outputs: 5
Console.WriteLine(Math.Floor(4.8));    // Outputs: 4
Console.WriteLine(Math.PI);            // Outputs: 3.14159265358979
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
            // Math class examples
            Console.WriteLine("Absolute: " + Math.Abs(-7));
            Console.WriteLine("Square Root: " + Math.Sqrt(49));
            Console.WriteLine("Power: " + Math.Pow(3, 4));
            Console.WriteLine("Maximum: " + Math.Max(12, 18));
            Console.WriteLine("Minimum: " + Math.Min(12, 18));
            Console.WriteLine("Rounded: " + Math.Round(7.5));
            Console.WriteLine("Ceiling: " + Math.Ceiling(7.1));
            Console.WriteLine("Floor: " + Math.Floor(7.9));

            Console.ReadKey();  // Waits for a key press
        }
    }
}
```

---

## Explanation of `Console.ReadKey()`
`Console.ReadKey()` waits for the user to press any key before the console window closes. This is helpful for keeping the output visible after program execution.

**Example:**
```csharp
Console.WriteLine("Press any key to continue...");
Console.ReadKey();
```

---

## Key Takeaways
- The Math class provides many useful methods for mathematical operations.
- Methods like `Abs`, `Sqrt`, `Pow`, and `Round` are commonly used.
- `Console.ReadKey()` keeps the console window open until a key is pressed.