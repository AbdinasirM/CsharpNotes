# C# Basics - Switch Statements

Welcome to this introduction to switch statements in C#! This guide explains how to use switch statements to simplify complex conditional logic in your programs.

## Table of Contents
- [C# Basics - Switch Statements](#c-basics---switch-statements)
  - [Table of Contents](#table-of-contents)
  - [Introduction](#introduction)
  - [Understanding Switch Statements](#understanding-switch-statements)
    - [Key Points](#key-points)
    - [Example with Switch](#example-with-switch)
  - [Example Code](#example-code)
  - [Explanation of `Console.ReadKey()`](#explanation-of-consolereadkey)
  - [Key Takeaways](#key-takeaways)

---

## Introduction
Switch statements provide a clean and efficient way to evaluate multiple conditions without writing long if-else chains. They improve code readability and performance in scenarios where multiple outcomes are possible.

---

## Understanding Switch Statements
A switch statement tests a variable against multiple possible values (cases) and executes the corresponding block when a match is found. The `default` block runs if no case matches.

### Key Points
- `case` blocks must end with `break` to prevent fall-through (executing the next case).
- The `default` case handles unmatched conditions.
- Complex conditions require `when` for evaluation.

### Example with Switch
```csharp
int age;
Console.WriteLine("How old are you?");
age = Convert.ToInt32(Console.ReadLine());

switch (age)
{
    case int n when (n >= 18 && n <= 64):
        Console.WriteLine("You are an adult!");
        break;
    case int n when (n >= 65):
        Console.WriteLine("You are a senior citizen");
        break;
    case int n when (n < 0):
        Console.WriteLine("You haven't been born yet");
        break;
    default:
        Console.WriteLine("You are under age and not an adult!");
        break;
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
            // Switch statements
            int age;
            Console.WriteLine("How old are you?");
            age = Convert.ToInt32(Console.ReadLine());

            switch (age)
            {
                case int n when (n >= 18 && n <= 64):
                    Console.WriteLine("You are an adult!");
                    break;
                case int n when (n >= 65):
                    Console.WriteLine("You are a senior citizen");
                    break;
                case int n when (n < 0):
                    Console.WriteLine("You haven't been born yet");
                    break;
                default:
                    Console.WriteLine("You are under age and not an adult!");
                    break;
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
- Switch statements simplify complex conditional logic.
- Use `when` in `case` blocks to handle conditions.
- `Console.ReadKey()` prevents the console from closing immediately after execution.