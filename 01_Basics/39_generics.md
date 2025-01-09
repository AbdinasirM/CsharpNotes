# Understanding Generics in C#

This guide explains **generics** in C#, their purpose, and how they enable code reusability across multiple data types. Generics are a powerful feature for writing flexible and type-safe code.

---

## Table of Contents
- [Understanding Generics in C#](#understanding-generics-in-c)
  - [Table of Contents](#table-of-contents)
  - [Introduction](#introduction)
  - [Example Code](#example-code)
  - [Key Concepts](#key-concepts)
    - [What are Generics?](#what-are-generics)
      - [Example:](#example)
    - [Benefits of Generics](#benefits-of-generics)
    - [Using Generics in Methods](#using-generics-in-methods)
    - [Generic Classes](#generic-classes)
    - [Expected Output:](#expected-output)
  - [Conclusion](#conclusion)

---

## Introduction
**Generics** in C# allow you to define classes, methods, and other structures that work with any data type without sacrificing type safety. They help eliminate code duplication by providing a template for operations that can work with multiple types.

---

## Example Code
Here’s an example demonstrating how to use generics in C#:

```csharp
using System;

namespace ConsoleApp1
{
    class Program
    {
        static void Main(string[] args)
        {
            // Without generics: separate code for each data type
            int[] intArray = { 1, 2, 3, 4 };
            double[] doubleArray = { 5.1, 3.4, 6.2, 6.7 };
            string[] stringArray = { "lion", "fox", "monkey" };

            // Using generics to display elements of different arrays
            displayElements<int>(intArray);
            displayElements<string>(stringArray);
            displayElements<double>(doubleArray);

            Console.ReadKey();
        }

        // Generic method to display elements of an array
        public static void displayElements<T>(T[] array)
        {
            foreach (T item in array)
            {
                Console.Write(item + " ");
            }
            Console.WriteLine();
        }
    }
}
```

---

## Key Concepts

### What are Generics?
Generics allow you to define methods, classes, interfaces, and delegates that can operate on any data type. By adding `<T>` (or other placeholder names) to a declaration, you make it generic.

#### Example:
```csharp
public static void displayElements<T>(T[] array)
{
    foreach (T item in array)
    {
        Console.Write(item + " ");
    }
    Console.WriteLine();
}
```
Here, `<T>` is a type parameter that can be replaced with any type when the method is called.

### Benefits of Generics
1. **Code Reusability:** Write a single method or class that works for multiple types.
2. **Type Safety:** Catch type-related errors at compile-time.
3. **Performance:** Avoid boxing and unboxing for value types, leading to better performance.

### Using Generics in Methods
You can use generics in methods to perform operations on various types:
```csharp
public static void displayElements<T>(T[] array)
{
    foreach (T item in array)
    {
        Console.Write(item + " ");
    }
    Console.WriteLine();
}
```
When calling the method, specify the type:
```csharp
displayElements<int>(intArray);
displayElements<string>(stringArray);
```
The compiler ensures type safety, so passing incompatible types will result in an error.

### Generic Classes
Generics can also be applied to classes:
```csharp
public class Box<T>
{
    public T Value { get; set; }

    public Box(T value)
    {
        Value = value;
    }

    public void Display()
    {
        Console.WriteLine("Value: " + Value);
    }
}
```
Usage:
```csharp
Box<int> intBox = new Box<int>(123);
intBox.Display(); // Output: Value: 123

Box<string> stringBox = new Box<string>("Hello");
stringBox.Display(); // Output: Value: Hello
```

---

### Expected Output:
```
1 2 3 4 
lion fox monkey 
5.1 3.4 6.2 6.7 
```

---

## Conclusion
Generics in C# enable flexible, reusable, and type-safe code. They reduce duplication by allowing a single method or class to work with multiple types.
