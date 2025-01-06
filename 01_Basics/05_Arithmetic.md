# C# Basics - Basic Arithmetic

Welcome to this introduction to basic arithmetic in C#! This guide explains how to perform simple arithmetic operations and introduces essential concepts with easy-to-understand examples.

## Table of Contents
- [C# Basics - Basic Arithmetic](#c-basics---basic-arithmetic)
  - [Table of Contents](#table-of-contents)
  - [Introduction](#introduction)
  - [Performing Basic Arithmetic](#performing-basic-arithmetic)
  - [Arithmetic Operators in C#](#arithmetic-operators-in-c)
  - [Example Code](#example-code)
  - [Explanation of `Console.ReadKey()`](#explanation-of-consolereadkey)
  - [Key Takeaways](#key-takeaways)

---

## Introduction
Arithmetic operations are the foundation of many programs, enabling you to perform calculations, process data, and automate tasks. In C#, arithmetic is straightforward and intuitive.

---

## Performing Basic Arithmetic
C# uses standard arithmetic operators to perform mathematical operations. These operators work with numerical data types like `int`, `double`, and `float`.

---

## Arithmetic Operators in C#
Here are the primary arithmetic operators in C#:

- **Addition (`+`)** – Adds two numbers.
- **Subtraction (`-`)** – Subtracts one number from another.
- **Multiplication (`*`)** – Multiplies two numbers.
- **Division (`/`)** – Divides one number by another.
- **Modulus (`%`)** – Returns the remainder from division.

**Example:**
```csharp
int a = 10;
int b = 3;

Console.WriteLine("Addition: " + (a + b));  // Outputs: 13
Console.WriteLine("Subtraction: " + (a - b));  // Outputs: 7
Console.WriteLine("Multiplication: " + (a * b));  // Outputs: 30
Console.WriteLine("Division: " + (a / b));  // Outputs: 3
Console.WriteLine("Modulus: " + (a % b));  // Outputs: 1
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
            // Basic arithmetic examples
            int x = 15;
            int y = 4;

            Console.WriteLine("x + y = " + (x + y));
            Console.WriteLine("x - y = " + (x - y));
            Console.WriteLine("x * y = " + (x * y));
            Console.WriteLine("x / y = " + (x / y));
            Console.WriteLine("x % y = " + (x % y));

            Console.ReadKey();  // Waits for a key press
        }
    }
}
```

---

## Explanation of `Console.ReadKey()`
`Console.ReadKey()` waits for the user to press any key before the console window closes. This helps keep the console window open to view the output of arithmetic operations.

**Example:**
```csharp
Console.WriteLine("Press any key to continue...");
Console.ReadKey();
```

---

## Key Takeaways
- Basic arithmetic in C# uses familiar operators like `+`, `-`, `*`, `/`, and `%`.
- Arithmetic operations are performed using standard mathematical rules.
- `Console.ReadKey()` pauses the program, ensuring you can see the results.



