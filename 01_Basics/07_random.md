# C# Basics - Random Numbers

Welcome to this introduction to generating random numbers in C#! This guide explains how to create random numbers and provides simple examples to help you **get** started.

## Table of Contents
- [C# Basics - Random Numbers](#c-basics---random-numbers)
  - [Table of Contents](#table-of-contents)
  - [Introduction](#introduction)
  - [Generating Random Numbers](#generating-random-numbers)
    - [Key Methods](#key-methods)
  - [Example Code](#example-code)
  - [Explanation of `Console.ReadKey()`](#explanation-of-consolereadkey)
  - [Key Takeaways](#key-takeaways)

---

## Introduction
Generating random numbers is essential for many applications, from games to simulations. C# provides the `Random` class to generate random values easily.

---

## Generating Random Numbers
To generate random numbers, you can use the `Random` class. By creating an instance of `Random`, you can call methods to produce random integers, doubles, or bytes.

### Key Methods
- **`Next()`** – Returns a non-negative random integer.
- **`Next(max)`** – Returns a random integer between 0 and `max` (exclusive).
- **`Next(min, max)`** – Returns a random integer between `min` (inclusive) and `max` (exclusive).
- **`NextDouble()`** – Returns a random floating-point number between 0.0 and 1.0.

**Example:**
```csharp
Random random = new Random();
int num = random.Next(1, 7);  // Generates a random number between 1 and 6
Console.WriteLine(num);
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
            // Generating random numbers
            Random random = new Random();
            int num = random.Next(1, 7);  // Generates a number between 1 and 6
            Console.WriteLine(num);

            Console.ReadKey();  // Waits for a key press
        }
    }
}
```

---

## Explanation of `Console.ReadKey()`
`Console.ReadKey()` waits for the user to press any key before the console window closes. This allows the user to view the random number before the program exits.

**Example:**
```csharp
Console.WriteLine("Press any key to continue...");
Console.ReadKey();
```

---

## Key Takeaways
- Use the `Random` class to generate random numbers in C#.
- `Next(min, max)` generates integers within a specified range.
- `Console.ReadKey()` pauses the console, ensuring the output is visible until a key is pressed.
