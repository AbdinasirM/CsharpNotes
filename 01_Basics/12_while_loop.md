# C# While Loop Example

This project demonstrates the use of a `while` loop in C#. The program prompts the user to enter their name and keeps asking until a valid (non-empty) name is provided. Once a name is entered, it greets the user.



## Code Overview
```csharp
using System;

namespace consoleApp1
{
    class Program
    {
        static void Main(string[] arg)
        {
            // The while loop repeats the code block while the condition is true.
            Console.Write("Enter your name: ");
            String name = Console.ReadLine();

            // The loop will continue until the user provides a non-empty name.
            while (name == null || name == "") {
                Console.Write("Enter your name: ");
                name = Console.ReadLine();
            }
            
            // Greets the user with the entered name.
            Console.WriteLine("Hello " + name);

            // Waits for a key press to exit the program.
            Console.ReadKey();
        }
    }
}
```

## How It Works
1. The program initially prompts the user to enter their name.
2. If the user enters an empty string or nothing, the `while` loop triggers and asks again.
3. This process repeats until the user provides a valid input.
4. Once a valid name is entered, the program exits the loop and greets the user.

## Example Output
```
Enter your name:
Enter your name:
Enter your name: John
Hello John
```

## Key Concepts
- **While Loop**: A control structure that repeats a block of code as long as a specified condition is `true`.
- **Condition**: The expression `name == null || name == ""` checks if the user has not entered any text.
- **Console.ReadLine()**: Reads input from the user.
- **Console.WriteLine()**: Outputs text to the console.
- **Console.ReadKey()**: Pauses the program, waiting for the user to press a key.

## Why Use While Loops?
While loops are useful for scenarios where the number of iterations is not known beforehand. They ensure that a block of code is executed repeatedly until a specific condition is met.



