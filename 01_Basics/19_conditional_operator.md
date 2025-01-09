# Conditional Operator in C#

This guide explains the conditional operator in C#, provides examples, and ensures that essential concepts are clear and easy to understand.

---

## What is the Conditional Operator?
The **conditional operator** is a shorthand way to perform conditional assignments in C#. It evaluates a condition and returns one of two values depending on whether the condition is `true` or `false`.

### Syntax:
```csharp
(condition) ? value_if_true : value_if_false;
```

- **`condition`**: The logical condition to evaluate (e.g., `x > 0`).
- **`value_if_true`**: The value to return if the condition is `true`.
- **`value_if_false`**: The value to return if the condition is `false`.

---

## Example Code
Here is a basic example to illustrate the conditional operator:

```csharp
using System;

namespace ConsoleApp1
{
    class Program
    {
        static void Main(string[] args)
        {
            int number;
            string result;

            Console.WriteLine("Enter a number: ");
            number = Convert.ToInt32(Console.ReadLine());

            // Using the conditional operator to check if the number is positive, negative, or zero
            result = (number > 0) ? "Positive" : (number < 0) ? "Negative" : "Zero";

            Console.WriteLine("The number is: " + result);

            Console.ReadKey();
        }
    }
}
```

---

## How It Works:
1. **Condition Evaluation**:
   - The condition `(number > 0)` is evaluated first.
   - If `true`, it assigns "Positive" to `result`.
   - If `false`, it evaluates the next condition `(number < 0)`.

2. **Nested Conditional Operators**:
   - The conditional operator can be nested as shown above to handle multiple conditions.
   - If all conditions are `false`, it defaults to the final value "Zero".

---

## More Examples
### Example 1: Checking for Even or Odd
```csharp
int number = 5;
string result = (number % 2 == 0) ? "Even" : "Odd";
Console.WriteLine("The number is: " + result);
```
**Output:**
```
The number is: Odd
```

### Example 2: Assigning a Discount Based on Age
```csharp
int age = 20;
int discount = (age < 18) ? 50 : 10;
Console.WriteLine("Discount: " + discount + "%");
```
**Output:**
```
Discount: 10%
```

### Example 3: Simplifying an If-Else Statement
Using the conditional operator is often a cleaner alternative to `if-else` statements:
```csharp
// Traditional if-else
if (age >= 18)
{
    result = "Adult";
}
else
{
    result = "Minor";
}

// Using conditional operator
result = (age >= 18) ? "Adult" : "Minor";
```

---

## Advantages of the Conditional Operator:
- **Concise**: Reduces the amount of code compared to `if-else` statements.
- **Readability**: When used appropriately, it makes the code cleaner and easier to read.

## When to Use:
- For simple, single-condition checks.
- Avoid using nested conditional operators for complex logic as it can reduce code readability.

---

## Example Output
### Scenario 1: Positive Number
```
Enter a number: 10
The number is: Positive
```

### Scenario 2: Negative Number
```
Enter a number: -5
The number is: Negative
```

### Scenario 3: Zero
```
Enter a number: 0
The number is: Zero
```

