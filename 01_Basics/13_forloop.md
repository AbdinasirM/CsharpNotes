# C# For Loop Example

This project demonstrates the use of `for` loops in C#. The program includes two examples:
1. A simple `for` loop that prints numbers from 0 to 9.
2. A nested `for` loop that generates a pattern of characters based on user input.



## Code Overview
```csharp
using System;

namespace consoleApp1
{
    class Program
    {
        static void Main(string[] arg)
        {
            // For loops: Repeats code for a finite number of times

            // Example 1: Basic for loop that prints numbers from 0 to 9
            for (int i = 0; i < 10; i++)
            {
                Console.WriteLine(i);   
            }

            // Example 2: Nested for loop to create a grid of characters
            Console.Write("How many rows: ");
            int rows = Convert.ToInt32(Console.ReadLine());
            Console.Write("How many columns: ");
            int columns = Convert.ToInt32(Console.ReadLine());
            Console.Write("What symbol or character: ");
            String character_symbol = Console.ReadLine();

            for (int i = 0; i < rows; ++i)
            {
                for (int j = 0; j < columns; j++)
                {
                    Console.Write(character_symbol);
                }
                Console.WriteLine();
            }

            Console.ReadKey();
        }
    }
}
```

## How It Works
### Example 1: Basic For Loop
- A `for` loop is used to iterate 10 times.
- Each iteration prints the current value of `i` to the console.

### Example 2: Nested For Loop (Grid Generator)
1. The program asks the user to input the number of rows and columns.
2. The user is also prompted to enter a symbol or character.
3. The outer `for` loop iterates over the rows, while the inner `for` loop iterates over the columns.
4. For each iteration of the outer loop, the inner loop prints the specified character, creating a grid-like structure.

## Example Output
```
0
1
2
3
4
5
6
7
8
9
How many rows: 3
How many columns: 5
What symbol or character: *
*****
*****
*****
```

## Key Concepts
- **For Loop**: A control structure that repeats code a specified number of times.
- **Nested Loops**: Loops within loops allow for creating multi-dimensional patterns or grids.
- **Console.ReadLine()**: Accepts user input.
- **Console.Write()**: Prints characters without a newline.
- **Console.WriteLine()**: Moves to the next line after printing.

## Why Use For Loops?
- `For` loops are useful when the number of iterations is known in advance.
- Nested loops are ideal for handling grid-based or matrix-like operations.



