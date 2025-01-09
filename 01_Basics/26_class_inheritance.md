# Abstract Classes in C#

This guide explains the concept of abstract classes in C#, provides examples, and ensures essential concepts are clearly understood.

---

## What is an Abstract Class?
An **abstract class** is a class that cannot be instantiated and serves as a blueprint for other classes. It may contain:
- Fully implemented methods.
- Abstract methods that are declared without implementation.

Abstract classes are used to provide a common base for derived classes while ensuring that certain methods or properties must be implemented in the derived classes.

### Key Features:
1. **Cannot Instantiate**: You cannot create objects of an abstract class.
2. **May Contain Abstract Methods**: These methods have no implementation in the abstract class and must be implemented in derived classes.
3. **Can Contain Regular Members**: Abstract classes can also contain implemented methods, fields, and properties.

---

## Example Code
### Abstract Class with Fully Implemented and Abstract Methods

```csharp
using System;

namespace ConsoleApp1
{
    class Program
    {
        static void Main(string[] args)
        {
            // Cannot instantiate the abstract class
            // Vehicle vehicle = new Vehicle(); // Error

            // Creating objects of derived classes
            Car car = new Car();
            Bike bike = new Bike();
            Boat boat = new Boat();

            car.speed = 50;
            bike.speed = 20;
            boat.speed = 30;

            car.go();    // Output: The car is driving!
            bike.go();   // Output: The bike is cycling!
            boat.go();   // Output: The boat is sailing!

            Console.ReadKey();
        }
    }

    // Abstract class
    abstract class Vehicle
    {
        public int speed;

        // Regular method
        public void displaySpeed()
        {
            Console.WriteLine($"Speed: {speed}");
        }

        // Abstract method (no implementation)
        public abstract void go();
    }

    // Derived classes
    class Car : Vehicle
    {
        public override void go()
        {
            Console.WriteLine("The car is driving!");
        }
    }

    class Bike : Vehicle
    {
        public override void go()
        {
            Console.WriteLine("The bike is cycling!");
        }
    }

    class Boat : Vehicle
    {
        public override void go()
        {
            Console.WriteLine("The boat is sailing!");
        }
    }
}
```

### Output
```
The car is driving!
The bike is cycling!
The boat is sailing!
```

---

## How It Works
1. **Abstract Class (Vehicle)**:
   - Contains an abstract method `go()` that must be implemented in all derived classes.
   - Provides a fully implemented method `displaySpeed()` that all derived classes inherit.

2. **Derived Classes (Car, Bike, Boat)**:
   - Inherit the `speed` field and `displaySpeed()` method from the `Vehicle` class.
   - Implement the abstract method `go()` with their own specific behavior.

3. **Object Creation**:
   - Objects of the derived classes (`Car`, `Bike`, `Boat`) can be created and used.
   - The base class (`Vehicle`) cannot be instantiated directly.

---

## Benefits of Abstract Classes
1. **Enforces Implementation**:
   - Ensures that all derived classes provide their own version of abstract methods.

2. **Code Reusability**:
   - Shared fields and methods can be implemented once in the abstract class and reused in derived classes.

3. **Polymorphism**:
   - Abstract classes allow for polymorphic behavior, where the same base class reference can point to different derived class objects.

---

## Key Points
### 1. Abstract Classes vs Interfaces
- Abstract classes can have both implemented and abstract members, while interfaces can only have abstract members (before C# 8.0).
- A class can inherit only one abstract class but can implement multiple interfaces.

### 2. Abstract Methods
- Abstract methods must be implemented in all derived classes unless the derived class is also declared abstract.

### 3. Use Cases
- Use abstract classes when you want to provide a base implementation for some methods while forcing derived classes to implement others.

---

## Best Practices
- Use abstract classes for "is-a" relationships, where derived classes share common behavior and characteristics.
- Avoid using abstract classes if all members are abstract; in such cases, an interface may be more appropriate.
- Keep abstract methods focused and purposeful to ensure consistent implementation across derived classes.

