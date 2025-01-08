# C# Arrays Example

This project demonstrates how to use arrays in C#. Arrays are variables that can store multiple values of the same type. They have a fixed size, meaning the number of elements must be specified or initialized at declaration.

## Code Overview
```csharp
using System;

namespace consoleApp1
{
    class Program
    {
        static void Main(string[] arg)
        {
            // Arrays: A collection that stores multiple values of the same type.
            // Example 1: Declaring and initializing an array with a fixed size
            String[] names = new string[3];
            names[0] = "a";
            names[1] = "b";
            names[2] = "c";
            
            // Printing individual elements
            Console.WriteLine(names[0]);  // Outputs: a
            Console.WriteLine(names[1]);  // Outputs: b
            Console.WriteLine(names[2]);  // Outputs: c

            Console.WriteLine();

            // Example 2: Declaring and initializing an array with values
            String[] cars = { "BMW", "Toyota" };
            
            // Accessing individual elements by index
            Console.WriteLine(cars[0]);  // Outputs: BMW
            Console.WriteLine(cars[1]);  // Outputs: Toyota

            Console.WriteLine();

            // Editing an array element
            cars[0] = "Honda";
            Console.WriteLine(cars[0]);  // Outputs: Honda

            // Example 3: Looping through an array using a for loop
            for (int i = 0; i < cars.Length; i++)
            {
                Console.WriteLine($"{cars[i]}");  // Outputs each element of the array
            }

            Console.ReadKey();
        }
    }
}
```

## How It Works
1. **Array Initialization**:
   - Arrays can be initialized with a fixed size (`new string[3]`) and populated later.
   - Arrays can also be initialized directly with values (`{ "BMW", "Toyota" }`).
   
2. **Accessing Array Elements**:
   - Use the index (starting from 0) to access individual elements (`cars[0]`).
   - Modifying an element is done by assigning a new value to a specific index (`cars[0] = "Honda"`).
   
3. **Looping Through Arrays**:
   - A `for` loop is used to iterate through the array and print each element.
   - The loop uses `cars.Length` to determine the size of the array.

## Example Output
```
a
b
c

BMW
Toyota

Honda
Toyota
```

## Key Concepts
- **Array Indexing**: Arrays in C# are zero-indexed, meaning the first element is at index `0`.
- **Fixed Size**: Arrays have a fixed size once declared, but their elements can be modified.
- **Iteration**: Looping through arrays is common for performing operations on each element.
- **Initialization**: Arrays can be initialized with or without predefined values.

Arrays are fundamental in managing collections of data, providing a structured way to store and manipulate multiple values efficiently.

