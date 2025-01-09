# Understanding Method Overriding in C#

This guide explains the concept of **method overriding** in C# and how it allows derived classes to provide specific implementations of methods defined in their base classes. This is an essential feature for implementing polymorphism.

---

## Table of Contents
- [Understanding Method Overriding in C#](#understanding-method-overriding-in-c)
  - [Table of Contents](#table-of-contents)
  - [Introduction](#introduction)
  - [Example Code](#example-code)
  - [Key Concepts](#key-concepts)
    - [What is Method Overriding?](#what-is-method-overriding)
    - [Using the `virtual` and `override` Keywords](#using-the-virtual-and-override-keywords)
      - [Example:](#example)
    - [Polymorphism in Action](#polymorphism-in-action)
      - [Example:](#example-1)
  - [Conclusion](#conclusion)

---

## Introduction
Method overriding in C# allows a subclass to provide a specific implementation for a method that is already defined in its base class. This is particularly useful when designing systems with polymorphism, enabling different behavior for the same method across different subclasses.

---

## Example Code
Here is the example code to demonstrate method overriding:

```csharp
using System;

namespace ConsoleApp1
{
    class Program
    {
        static void Main(string[] args)
        {
            // Creating instances of Dog and Cat
            Dog dog = new Dog();
            Cat cat = new Cat();

            // Calling the overridden Speak method
            dog.Speak();
            cat.Speak();

            Console.ReadKey();
        }
    }

    // Base class
    class Animal
    {
        public virtual void Speak()
        {
            Console.WriteLine("The animal goes *brr*");
        }
    }

    // Derived class: Dog
    class Dog : Animal
    {
        public override void Speak()
        {
            Console.WriteLine("The dog goes *Woof woof!*");
        }
    }

    // Derived class: Cat
    class Cat : Animal
    {
        public override void Speak()
        {
            Console.WriteLine("The cat goes *Meow!*");
        }
    }
}
```

---

## Key Concepts

### What is Method Overriding?
Method overriding allows a derived class to replace or modify the implementation of a method inherited from a base class. This is done by using the `override` keyword in the derived class.

To override a method:
1. The base class method must be marked with the `virtual`, `abstract`, or `override` keyword.
2. The derived class method must use the `override` keyword.

### Using the `virtual` and `override` Keywords
- **`virtual`:** Used in the base class to indicate that a method can be overridden in derived classes.
- **`override`:** Used in the derived class to provide a new implementation for a virtual method.

#### Example:
```csharp
class Animal
{
    public virtual void Speak()
    {
        Console.WriteLine("The animal goes *brr*");
    }
}

class Dog : Animal
{
    public override void Speak()
    {
        Console.WriteLine("The dog goes *Woof woof!*");
    }
}
```

### Polymorphism in Action
Polymorphism allows us to treat objects of derived classes as objects of the base class. This means we can call the same method on different types of objects and get behavior specific to their types.

#### Example:
```csharp
Animal animal1 = new Dog();
animal1.Speak(); // Output: The dog goes *Woof woof!*

Animal animal2 = new Cat();
animal2.Speak(); // Output: The cat goes *Meow!*
```

---

## Conclusion
Method overriding is a cornerstone of object-oriented programming in C#. It allows derived classes to provide specific implementations of methods defined in base classes, enabling polymorphism and more flexible designs.