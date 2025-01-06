# C# Basics - If Statements

Welcome to this introduction to if statements in C#! This guide explains how to use conditional logic to make decisions in your programs.

## Table of Contents
- [C# Basics - If Statements](#c-basics---if-statements)
  - [Table of Contents](#table-of-contents)
  - [Introduction](#introduction)
  - [Understanding If Statements](#understanding-if-statements)
    - [Operators Often Used in If Statements](#operators-often-used-in-if-statements)
  - [Example Code](#example-code)
  - [Explanation of `Console.ReadKey()`](#explanation-of-consolereadkey)
  - [Key Takeaways](#key-takeaways)

---

## Introduction
If statements are essential for decision-making in programming. They allow the program to execute different blocks of code based on specific conditions.

---

## Understanding If Statements
In C#, if statements check conditions and execute code blocks based on whether the condition evaluates to true or false. The structure can include:
- `if` – Executes a block if the condition is true.
- `else if` – Checks another condition if the previous one is false.
- `else` – Executes a block if no preceding conditions are true.

### Operators Often Used in If Statements
- **`==`** – Equal to
- **`!=`** – Not equal to
- **`>`** – Greater than
- **`<`** – Less than
- **`>=`** – Greater than or equal to
- **`<=`** – Less than or equal to
- **`&&`** – Logical AND
- **`||`** – Logical OR

**Example:**
```csharp
int age;
Console.WriteLine("How old are you?");
age = Convert.ToInt32(Console.ReadLine());

if (age >= 18 && age <= 64)
{
    Console.WriteLine("You are an adult!");
}
else if (age >= 65)
{
    Console.WriteLine("You are a senior citizen");
}
else if (age < 0)
{
    Console.WriteLine("You haven't been born yet");
}
else
{
    Console.WriteLine("You are under age and not an adult!");
}
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
            // If statements
            int age;
            Console.WriteLine("How old are you?");
            age = Convert.ToInt32(Console.ReadLine());

            if (age >= 18 && age <= 64)
            {
                Console.WriteLine("You are an adult!");
            }
            else if (age >= 65)
            {
                Console.WriteLine("You are a senior citizen");
            }
            else if (age < 0)
            {
                Console.WriteLine("You haven't been born yet");
            }
            else
            {
                Console.WriteLine("You are under age and not an adult!");
            }

            Console.ReadKey();  // Waits for a key press
        }
    }
}
```

---

## Explanation of `Console.ReadKey()`
`Console.ReadKey()` pauses the program until the user presses any key. This ensures the console remains open long enough for the user to read the output.

**Example:**
```csharp
Console.WriteLine("Press any key to continue...");
Console.ReadKey();
```

---

## Key Takeaways
- If statements control program flow by executing code blocks based on conditions.
- Logical operators like `&&` (AND) and `||` (OR) can combine multiple conditions.
- `Console.ReadKey()` prevents the console from closing immediately after execution.