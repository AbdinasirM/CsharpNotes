# Understanding Polymorphism in C#

This guide explains the concept of **polymorphism** in C#. Polymorphism allows objects to be identified and used as instances of their parent type, enabling flexibility and extensibility in object-oriented programming.

---

## Table of Contents
- [Understanding Polymorphism in C#](#understanding-polymorphism-in-c)
  - [Table of Contents](#table-of-contents)
  - [Introduction](#introduction)
  - [Example Code](#example-code)
  - [Key Concepts](#key-concepts)
    - [What is Polymorphism?](#what-is-polymorphism)
    - [Using Polymorphism in C#](#using-polymorphism-in-c)
    - [Virtual and Override Keywords](#virtual-and-override-keywords)
      - [Example:](#example)
    - [Expected Output:](#expected-output)
  - [Conclusion](#conclusion)

---

## Introduction
Polymorphism is a core concept of object-oriented programming. The word "polymorphism" comes from Greek, meaning "many forms." In C#, polymorphism allows objects of a derived class to be treated as objects of their base class. This capability is especially useful in scenarios like collections of mixed objects or when implementing behavior that varies by object type.

---

## Example Code
Here is an example to demonstrate polymorphism:

```csharp
using System;

namespace ConsoleApp1
{
    class Program
    {
        static void Main(string[] args)
        {
            // Creating instances of derived classes
            Car car = new Car();
            Bicycle bicycle = new Bicycle();
            Boat boat = new Boat();

            // Array of base class type holding derived class objects
            Vehicle[] myVehicles = { car, bicycle, boat };

            // Using polymorphism to call the overridden Go method
            foreach (Vehicle vehicle in myVehicles)
            {
                vehicle.Go();
            }

            Console.ReadKey();
        }
    }

    // Base class
    class Vehicle
    {
        public virtual void Go()
        {
            Console.WriteLine("The vehicle is moving!");
        }
    }

    // Derived class: Car
    class Car : Vehicle
    {
        public override void Go()
        {
            Console.WriteLine("The car is moving!");
        }
    }

    // Derived class: Bicycle
    class Bicycle : Vehicle
    {
        public override void Go()
        {
            Console.WriteLine("The bicycle is moving!");
        }
    }

    // Derived class: Boat
    class Boat : Vehicle
    {
        public override void Go()
        {
            Console.WriteLine("The boat is moving!");
        }
    }
}
```

---

## Key Concepts

### What is Polymorphism?
Polymorphism allows an object to be referenced by multiple types:
- A `Car` is a `Vehicle`.
- A `Bicycle` is a `Vehicle`.
- A `Boat` is a `Vehicle`.

This flexibility allows you to use derived class objects in situations where the base class type is expected, enabling clean and scalable code.

### Using Polymorphism in C#
In the example, an array of `Vehicle` objects (`myVehicles`) holds objects of the derived classes `Car`, `Bicycle`, and `Boat`. The `foreach` loop iterates through this array and calls the `Go` method on each object.

Since the `Go` method is overridden in each derived class, the specific implementation for each object is executed, demonstrating polymorphism.

### Virtual and Override Keywords
- **`virtual`:** Used in the base class to mark a method as "overridable."
- **`override`:** Used in the derived class to provide a specific implementation of the base class method.

#### Example:
```csharp
class Vehicle
{
    public virtual void Go()
    {
        Console.WriteLine("The vehicle is moving!");
    }
}

class Car : Vehicle
{
    public override void Go()
    {
        Console.WriteLine("The car is moving!");
    }
}
```

---


### Expected Output:
```
The car is moving!
The bicycle is moving!
The boat is moving!
```

---

## Conclusion
Polymorphism is a powerful feature of object-oriented programming that simplifies code and enables flexible designs. By leveraging base class references and overriding methods, you can create extensible and maintainable applications.

