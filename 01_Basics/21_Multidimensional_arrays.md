# Multidimensional Arrays in C#

This guide explains multidimensional arrays in C#, provides examples, and ensures essential concepts are clear and easy to understand.

---

## What are Multidimensional Arrays?
A **multidimensional array** is an array that has more than one dimension. In C#, you can create arrays with two or more dimensions to represent data in a structured format like a table, grid, or matrix.

### Types of Multidimensional Arrays:
1. **Rectangular Arrays**: All rows have the same number of columns.
2. **Jagged Arrays**: An array of arrays where each row can have a different number of columns (not covered here).

---

## Syntax for Declaring Multidimensional Arrays
### General Syntax:
```csharp
DataType[,] arrayName = new DataType[rows, columns];
```
- **`DataType`**: The type of data the array will store (e.g., `int`, `string`).
- **`rows`**: Number of rows.
- **`columns`**: Number of columns.

---

## Example Code
### Example 1: Initializing and Accessing a 2D Array
```csharp
using System;

namespace ConsoleApp1
{
    class Program
    {
        static void Main(string[] args)
        {
            // Declare and initialize a 2D array
            int[,] numbers = new int[2, 3]
            {
                { 1, 2, 3 },
                { 4, 5, 6 }
            };

            // Access elements in the array
            Console.WriteLine("Element at [0, 0]: " + numbers[0, 0]); // Output: 1
            Console.WriteLine("Element at [1, 2]: " + numbers[1, 2]); // Output: 6

            // Print all elements in the array
            Console.WriteLine("All elements in the array:");
            for (int i = 0; i < 2; i++)
            {
                for (int j = 0; j < 3; j++)
                {
                    Console.Write(numbers[i, j] + " ");
                }
                Console.WriteLine();
            }

            Console.ReadKey();
        }
    }
}
```
**Output:**
```
Element at [0, 0]: 1
Element at [1, 2]: 6
All elements in the array:
1 2 3 
4 5 6
```

### Example 2: Declaring and Initializing Inline
```csharp
int[,] matrix = {
    { 10, 20, 30 },
    { 40, 50, 60 },
    { 70, 80, 90 }
};

Console.WriteLine("Element at [2, 1]: " + matrix[2, 1]); // Output: 80
```

---

## How It Works:
1. **Declaration**:
   - The array is declared with a specific size (e.g., `new int[2, 3]`).
   - In a rectangular array, every row has the same number of columns.

2. **Accessing Elements**:
   - Use the row and column indices to access or modify an element: `array[row, column]`.
   - Indexing starts at `0` (zero-based indexing).

3. **Iteration**:
   - Use nested loops to traverse and manipulate elements in a multidimensional array.

---

## Additional Examples
### Example 3: Summing All Elements in a 2D Array
```csharp
int[,] grid = {
    { 1, 2, 3 },
    { 4, 5, 6 },
    { 7, 8, 9 }
};

int sum = 0;
for (int i = 0; i < 3; i++)
{
    for (int j = 0; j < 3; j++)
    {
        sum += grid[i, j];
    }
}

Console.WriteLine("Sum of all elements: " + sum); // Output: 45
```

### Example 4: Finding the Maximum Element
```csharp
int[,] values = {
    { 5, 12, 3 },
    { 9, 21, 6 },
    { 8, 14, 17 }
};

int max = values[0, 0];
for (int i = 0; i < 3; i++)
{
    for (int j = 0; j < 3; j++)
    {
        if (values[i, j] > max)
        {
            max = values[i, j];
        }
    }
}

Console.WriteLine("Maximum element: " + max); // Output: 21
```

---

## Advantages of Multidimensional Arrays
1. **Organized Data Storage**: Useful for representing tables, grids, and matrices.
2. **Ease of Access**: Elements can be directly accessed using row and column indices.
3. **Structured Layout**: Simplifies complex data relationships.

## Best Practices
- Use multidimensional arrays for fixed-size data that fits a grid-like structure.
- For varying row sizes, consider using jagged arrays.

