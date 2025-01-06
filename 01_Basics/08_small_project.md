# C# Basics - Calculating the Hypotenuse of a Triangle

Welcome to this small project on calculating the hypotenuse of a triangle in C#! This guide walks you through building a simple program to compute the hypotenuse using the Pythagorean theorem.

## Table of Contents
- [C# Basics - Calculating the Hypotenuse of a Triangle](#c-basics---calculating-the-hypotenuse-of-a-triangle)
  - [Table of Contents](#table-of-contents)
  - [Introduction](#introduction)
  - [Understanding the Pythagorean Theorem](#understanding-the-pythagorean-theorem)
  - [Example Code](#example-code)
  - [Explanation of `Console.ReadKey()`](#explanation-of-consolereadkey)
  - [Key Takeaways](#key-takeaways)

---

## Introduction
Calculating the hypotenuse of a right-angled triangle is a common mathematical task. This project uses basic arithmetic, user input, and the `Math` class in C# to compute the hypotenuse.

---

## Understanding the Pythagorean Theorem
The Pythagorean theorem states:

**c² = a² + b²**

Where:
- `c` is the hypotenuse.
- `a` and `b` are the two sides of the triangle.

To find the hypotenuse:

**c = sqrt(a² + b²)**

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
            // Calculate the hypotenuse of a triangle
            int a, b;
            
            Console.WriteLine("Enter the value for side A");
            a = Convert.ToInt32(Console.ReadLine());
            
            Console.WriteLine("Enter the value for side B");
            b = Convert.ToInt32(Console.ReadLine());

            double c = Math.Sqrt((a * a) + (b * b));
            Console.WriteLine("The hypotenuse of the triangle with Side A= " + a + " and Side B= " + b + " is " + c);

            Console.ReadKey();  // Waits for a key press
        }
    }
}
```

---

## Explanation of `Console.ReadKey()`
`Console.ReadKey()` pauses the program until the user presses any key. This ensures the result stays visible in the console window after execution.

**Example:**
```csharp
Console.WriteLine("Press any key to continue...");
Console.ReadKey();
```

---

## Key Takeaways
- This project demonstrates basic input handling and mathematical operations in C#.
- The `Math.Sqrt` method calculates the square root.
- `Console.ReadKey()` prevents the console window from closing immediately after execution.
