# Understanding Objects as Arguments in C#

This guide explains the concept of using objects as arguments in C#, using practical examples to demonstrate how objects can be passed to methods, modified, and copied.

---

## Table of Contents
- [Understanding Objects as Arguments in C#](#understanding-objects-as-arguments-in-c)
  - [Table of Contents](#table-of-contents)
  - [Introduction](#introduction)
  - [Example Code](#example-code)
  - [Key Concepts](#key-concepts)
    - [Passing Objects as Arguments](#passing-objects-as-arguments)
    - [Modifying Object Properties](#modifying-object-properties)
    - [Copying Objects](#copying-objects)
  - [Conclusion](#conclusion)

---

## Introduction
In C#, objects are passed by reference by default. This means that when an object is passed to a method, any changes made to the object inside the method will affect the original object. Additionally, you can create a new copy of an object to avoid altering the original.

---

## Example Code
Here is the example code to demonstrate the concept:

```csharp
using System;

namespace ConsoleApp1
{
    class Program
    {
        static void Main(string[] args)
        {
            // Creating a Car object
            Car car1 = new Car("Mustang", "Red");
            Console.WriteLine($"Original car: Model = {car1.model}, Color = {car1.color}");

            // Changing the color of the car
            ChangeColor(car1, "Blue");
            Console.WriteLine($"After ChangeColor: Model = {car1.model}, Color = {car1.color}");

            // Copying the car object
            Car car2 = CopyCarObject(car1);
            Console.WriteLine($"Copied car: Model = {car2.model}, Color = {car2.color}");

            Console.ReadKey();
        }

        // Method to change the color of the car
        public static void ChangeColor(Car car, string color)
        {
            car.color = color;
        }

        // Method to create a copy of the car object
        public static Car CopyCarObject(Car car)
        {
            return new Car(car.model, car.color);
        }
    }

    // Car class definition
    class Car 
    {
        public string model;
        public string color;

        public Car(string model, string color)
        {
            this.model = model;
            this.color = color;
        }
    }
}
```

---

## Key Concepts
### Passing Objects as Arguments
In the example, the `ChangeColor` method takes a `Car` object as an argument:

```csharp
public static void ChangeColor(Car car, string color)
{
    car.color = color;
}
```

When `car1` is passed to this method, its `color` property is updated directly because objects are passed by reference.

### Modifying Object Properties
By passing `car1` to `ChangeColor`, we effectively modify the original object:

```csharp
Car car1 = new Car("Mustang", "Red");
ChangeColor(car1, "Blue");
// car1.color is now "Blue"
```

### Copying Objects
The `CopyCarObject` method demonstrates how to create a new instance of an object with the same properties as the original:

```csharp
public static Car CopyCarObject(Car car)
{
    return new Car(car.model, car.color);
}
```

This ensures that changes to the new object do not affect the original.

---



## Conclusion
This example demonstrates how objects can be passed to methods in C# and how they can be modified or copied. Understanding this concept is crucial for effective object-oriented programming in C#.

