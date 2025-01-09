
# Understanding Multithreading in C#

This guide explains the concept of **multithreading** in C#, its purpose, and how to use it effectively. Multithreading allows programs to perform multiple tasks concurrently, improving performance and responsiveness.

---

## Table of Contents
- [Understanding Multithreading in C#](#understanding-multithreading-in-c)
  - [Table of Contents](#table-of-contents)
  - [Introduction](#introduction)
  - [Example Code](#example-code)
  - [Key Concepts](#key-concepts)
    - [What is Multithreading?](#what-is-multithreading)
      - [Benefits:](#benefits)
    - [Creating and Starting Threads](#creating-and-starting-threads)
      - [Example:](#example)
    - [Thread Safety](#thread-safety)
  - [Commonly Used Thread Methods](#commonly-used-thread-methods)
    - [1. `Thread.Start()`](#1-threadstart)
    - [2. `Thread.Sleep(int milliseconds)`](#2-threadsleepint-milliseconds)
    - [3. `Thread.Join()`](#3-threadjoin)
    - [4. `Thread.Abort()`](#4-threadabort)
    - [5. `Thread.CurrentThread`](#5-threadcurrentthread)
    - [6. `Thread.IsAlive`](#6-threadisalive)
  - [Advanced Examples](#advanced-examples)
    - [Example 1: Multithreading with Multiple Data Types](#example-1-multithreading-with-multiple-data-types)
      - [Expected Output:](#expected-output)
    - [Example 2: Multithreading with Class and Shared Resource](#example-2-multithreading-with-class-and-shared-resource)
      - [Expected Output:](#expected-output-1)
  - [Conclusion](#conclusion)

---

## Introduction
In C#, a **thread** is an independent path of execution. The main thread is the primary thread that runs a program by default. Multithreading allows creating additional threads to perform different tasks concurrently, making programs more efficient and responsive.

---

## Example Code
Here’s an example demonstrating the use of multithreading in C#:

```csharp
using System;
using System.Collections.Generic;
using System.Threading;

namespace ConsoleApp1
{
    class Program
    {
        static void Main(string[] args)
        {
            // Main thread setup
            Thread mainThread = Thread.CurrentThread;
            mainThread.Name = "Main Thread";
            Console.WriteLine(mainThread.Name + " is starting!");

            // List of names to greet
            List<string> names = new List<string> { "John", "Alex", "Matt", "Abdi", "Will", "Thomas", "Jarry", "Doe", "Natalia", "Karen" };

            // Creating threads
            Thread thread1 = new Thread(Countdown); // Thread for counting down
            Thread thread2 = new Thread(Countup); // Thread for counting up
            Thread thread3 = new Thread(() => { Greet(names); }); // Thread for greeting names

            // Starting threads
            thread1.Start();
            thread2.Start();
            thread3.Start();

            Console.WriteLine(mainThread.Name + " is complete!");

            Console.ReadKey();
        }

        // Method for countdown timer
        public static void Countdown()
        {
            for (int i = 10; i >= 0; i--)
            {
                Console.WriteLine($"Timer #1: {i} seconds");
                Thread.Sleep(1000); // Simulate work with a delay
            }
            Console.WriteLine("Timer #1 is complete!");
        }

        // Method for countup timer
        public static void Countup()
        {
            for (int i = 0; i <= 10; i++)
            {
                Console.WriteLine($"Timer #2: {i} seconds");
                Thread.Sleep(1000);
            }
            Console.WriteLine("Timer #2 is complete!");
        }

        // Method to greet a list of names
        public static void Greet(List<string> names)
        {
            foreach (var name in names)
            {
                Console.WriteLine($"Timer #3: Hello {name}");
                Thread.Sleep(1000);
            }
            Console.WriteLine("Timer #3 is complete!");
        }
    }
}
```

---

## Key Concepts

### What is Multithreading?
Multithreading enables a program to run multiple threads simultaneously. Each thread runs independently, allowing tasks to execute concurrently.

#### Benefits:
1. **Concurrency:** Perform multiple tasks at the same time.
2. **Responsiveness:** Keeps the application responsive, especially in user interfaces.
3. **Efficiency:** Utilizes CPU resources more effectively.

### Creating and Starting Threads
Threads are created using the `Thread` class and started with the `Start` method.

#### Example:
```csharp
Thread thread = new Thread(MethodName);
thread.Start();
```
To pass arguments to a thread, use a lambda expression:
```csharp
Thread thread = new Thread(() => MethodName(argument));
thread.Start();
```

### Thread Safety
When multiple threads access shared resources, ensure thread safety to avoid race conditions or inconsistent data. Techniques like locks, semaphores, or the `Monitor` class can be used to synchronize threads.

---

## Commonly Used Thread Methods

### 1. `Thread.Start()`
Starts a thread.
```csharp
Thread thread = new Thread(MethodName);
thread.Start();
```

### 2. `Thread.Sleep(int milliseconds)`
Pauses the thread for a specified time.
```csharp
Thread.Sleep(1000); // Pause for 1 second
```

### 3. `Thread.Join()`
Blocks the calling thread until the specified thread terminates.
```csharp
thread.Join();
```

### 4. `Thread.Abort()`
Attempts to terminate the thread (not recommended for most use cases).
```csharp
thread.Abort();
```

### 5. `Thread.CurrentThread`
Gets the currently executing thread.
```csharp
Thread current = Thread.CurrentThread;
current.Name = "Main Thread";
```

### 6. `Thread.IsAlive`
Checks whether the thread is still running.
```csharp
if (thread.IsAlive)
{
    Console.WriteLine("Thread is still running");
}
```

---

## Advanced Examples

### Example 1: Multithreading with Multiple Data Types
```csharp
using System;
using System.Collections.Generic;
using System.Threading;

namespace ConsoleApp1
{
    class Program
    {
        static void Main(string[] args)
        {
            DataProcessor processor = new DataProcessor();

            // Thread for processing integers
            Thread thread1 = new Thread(() => processor.ProcessIntegers(new int[] { 1, 2, 3, 4 }));

            // Thread for processing strings
            Thread thread2 = new Thread(() => processor.ProcessStrings(new string[] { "apple", "banana", "cherry" }));

            // Thread for processing doubles
            Thread thread3 = new Thread(() => processor.ProcessDoubles(new double[] { 1.1, 2.2, 3.3 }));

            // Start threads
            thread1.Start();
            thread2.Start();
            thread3.Start();

            // Wait for all threads to complete
            thread1.Join();
            thread2.Join();
            thread3.Join();

            Console.WriteLine("All threads completed!");
            Console.ReadKey();
        }
    }

    class DataProcessor
    {
        // Method to process integer data
        public void ProcessIntegers(int[] numbers)
        {
            foreach (int number in numbers)
            {
                Console.WriteLine($"Processing integer: {number}");
                Thread.Sleep(500); // Simulate processing delay
            }
        }

        // Method to process string data
        public void ProcessStrings(string[] strings)
        {
            foreach (string str in strings)
            {
                Console.WriteLine($"Processing string: {str}");
                Thread.Sleep(500);
            }
        }

        // Method to process double data
        public void ProcessDoubles(double[] doubles)
        {
            foreach (double dbl in doubles)
            {
                Console.WriteLine($"Processing double: {dbl}");
                Thread.Sleep(500);
            }
        }
    }
}
```

#### Expected Output:
```
Processing integer: 1
Processing string: apple
Processing double: 1.1
Processing integer: 2
Processing string: banana
Processing double: 2.2
Processing integer: 3
Processing string: cherry
Processing double: 3.3
Processing integer: 4
All threads completed!
```

---

### Example 2: Multithreading with Class and Shared Resource
```csharp
using System;
using System.Threading;

namespace ConsoleApp2
{
    class Program
    {
        static void Main(string[] args)
        {
            Counter counter = new Counter();

            // Threads incrementing the counter
            Thread thread1 = new Thread(counter.Increment);
            Thread thread2 = new Thread(counter.Increment);

            thread1.Start();
            thread2.Start();

            thread1.Join();
            thread2.Join();

            Console.WriteLine($"Final count: {counter.Count}");
            Console.ReadKey();
        }
    }

    class Counter
    {
        private int count = 0; // Shared resource
        private object lockObject = new object(); // Object for locking

        public int Count => count;

        // Increment method with lock for thread safety
        public void Increment()
        {
            for (int i = 0; i < 100; i++)
            {
                lock (lockObject)
                {
                    count++;
                    Console.WriteLine($"Count: {count}");
                }
                Thread.Sleep(10); // Simulate processing delay
            }
        }
    }
}
```

#### Expected Output:
```
Count: 1
Count: 2
...
Count: 200
Final count: 200
```

---

## Conclusion
Multithreading in C# provides flexibility for performing concurrent tasks. Using common methods like `Start`, `Sleep`, and `Join`, you can control thread execution effectively. By combining multithreading with classes and generic data types, you can handle complex scenarios efficiently.
