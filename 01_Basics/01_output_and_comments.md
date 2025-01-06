# C# Basics - Output and Comments

Welcome to this brief introduction to output and comments in C#! This guide provides an easy-to-understand overview with simple examples.

## Table of Contents
- [C# Basics - Output and Comments](#c-basics---output-and-comments)
  - [Table of Contents](#table-of-contents)
  - [Introduction](#introduction)
  - [Comments in C#](#comments-in-c)
    - [Types of Comments](#types-of-comments)
  - [Output in C#](#output-in-c)
    - [Methods for Output](#methods-for-output)
  - [Example Code](#example-code)
  - [Explanation of `Console.ReadKey()`](#explanation-of-consolereadkey)
  - [Key Takeaways](#key-takeaways)

---

## Introduction
C# (pronounced "C-sharp") is a modern, object-oriented programming language developed by Microsoft. This guide covers how to produce output and write comments, two essential skills for any C# developer.

---

## Comments in C#
Comments are important as they help explain what your code does, making it easier to understand for you and others. They are ignored by the compiler and have no effect on program execution.

### Types of Comments
- **Single-line comment**: Use `//` for comments that occupy one line.
- **Multi-line comment**: Use `/* ... */` for comments that span multiple lines.

**Example:**
```csharp
// This is a single-line comment
/*
 This is a
 multi-line comment
*/
```

---

## Output in C#
Outputting text to the console is fundamental for interacting with users and debugging. C# provides several methods to print text to the console.

### Methods for Output
- `Console.WriteLine()`: Prints text and moves to the next line (like `print()` in Python).
- `Console.Write()`: Prints text without moving to the next line (like `end=""` in Python).

**Example:**
```csharp
Console.WriteLine("Hello, World!"); // Outputs and moves to the next line
Console.Write("Hello"); // Outputs without moving to the next line
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
            // Output and comments
            // Single-line comment
            /*
             Multi-line comment
             */

            // Output examples
            Console.WriteLine("Hello, World!");  // Output with newline
            Console.Write("Hello");             // Output without newline

            Console.ReadKey(); // Waits for a key press to exit
        }
    }
}
```

---

## Explanation of `Console.ReadKey()`
`Console.ReadKey()` is used to wait for the user to press a key before the console window closes. This is especially useful when running console applications because it prevents the program from closing immediately after execution.

**Example:**
```csharp
Console.WriteLine("Press any key to exit...");
Console.ReadKey(); // Waits until a key is pressed
```

---

## Key Takeaways
- Use `//` for single-line comments and `/* */` for multi-line comments.
- `Console.WriteLine()` outputs text with a newline, while `Console.Write()` does not.
- `Console.ReadKey()` pauses the program until a key is pressed, preventing the console from closing immediately.


