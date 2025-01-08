# C# Guessing Game Using Loops

This project demonstrates a simple guessing game using loops in C#. The program generates a random number between 1 and 100 and asks the user to guess the number. It continues to prompt the user until the correct number is guessed.



## Code Overview
```csharp
using System;

namespace consoleApp1
{
    class Program
    {
        static void Main(string[] arg)
        {
            // Guessing game using while loop

            // Generate a random number between 1 and 100
            Random rnd = new Random();
            bool play_again = true;
            int min = 1;
            int max = 100;
            int random_number_to_guess = rnd.Next(min, max);  

            // Ask the user to guess the number
            Console.WriteLine("Guess a number between 1 - 100 :");
            int secret_number = Convert.ToInt32(Console.ReadLine());

            // Loop until the user guesses the correct number
            while (secret_number != random_number_to_guess)
            {
                // Prompt the user to guess again
                Console.WriteLine(secret_number + " is not correct. Guess again: ");
                secret_number = Convert.ToInt32(Console.ReadLine());
            }

            // Congratulate the user on guessing the correct number
            Console.WriteLine("You guessed it right! The secret number was " + random_number_to_guess);
            
            Console.ReadKey();
        }
    }
}
```

## How It Works
1. The program generates a random number between 1 and 100 using `Random.Next()`.
2. It prompts the user to guess the number.
3. If the user's guess is incorrect, the program enters a `while` loop.
4. The loop continues to prompt the user until the correct number is guessed.
5. Once the user guesses the correct number, the program exits the loop and congratulates the user.

## Example Output
```
Guess a number between 1 - 100 :
50 is not correct. Guess again:
75 is not correct. Guess again:
90 is not correct. Guess again:
100 is not correct. Guess again:
85 is not correct. Guess again:
92 is not correct. Guess again:
95 is not correct. Guess again:
98 is not correct. Guess again:
99 is not correct. Guess again:
97
You guessed it right! The secret number was 97
```

## Key Concepts
- **Random Number Generation**: The `Random` class generates a random number within a specified range.
- **While Loop**: The `while` loop keeps prompting the user until the condition (`secret_number != random_number_to_guess`) is false.
- **User Input**: The program reads user input using `Console.ReadLine()` and converts it to an integer.
- **Console.WriteLine()**: Provides feedback to the user after each guess.



