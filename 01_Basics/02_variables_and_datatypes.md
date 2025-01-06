# C# Basics - Variables, Data Types, and Constants

Welcome to this introduction to variables, data types, and constants in C#! This guide explains the concept of variables, their declaration and initialization, key data types used in C#, and the role of constants.

## Table of Contents
1. [Introduction](#introduction)
2. [Understanding Variables](#understanding-variables)
3. [Variable Declaration and Initialization](#variable-declaration-and-initialization)
4. [Data Types in C#](#data-types-in-c)
5. [Constants in C#](#constants-in-c)
6. [Example Code](#example-code)
7. [Explanation of `Console.ReadKey()`](#explanation-of-consolereadkey)

---

## Introduction
Variables and constants are essential in programming as they store data that can be used and manipulated throughout the program. This section provides an overview of how variables, data types, and constants work in C#.

---

## Understanding Variables
Variables allow you to store and reuse data in your program. To use a variable in C#, it must be declared (specifying its type) and initialized (assigning a value).

### Key Concepts
- **Declaration**: Telling the program the type of data a variable will hold.
- **Initialization**: Assigning a value to a declared variable.

---

## Variable Declaration and Initialization
### Separate Declaration and Initialization
```csharp
int age;  // Declaration
age = 100;  // Initialization
Console.WriteLine(age);  // Outputs: 100
```

### Combined Declaration and Initialization
```csharp
int number = 42;  // Declaring and initializing in one step
Console.WriteLine(number);  // Outputs: 42
```

---

## Data Types in C#
C# provides various data types to store different kinds of information. Here are some of the most commonly used types:

### Numeric Types
- **`int`** – Represents integer values (whole numbers).
- **`double`** – Represents floating-point numbers (decimals).

### Boolean Type
- **`bool`** – Represents true or false values.

### Character Type
- **`char`** – Represents a single character.

### String Type
- **`string`** – Represents a sequence of characters (text).

**Example:**
```csharp
int count = 10;
double price = 9.99;
bool isAvailable = true;
char grade = 'A';
string name = "John";

Console.WriteLine(name + " has grade " + grade);
```

---

## Constants in C#
Constants are values that cannot be changed during the program's execution. They are initialized at compile time and remain the same throughout the life of the program. 

### Declaration and Initialization of Constants
```csharp
const double pi = 3.14;  // Constant declaration and initialization
Console.WriteLine(pi);  // Outputs: 3.14
```

### Key Points about Constants
- Use the `const` keyword to declare a constant.
- Constants must be initialized at the time of declaration.
- Constants cannot be modified later in the program.

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
            // Variable examples
            int age;  // Declaration
            age = 100;  // Initialization
            Console.WriteLine(age);  // Outputs: 100

            int number = 42;  // Combined declaration and initialization
            Console.WriteLine(number);

            double price = 19.95;
            bool isHappy = true;
            char initial = 'C';
            string message = "Hello, C#";
            
            Console.WriteLine(message);
            
            // Constant example
            const double pi = 3.14;
            Console.WriteLine(pi);  // Outputs: 3.14

            Console.ReadKey();  // Waits for a key press
        }
    }
}
```

---

## Explanation of `Console.ReadKey()`
`Console.ReadKey()` waits for the user to press any key before the console window closes. This is useful for keeping the output visible after program execution.

**Example:**
```csharp
Console.WriteLine("Press any key to continue...");
Console.ReadKey();  // Pauses the program until a key is pressed
```

---

## Key Takeaways
- Variables must be declared with a data type before use.
- Initialization can be done at the time of declaration or separately.
- C# supports various data types such as `int`, `double`, `bool`, `char`, and `string`.
- Constants are declared using the `const` keyword and cannot be changed after initialization.
- `Console.ReadKey()` prevents the console from closing immediately.


