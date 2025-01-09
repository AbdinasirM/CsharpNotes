# Array of Objects in C#

This guide explains the concept of arrays of objects in C#, provides examples, and ensures essential concepts are clearly understood.

---

## What is an Array of Objects?
An **array of objects** is a collection where each element is an object of a specific class. It allows you to store and manage multiple objects in a single array structure.

### Key Features:
1. An array can hold objects of the same type.
2. Individual objects in the array can be accessed and manipulated using their index.
3. Useful for managing collections of objects efficiently.

---

## Example Code
Here’s a simple example demonstrating an array of objects:

```csharp
using System;

namespace ConsoleApp1
{
    class Program
    {
        static void Main(string[] args)
        {
            // Create an array to hold Car objects
            Car[] garage = new Car[3];

            // Create individual Car objects
            Car car1 = new Car("Model A");
            Car car2 = new Car("Model B");
            Car car3 = new Car("Model C");

            // Add Car objects to the array
            garage[0] = car1;
            garage[1] = car2;
            garage[2] = car3;

            // Iterate over the array and display each car's model
            for (int i = 0; i < garage.Length; i++)
            {
                Console.WriteLine(garage[i].model);
            }

            Console.ReadKey();
        }
    }

    // Car class definition
    class Car
    {
        public string model;

        // Constructor
        public Car(string model)
        {
            this.model = model;
        }
    }
}
```

### Output
```
Model A
Model B
Model C
```

---

## How It Works
1. **Array Declaration**:
   - `Car[] garage = new Car[3];` creates an array capable of holding three `Car` objects.

2. **Object Initialization**:
   - Individual `Car` objects are created using the `Car` class constructor and assigned to array elements.

3. **Iteration**:
   - The `for` loop iterates through the `garage` array, accessing each `Car` object and printing its `model` field.

---

## Additional Examples
### Example 1: Initializing an Array Inline
You can initialize an array of objects directly without assigning them one by one:

```csharp
Car[] garage = new Car[]
{
    new Car("Model X"),
    new Car("Model Y"),
    new Car("Model Z")
};

foreach (Car car in garage)
{
    Console.WriteLine(car.model);
}
```
**Output:**
```
Model X
Model Y
Model Z
```

### Example 2: Modifying Objects in the Array
Objects in the array can be updated by accessing them via their index:

```csharp
Car[] garage = new Car[2];

garage[0] = new Car("Old Model");
garage[1] = new Car("Another Model");

garage[0].model = "Updated Model"; // Modify the model of the first car

Console.WriteLine(garage[0].model); // Output: Updated Model
```

---

## Key Points
1. **Null Values in Arrays**:
   - By default, elements in an array of objects are `null` until initialized.
   - Example:
     ```csharp
     Car[] garage = new Car[3];
     Console.WriteLine(garage[0]); // Output: null
     ```

2. **Array Manipulation**:
   - Objects in the array can be replaced or updated using their index.
   - Example:
     ```csharp
     garage[0] = new Car("New Model");
     ```

3. **Dynamic Arrays**:
   - For variable-sized collections, consider using `List<T>` instead of arrays.
   - Example:
     ```csharp
     List<Car> garage = new List<Car>();
     garage.Add(new Car("Model 1"));
     ```

---

## Best Practices
- Ensure objects in the array are initialized before use to avoid `NullReferenceException`.
- Use `foreach` for cleaner iteration when no index manipulation is required.
- Consider `List<T>` for dynamic-sized collections.

