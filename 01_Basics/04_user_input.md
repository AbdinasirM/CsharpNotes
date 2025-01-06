# C# Basics - User Input

Welcome to this introduction to handling user input in C#! This guide explains how to capture and use input from users through the console.

## Table of Contents
- [C# Basics - User Input](#c-basics---user-input)
  - [Table of Contents](#table-of-contents)
  - [Introduction](#introduction)
  - [Capturing User Input](#capturing-user-input)
  - [Converting Input to Other Types](#converting-input-to-other-types)
  - [Example Code](#example-code)
  - [Explanation of `Console.ReadKey()`](#explanation-of-consolereadkey)
  - [Key Takeaways](#key-takeaways)

---

## Introduction
User input is a fundamental part of many programs, allowing users to interact with the application by providing data that the program processes.

---

## Capturing User Input
To get input from the user in C#, you use the `Console.ReadLine()` method. This method waits for the user to type something and press Enter.

**Example:**
```csharp
Console.Write("What is your name: ");
string name = Console.ReadLine();
Console.WriteLine("Hello " + name);
```
- `Console.Write()` displays a prompt without adding a newline.
- `Console.ReadLine()` captures the user's input as a string.

---

## Converting Input to Other Types
User input from `Console.ReadLine()` is always treated as a string. To convert it to another type, such as an integer, you can use the `Convert` class.

**Example:**
```csharp
int age;
Console.WriteLine("How old are you?");
age = Convert.ToInt32(Console.ReadLine());  // Convert input to int
Console.WriteLine("You are " + age + " years old");
```

- `Convert.ToInt32()` changes the string input to an integer.
- Be cautious; if the user inputs non-numeric data, the program will throw an error.

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
            // Getting user input
            int age;

            Console.WriteLine("How old are you?");
            age = Convert.ToInt32(Console.ReadLine());
            Console.WriteLine("You are " + age + " years old");

            Console.ReadKey();  // Waits for a key press
        }
    }
}
```

---

## Explanation of `Console.ReadKey()`
`Console.ReadKey()` pauses the program until the user presses a key. This prevents the console window from closing immediately after execution, allowing you to view the output.

**Example:**
```csharp
Console.WriteLine("Press any key to continue...");
Console.ReadKey();
```

---

## Key Takeaways
- Use `Console.ReadLine()` to capture user input.
- Always convert input when necessary to match the desired data type.
- `Console.ReadKey()` keeps the console window open until a key is pressed.
