# Understanding Lists of Objects in C#

This guide explains how to create and use **lists of objects** in C#. Lists of objects allow you to group instances of a class in a dynamic and flexible data structure. This is particularly useful when working with collections of data.

---

## Table of Contents
- [Understanding Lists of Objects in C#](#understanding-lists-of-objects-in-c)
  - [Table of Contents](#table-of-contents)
  - [Introduction](#introduction)
  - [Example Code](#example-code)
  - [Key Concepts](#key-concepts)
    - [What is a List of Objects?](#what-is-a-list-of-objects)
    - [Adding Objects to a List](#adding-objects-to-a-list)
    - [Iterating Through a List of Objects](#iterating-through-a-list-of-objects)
    - [Customizing Object Output with ToString](#customizing-object-output-with-tostring)
    - [Expected Output:](#expected-output)
  - [Conclusion](#conclusion)

---

## Introduction
A **list of objects** in C# is a collection of instances of a class. This allows you to dynamically manage and manipulate multiple objects. Lists are part of the `System.Collections.Generic` namespace and provide flexible operations such as adding, removing, and iterating through items.

---

## Example Code
Here’s an example to demonstrate creating and using a list of objects in C#:

```csharp
using System;
using System.Collections.Generic;

namespace ConsoleApp1
{
    class Program
    {
        static void Main(string[] args)
        {
            // Creating a list of Player objects
            List<Player> players = new List<Player>();

            // Creating Player instances
            Player player1 = new Player("Abdi");
            Player player2 = new Player("John");
            Player player3 = new Player("Matt");

            // Adding players to the list
            players.Add(player1);
            players.Add(player2);
            players.Add(player3);

            // Iterating through the list and displaying each player
            foreach (Player player in players)
            {
                Console.WriteLine(player);
            }

            Console.ReadKey();
        }
    }

    // Player class definition
    class Player
    {
        public string Username { get; }

        public Player(string username)
        {
            Username = username;
        }

        // Overriding ToString to customize output
        public override string ToString()
        {
            return Username;
        }
    }
}
```

---

## Key Concepts

### What is a List of Objects?
A **list of objects** is a collection of instances of a class stored in a `List<T>`, where `T` is the type of the objects (e.g., `Player` in this example). This allows you to manage multiple objects dynamically in a single data structure.

### Adding Objects to a List
Objects can be added to a list using the `Add` method:
```csharp
Player player1 = new Player("Abdi");
players.Add(player1);
```
This adds the `Player` object `player1` to the list.

### Iterating Through a List of Objects
You can iterate through a list of objects using a `foreach` loop:
```csharp
foreach (Player player in players)
{
    Console.WriteLine(player);
}
```
This displays each object in the list.

### Customizing Object Output with ToString
The `ToString` method is overridden in the `Player` class to return the `Username` property:
```csharp
public override string ToString()
{
    return Username;
}
```
This ensures that when a `Player` object is displayed (e.g., using `Console.WriteLine`), the `Username` is printed instead of the default type information.

---
### Expected Output:
```
Abdi
John
Matt
```

---

## Conclusion
Using lists of objects in C# is a flexible and powerful way to manage collections of data. By combining the dynamic nature of lists with class instances, you can create scalable and maintainable code. 
