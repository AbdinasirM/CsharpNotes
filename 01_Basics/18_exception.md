# Exception Handling in C#

This guide explains the basics of exception handling in C#, provides examples, and ensures that essential concepts are easy to understand.

---

## What is Exception Handling?
Exception handling is a mechanism to handle runtime errors in your program. It allows you to manage and recover from unexpected issues that may occur during program execution without crashing the entire application.

### Key Components:
- **`try` block**: Contains the code that might throw an exception. This is considered the "dangerous" code.
- **`catch` block**: Handles the exceptions that occur within the `try` block.
- **`finally` block**: (Optional) Contains code that will always execute, regardless of whether an exception was thrown or caught.

---

## Code Example
Here is an example of how exception handling works in C#:

```csharp
using System;

namespace ConsoleApp1
{
    class Program
    {
        static void Main(string[] args)
        {
            int x;
            int y;
            double result;

            try
            {
                Console.WriteLine("Enter a number 1: ");
                x = Convert.ToInt32(Console.ReadLine());

                Console.WriteLine("Enter a number 2: ");
                y = Convert.ToInt32(Console.ReadLine());

                result = x / y;
                Console.WriteLine("Result: " + result);
            }
            catch (FormatException e)
            {
                Console.WriteLine("Enter ONLY numbers, please!");
            }
            catch (DivideByZeroException z)
            {
                Console.WriteLine("Can't divide by zero!");
            }
            catch (Exception e)
            {
                Console.WriteLine("Something went wrong: " + e.Message);
            }
            finally
            {
                Console.WriteLine("Execution completed.");
            }

            Console.ReadKey();
        }
    }
}
```

---

## How It Works:
1. **`try` Block**:
   - The program attempts to execute the code inside the `try` block.
   - If the code runs successfully, the `catch` blocks are skipped.
   
2. **`catch` Blocks**:
   - If an exception occurs, the appropriate `catch` block is executed based on the exception type.
   - Example: If the user enters a non-numeric value, a `FormatException` is caught.

3. **`finally` Block**:
   - The `finally` block executes after the `try` and `catch` blocks, regardless of whether an exception was thrown or not.
   - It is often used for cleanup tasks like closing files, releasing resources, etc.

---

## Types of Exceptions Handled:
1. **`FormatException`**:
   - Occurs when an invalid format is provided (e.g., entering text instead of a number).
   - Example Output: `Enter ONLY numbers, please!`

2. **`DivideByZeroException`**:
   - Occurs when attempting to divide by zero.
   - Example Output: `Can't divide by zero!`

3. **General Exceptions**:
   - Caught by the `Exception` class to handle any unexpected errors.
   - Example Output: `Something went wrong: [error message]`

---

## Additional Notes:
- **Multiple `catch` blocks**:
  - You can have multiple `catch` blocks to handle different types of exceptions.
  - Always put the more specific exceptions (e.g., `FormatException`) before the general `Exception` class.

- **Exception Message**:
  - Use `e.Message` to display the detailed error message when using the `Exception` class.

- **Best Practices**:
  - Handle exceptions gracefully to avoid confusing users.
  - Do not use exceptions for regular control flow.
  - Always clean up resources (e.g., files, connections) in the `finally` block.

---

## Example Output
### Scenario 1: Correct Input
```
Enter a number 1: 10
Enter a number 2: 2
Result: 5
Execution completed.
```

### Scenario 2: Invalid Format Input
```
Enter a number 1: abc
Enter ONLY numbers, please!
Execution completed.
```

### Scenario 3: Division by Zero
```
Enter a number 1: 10
Enter a number 2: 0
Can't divide by zero!
Execution completed.
```
