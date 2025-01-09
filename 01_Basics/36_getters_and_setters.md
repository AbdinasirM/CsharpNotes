# Understanding Getters and Setters in C#

This guide explains the concept of **getters and setters** in C#, their role in encapsulation, and how to implement them using properties. Getters and setters add security and control to class fields by providing controlled access.

---

## Table of Contents
- [Understanding Getters and Setters in C#](#understanding-getters-and-setters-in-c)
  - [Table of Contents](#table-of-contents)
  - [Introduction](#introduction)
  - [Example Code](#example-code)
  - [Key Concepts](#key-concepts)
    - [What are Getters and Setters?](#what-are-getters-and-setters)
    - [Properties in C#](#properties-in-c)
    - [Encapsulation and Security](#encapsulation-and-security)
    - [Using the `value` Keyword](#using-the-value-keyword)
    - [Expected Output:](#expected-output)
  - [Conclusion](#conclusion)

---

## Introduction
Getters and setters in C# are part of the concept of **properties**, which combine aspects of fields and methods. They provide a way to encapsulate the fields of a class, controlling how they are accessed and modified. This is a cornerstone of object-oriented programming principles like encapsulation and data hiding.

---

## Example Code
Here’s an example demonstrating how getters and setters work in C#:

```csharp
using System;

namespace ConsoleApp1
{
    class Program
    {
        static void Main(string[] args)
        {
            // Creating a Car object with an initial speed
            Car car = new Car(50);

            // Using the setter to modify the speed
            car.Speed = 750; // The setter limits the value to 500

            // Using the getter to retrieve the speed
            Console.WriteLine(car.Speed); // Output: 500

            Console.ReadKey();
        }
    }

    // Car class definition
    class Car
    {
        private int speed; // Private field

        public Car(int speed)
        {
            Speed = speed; // Use the property to set the initial value
        }

        // Property to get and set the speed
        public int Speed
        {
            get { return speed; } // Getter: retrieves the value of speed
            set
            {
                // Setter: assigns a value to speed, with validation
                if (value > 500)
                {
                    speed = 500; // Limit the maximum speed to 500
                }
                else
                {
                    speed = value;
                }
            }
        }
    }
}
```

---

## Key Concepts

### What are Getters and Setters?
- **Getters**: Accessors used to retrieve the value of a property.
- **Setters**: Accessors used to assign a value to a property. 

Getters and setters are often paired in a **property**, providing controlled access to private fields.

### Properties in C#
A **property** is a construct in C# that combines methods (get and set) with a field. It has:
- A **get accessor** to read the property value.
- A **set accessor** to assign a new value to the property.

Example:
```csharp
public int Speed
{
    get { return speed; }
    set { speed = value; }
}
```

### Encapsulation and Security
Encapsulation is the practice of hiding internal details and controlling access to them. By making fields private and using properties, you can:
- Prevent unauthorized access or modification.
- Add validation logic (e.g., limiting the range of values).

In the example:
- The `speed` field is private.
- The `Speed` property enforces a maximum speed of 500 using validation logic in the setter.

### Using the `value` Keyword
In a setter, the `value` keyword represents the value being assigned to the property:
```csharp
set { speed = value; }
```
In the example, the setter checks if `value` exceeds 500 and adjusts it accordingly:
```csharp
set
{
    if (value > 500)
    {
        speed = 500;
    }
    else
    {
        speed = value;
    }
}
```

---
### Expected Output:
```
500
```

---

## Conclusion
Getters and setters in C# provide a secure and controlled way to access and modify class fields. By using properties, you can enforce validation, ensure data integrity, and maintain encapsulation in your programs.