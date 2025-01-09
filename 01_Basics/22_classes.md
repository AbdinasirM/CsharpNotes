# Classes in C#

This guide covers the concept of classes in C#, provides examples, and explains important concepts such as `public`, `private`, `internal`, and `static`.

---

## What is a Class?
A **class** in C# is a blueprint for creating objects. It is a fundamental concept of Object-Oriented Programming (OOP) and is used to bundle related data and methods together.

### Key Features of Classes:
- Encapsulation of data and methods.
- Can be instantiated into objects (non-static classes).
- Can contain static methods and properties (usable without creating an object).

---

## Creating a Class in C#
### Example 1: Creating a Class in the Same File
You can define a class within the same file as your `Main` method:

```csharp
class Messages
{
    public void Hello()
    {
        Console.WriteLine("Hello");
    }

    public void Bye()
    {
        Console.WriteLine("Bye");
    }
}

// Usage in Main method:
Messages msg = new Messages();
msg.Hello(); // Output: Hello
msg.Bye();   // Output: Bye
```

### Example 2: Using a Class from Another File
To organize your code, you can create classes in separate files.

**File: Class1.cs**
```csharp
namespace ConsoleApp1
{
    public class Class1
    {
        public static void Greet(string name)
        {
            Console.WriteLine($"Hello {name}");
        }
    }
}
```

**File: Program.cs**
```csharp
using ConsoleApp1;

namespace consoleApp1
{
    class Program
    {
        static void Main(string[] args)
        {
            // Calling a static method from another class
            Class1.Greet("Abdi"); // Output: Hello Abdi
            Console.ReadKey();
        }
    }
}
```

---

## Access Modifiers in C#
Access modifiers control the visibility and accessibility of classes, methods, and properties. They ensure encapsulation, a core principle of OOP.

### 1. **Public**
- Accessible from any class and namespace.
- Similar to `public` in C++.

```csharp
public class PublicExample
{
    public void SayHello()
    {
        Console.WriteLine("Hello from a public method");
    }
}

// Usage:
PublicExample example = new PublicExample();
example.SayHello();
```

### 2. **Private**
- Accessible only within the same class.
- Similar to `private` in C++.

```csharp
class PrivateExample
{
    private void SaySecret()
    {
        Console.WriteLine("This is private");
    }

    public void RevealSecret()
    {
        SaySecret();
    }
}

// Usage:
PrivateExample example = new PrivateExample();
example.RevealSecret(); // Output: This is private
```

### 3. **Internal**
- Accessible only within the same assembly (project).
- Useful for sharing functionality within a project while keeping it hidden from external assemblies.

```csharp
internal class InternalExample
{
    internal void SayInternal()
    {
        Console.WriteLine("This is internal");
    }
}

// Usage within the same assembly:
InternalExample example = new InternalExample();
example.SayInternal();
```

### 4. **Static**
- Belongs to the class, not to any object.
- Can be accessed without creating an instance of the class.

```csharp
public class StaticExample
{
    public static void SayStatic()
    {
        Console.WriteLine("This is a static method");
    }
}

// Usage:
StaticExample.SayStatic(); // Output: This is a static method
```

---

## Summary of Access Modifiers
| Modifier   | Accessibility                                     |
|------------|--------------------------------------------------|
| `public`   | Accessible from anywhere.                        |
| `private`  | Accessible only within the same class.           |
| `internal` | Accessible only within the same assembly.        |
| `static`   | Can be accessed without creating an object.      |

---

## Combining Modifiers
Modifiers like `static` can be combined with others:
- **`public static`**: A method or property accessible from anywhere without creating an object.
- **`internal static`**: A static method accessible only within the same assembly.

---

## Example Output
### Input Code
```csharp
namespace ConsoleApp1
{
    public class Greetings
    {
        public static void Welcome(string name)
        {
            Console.WriteLine($"Welcome, {name}!");
        }
    }

    class Program
    {
        static void Main(string[] args)
        {
            Greetings.Welcome("John");
            Console.ReadKey();
        }
    }
}
```

### Output
```
Welcome, John!
```

