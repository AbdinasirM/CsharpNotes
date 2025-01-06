# C# Basics - String Methods

Welcome to this introduction to string methods in C#! This guide explains how to manipulate and work with strings using common methods available in C#.

## Table of Contents
- [C# Basics - String Methods](#c-basics---string-methods)
  - [Table of Contents](#table-of-contents)
  - [Introduction](#introduction)
  - [Common String Methods](#common-string-methods)
  - [Example Code](#example-code)
  - [Explanation of `Console.ReadKey()`](#explanation-of-consolereadkey)
  - [Key Takeaways](#key-takeaways)

---

## Introduction
Strings are a crucial part of programming, and C# offers numerous methods to manipulate and format strings easily. This guide covers frequently used string methods to perform tasks like changing case, replacing characters, and extracting substrings.

---

## Common String Methods
Here are some of the most commonly used string methods in C#:

- **`ToUpper()`** – Converts all characters in the string to uppercase.
- **`ToLower()`** – Converts all characters in the string to lowercase.
- **`Replace(oldChar, newChar)`** – Replaces all instances of `oldChar` with `newChar`. You can also replace a character with an empty string to remove it.
- **`Insert(index, value)`** – Inserts the specified string at a specified index position.
- **`Length`** – Returns the number of characters in the string.
- **`Substring(startIndex, length)`** – Extracts a substring from the string starting at `startIndex` for the specified `length`.
- **`Trim()`** – Removes all leading and trailing whitespace from the string.
- **`StartsWith(value)`** – Checks if the string starts with the specified substring and returns a boolean.
- **`EndsWith(value)`** – Checks if the string ends with the specified substring and returns a boolean.
- **`Contains(value)`** – Determines whether the string contains the specified substring.
- **`IndexOf(value)`** – Returns the index of the first occurrence of the specified substring.
- **`LastIndexOf(value)`** – Returns the index of the last occurrence of the specified substring.

**Example:**
```csharp
String full_name = "Abdi nasir";
String phone_number = "123-456-7890";

Console.WriteLine(full_name.ToUpper());  // ABDI NASIR
Console.WriteLine(full_name.ToLower());  // abdi nasir
Console.WriteLine(phone_number.Replace("-", ""));  // 1234567890

String user_name = (full_name.Replace(" ", "")).Insert(0, "@");
Console.WriteLine(user_name);  // @Abdinasir

Console.WriteLine(full_name.Length);  // 10

string first_name = full_name.Substring(0, 4);
Console.WriteLine(first_name);  // Abdi

string last_name = full_name.Substring(5, 5);
Console.WriteLine(last_name);  // nasir

Console.WriteLine(full_name.Trim());  // Removes extra spaces
Console.WriteLine(full_name.StartsWith("Ab"));  // True
Console.WriteLine(full_name.EndsWith("nasir"));  // True
Console.WriteLine(full_name.Contains("nas"));  // True
Console.WriteLine(full_name.IndexOf("n"));  // 5
Console.WriteLine(full_name.LastIndexOf("i"));  // 9
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
            // String methods
            String full_name = "Abdi nasir";
            String phone_number = "123-456-7890";

            Console.WriteLine(full_name.ToUpper());
            Console.WriteLine(full_name.ToLower());

            Console.WriteLine(phone_number.Replace("-", ""));

            String user_name = (full_name.Replace(" ", "")).Insert(0, "@");
            Console.WriteLine(user_name);

            Console.WriteLine(full_name.Length);

            string first_name = full_name.Substring(0, 4);
            Console.WriteLine(first_name);

            string last_name = full_name.Substring(5, 5);
            Console.WriteLine(last_name);

            Console.WriteLine(full_name.Trim());
            Console.WriteLine(full_name.StartsWith("Ab"));
            Console.WriteLine(full_name.EndsWith("nasir"));
            Console.WriteLine(full_name.Contains("nas"));
            Console.WriteLine(full_name.IndexOf("n"));
            Console.WriteLine(full_name.LastIndexOf("i"));

            Console.ReadKey();  // Waits for a key press
        }
    }
}
```

---

## Explanation of `Console.ReadKey()`
`Console.ReadKey()` pauses the program until the user presses any key. This helps keep the console window open so the user can see the output.

**Example:**
```csharp
Console.WriteLine("Press any key to continue...");
Console.ReadKey();
```

---

## Key Takeaways
- String methods in C# make it easy to manipulate and format text.
- Methods like `ToUpper()`, `Replace()`, `Trim()`, and `Substring()` are useful for various tasks.
- `Console.ReadKey()` ensures the console remains open until a key is pressed.