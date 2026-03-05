# C# — A Comprehensive Guide for Beginners

<h1 align="center">
    <img alt="C#" title="C#" src="https://upload.wikimedia.org/wikipedia/commons/thumb/b/bd/Logo_C_sharp.svg/256px-Logo_C_sharp.svg.png" width="200px" />
</h1>

<p align="center">
  <a href="#about">About</a>&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
  <a href="#contents">Contents</a>&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
  <a href="#section-1">Section 1 — Introduction</a>&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
  <a href="#section-2">Section 2 — Variables & Types</a>&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
  <a href="#section-3">Section 3 — Operators</a>&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
  <a href="#section-4">Section 4 — Control Structures</a>&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
  <a href="#section-5">Section 5 — Collections</a>&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
  <a href="#section-6">Section 6 — Methods</a>&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
  <a href="#section-7">Section 7 — OOP</a>&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
  <a href="#section-8">Section 8 — Generics & LINQ</a>&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
  <a href="#section-9">Section 9 — Modern C# Features</a>&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
  <a href="#references">References</a>
</p>

---

## :bookmark_tabs: About <a name = "about"></a>

This guide is a structured, step-by-step roadmap to learn the **C# programming language** from scratch. It covers everything from variables and control flow to object-oriented programming, generics, LINQ, and modern C# features.

This guide is the **first part** of a two-part series:
- **Part 1 (this document):** The C# language itself
- **Part 2:** The .NET Platform, ASP.NET Core, EF Core, and Web APIs

> **How to use this guide:** Read each section in order. Every topic includes a brief explanation, key concepts, and practical code examples. Each section ends with exercises to consolidate your knowledge.

---

## :books: Contents <a name = "contents"></a>

| Section | Topic |
|---------|-------|
| [Section 1](#section-1) | Introduction to C# |
| [Section 2](#section-2) | Variables and Data Types |
| [Section 3](#section-3) | Operators |
| [Section 4](#section-4) | Control Structures |
| [Section 5](#section-5) | Arrays and Collections |
| [Section 6](#section-6) | Methods |
| [Section 7](#section-7) | Object-Oriented Programming |
| [Section 8](#section-8) | Generics and LINQ |
| [Section 9](#section-9) | Modern C# Features |

---

## Section 1 — Introduction to C# <a name = "section-1"></a>

### 1.1 What is C#?

C# (pronounced *"C-sharp"*) is a modern, object-oriented, and type-safe programming language created by **Anders Hejlsberg** at Microsoft, first released in 2000. It runs on the **.NET** runtime, making it cross-platform — you can build and run C# applications on Windows, Linux, and macOS.

**Why learn C#?**
- Used for Web APIs, desktop apps, mobile apps (Xamarin/MAUI), games (Unity), and cloud services.
- Strongly typed with rich IDE support (Visual Studio, Rider, VS Code).
- Modern features: nullable reference types, pattern matching, records, async/await.
- Large ecosystem and active community.

**Key characteristics:**
- **Statically typed** — variable types are known at compile time.
- **Managed memory** — the CLR (Common Language Runtime) handles garbage collection.
- **Object-oriented** — everything revolves around classes and objects.
- **Cross-platform** — runs on Windows, Linux, and macOS via .NET.

---

### 1.2 Setting Up the Environment

```bash
# 1. Install the .NET SDK from https://dotnet.microsoft.com/download
# Check the installed version
dotnet --version

# 2. Create your first console project
dotnet new console -n HelloWorld
cd HelloWorld

# 3. Run it
dotnet run
```

---

### 1.3 Your First Program

```csharp
// Program.cs — Top-level statements (.NET 6+)
Console.WriteLine("Hello, World!");
```

Or the traditional, explicit form:

```csharp
using System;

namespace HelloWorld
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Hello, World!");
            Console.ReadLine(); // waits for user input
        }
    }
}
```

**Key points:**
- `using System;` imports the `System` namespace (contains `Console`).
- `namespace` groups related classes.
- `Main` is the **entry point** of every C# program.
- `Console.WriteLine()` prints text followed by a newline.
- Statements end with a semicolon `;`.

---

### :pencil: Section 1 — Exercises

1. Create a new console project and modify it to print your name, age, and city on separate lines.
2. Print a simple ASCII art pattern using `Console.WriteLine`.

---

## Section 2 — Variables and Data Types <a name = "section-2"></a>

### 2.1 Value Types vs Reference Types

C# divides all types into two fundamental categories:

| Category | Description | Stored in |
|----------|-------------|-----------|
| **Value types** | Hold the data directly | Stack |
| **Reference types** | Hold a reference (pointer) to the data | Heap |

---

### 2.2 Built-in Value Types

| Type | Size | Range / Notes | Example |
|------|------|---------------|---------|
| `byte` | 1 byte | 0 to 255 | `byte b = 200;` |
| `short` | 2 bytes | -32,768 to 32,767 | `short s = 1000;` |
| `int` | 4 bytes | ~-2 billion to 2 billion | `int age = 25;` |
| `long` | 8 bytes | Very large integers | `long pop = 8_000_000_000L;` |
| `float` | 4 bytes | ~7 decimal digits | `float f = 3.14f;` |
| `double` | 8 bytes | ~15-16 decimal digits | `double d = 3.14159;` |
| `decimal` | 16 bytes | 28-29 significant digits (financial) | `decimal price = 9.99m;` |
| `bool` | 1 byte | `true` or `false` | `bool isActive = true;` |
| `char` | 2 bytes | Single Unicode character | `char grade = 'A';` |

---

### 2.3 Reference Types

```csharp
// string — immutable sequence of characters
string name = "Alice";
string fullName = "Alice" + " " + "Smith"; // concatenation
string interpolated = $"Hello, {name}!";   // string interpolation

// object — base type of all types in C#
object obj = 42;       // boxing: int → object
int num = (int)obj;    // unboxing: object → int

// Arrays and classes are also reference types (covered in later sections)
```

---

### 2.4 Variable Declaration

```csharp
// Explicit declaration
int age = 30;
string city = "São Paulo";
bool isAdmin = false;
double height = 1.75;

// var — type is inferred by the compiler at compile time
var country = "Brazil";  // inferred as string
var count = 10;           // inferred as int
var price = 9.99m;        // inferred as decimal

// Constants — value cannot change after assignment
const double Pi = 3.14159265358979;
const int MaxRetries = 3;

// Readonly — can only be assigned in constructor (for fields)
// readonly int _id;

// Multiple variables in one line (same type)
int x = 1, y = 2, z = 3;
```

---

### 2.5 Nullable Types

By default, value types cannot be `null`. Use the `?` suffix to make them nullable.

```csharp
// Nullable value type
int? age = null;
double? salary = null;

// Check and use safely
if (age.HasValue)
{
    Console.WriteLine($"Age: {age.Value}");
}

// Null-coalescing operator ?? — provide a default if null
int result = age ?? 0;       // if age is null, use 0
string name = null;
string display = name ?? "Anonymous";

// Null-coalescing assignment ??=
name ??= "Default Name";     // assigns only if name is null

// Nullable reference types (C# 8+ with #nullable enable)
#nullable enable
string? nullableString = null;  // explicitly nullable
string nonNullable = "Hello";   // must not be null
```

---

### 2.6 Type Conversion

```csharp
// Implicit conversion (safe, no data loss)
int i = 100;
long l = i;    // int → long (implicit)
double d = i;  // int → double (implicit)

// Explicit conversion / casting (may lose data)
double pi = 3.14;
int truncated = (int)pi;  // 3 — decimal part is lost

// Convert class (safer for strings and cross-type conversions)
string strNum = "42";
int parsed = Convert.ToInt32(strNum);
bool flag = Convert.ToBoolean(1);       // true

// TryParse — safe parsing without exceptions
string input = "123abc";
bool success = int.TryParse(input, out int value);
// success = false, value = 0

// ToString
int number = 42;
string text = number.ToString();        // "42"
string formatted = number.ToString("D5"); // "00042"
decimal money = 1234.56m;
string currency = money.ToString("C");  // "$1,234.56" (locale-dependent)
```

---

### :pencil: Section 2 — Exercises

1. Declare variables of at least 6 different types and print each one with its type name using `GetType().Name`.
2. Write a program that reads the user's name and age from the console (`Console.ReadLine()`) and prints a greeting.
3. Create a `decimal? discount` nullable variable. Use the `??` operator to calculate a final price: if discount is null, apply 0% discount.

---

## Section 3 — Operators <a name = "section-3"></a>

### 3.1 Arithmetic Operators

```csharp
int a = 10, b = 3;

Console.WriteLine(a + b);   // 13  — addition
Console.WriteLine(a - b);   // 7   — subtraction
Console.WriteLine(a * b);   // 30  — multiplication
Console.WriteLine(a / b);   // 3   — integer division (truncates)
Console.WriteLine(a % b);   // 1   — modulo (remainder)

// Integer vs floating-point division
double result = 10.0 / 3;   // 3.3333... (use double to get decimal result)

// Increment and Decrement
int x = 5;
x++;    // post-increment: x becomes 6
++x;    // pre-increment:  x becomes 7
x--;    // post-decrement: x becomes 6
--x;    // pre-decrement:  x becomes 5

// Compound assignment
x += 3;  // x = x + 3
x -= 2;  // x = x - 2
x *= 4;  // x = x * 4
x /= 2;  // x = x / 2
x %= 3;  // x = x % 3
```

---

### 3.2 Comparison Operators

```csharp
int a = 10, b = 3;

Console.WriteLine(a == b);   // False — equal to
Console.WriteLine(a != b);   // True  — not equal to
Console.WriteLine(a > b);    // True  — greater than
Console.WriteLine(a < b);    // False — less than
Console.WriteLine(a >= 10);  // True  — greater than or equal
Console.WriteLine(a <= 9);   // False — less than or equal

// String comparison
string s1 = "hello";
string s2 = "HELLO";
Console.WriteLine(s1 == s2);  // False (case-sensitive)
Console.WriteLine(string.Equals(s1, s2, StringComparison.OrdinalIgnoreCase)); // True
```

---

### 3.3 Logical Operators

```csharp
bool t = true, f = false;

Console.WriteLine(t && f);  // False — AND: both must be true
Console.WriteLine(t || f);  // True  — OR: at least one must be true
Console.WriteLine(!t);      // False — NOT: inverts

// Short-circuit evaluation
int x = 0;
bool r1 = (x != 0) && (10 / x > 1);  // safe: second part not evaluated if first is false
bool r2 = (x == 0) || (10 / x > 1);  // safe: second part not evaluated if first is true
```

---

### 3.4 String Operators

```csharp
string firstName = "Alice";
string lastName = "Smith";

// Concatenation
string full = firstName + " " + lastName;           // "Alice Smith"

// String interpolation (preferred — readable and efficient)
string greeting = $"Hello, {firstName} {lastName}!";

// Verbatim string (ignores escape sequences)
string path = @"C:\Users\Alice\Documents";

// Multi-line string (C# 11)
string multiLine = """
    This is line 1.
    This is line 2.
    """;

// Useful string methods
string text = "  Hello, World!  ";
Console.WriteLine(text.Trim());              // "Hello, World!"
Console.WriteLine(text.ToUpper());           // "  HELLO, WORLD!  "
Console.WriteLine(text.ToLower());           // "  hello, world!  "
Console.WriteLine(text.Contains("World"));  // True
Console.WriteLine(text.Replace("World", "C#")); // "  Hello, C#!  "
Console.WriteLine(text.Substring(2, 5));    // "Hello"

string csv = "a,b,c,d";
string[] parts = csv.Split(',');             // ["a", "b", "c", "d"]
string joined = string.Join(" | ", parts);  // "a | b | c | d"
```

---

### :pencil: Section 3 — Exercises

1. Write a program that calculates the area and perimeter of a rectangle, given `width` and `height` entered by the user.
2. Create a "grade checker": ask for a score (0–100) and print whether it is a pass (>= 60) AND above average (>= 75) using logical operators.
3. Given a full name as a single string (e.g., `"John Michael Doe"`), extract and print the first name, middle name, and last name separately using string methods.

---

## Section 4 — Control Structures <a name = "section-4"></a>

### 4.1 If / Else If / Else

```csharp
int score = 78;

if (score >= 90)
{
    Console.WriteLine("Grade: A");
}
else if (score >= 80)
{
    Console.WriteLine("Grade: B");
}
else if (score >= 70)
{
    Console.WriteLine("Grade: C");
}
else if (score >= 60)
{
    Console.WriteLine("Grade: D");
}
else
{
    Console.WriteLine("Grade: F");
}

// Ternary operator — concise if/else for single expressions
string status = score >= 60 ? "Pass" : "Fail";
Console.WriteLine(status);

// Null-conditional in condition
string? name = null;
string display = name?.ToUpper() ?? "UNKNOWN"; // "UNKNOWN"
```

---

### 4.2 Switch Statement

```csharp
string day = "Wednesday";

switch (day)
{
    case "Monday":
    case "Tuesday":
    case "Wednesday":
    case "Thursday":
    case "Friday":
        Console.WriteLine("Weekday — back to work!");
        break;
    case "Saturday":
    case "Sunday":
        Console.WriteLine("Weekend — enjoy your rest!");
        break;
    default:
        Console.WriteLine("Invalid day.");
        break;
}
```

---

### 4.3 Switch Expression (C# 8+)

```csharp
// Switch expression — returns a value
string day = "Saturday";
string type = day switch
{
    "Saturday" or "Sunday" => "Weekend",
    "Monday" or "Tuesday" or "Wednesday"
        or "Thursday" or "Friday" => "Weekday",
    _ => "Invalid"
};
Console.WriteLine(type); // "Weekend"

// With objects and pattern matching
object obj = 3.14;
string description = obj switch
{
    int i    => $"Integer: {i}",
    double d => $"Double: {d}",
    string s => $"String: {s}",
    null     => "Null value",
    _        => "Unknown type"
};
```

---

### 4.4 Loops

#### for

```csharp
// Classic for loop
for (int i = 0; i < 5; i++)
{
    Console.WriteLine($"Iteration {i}");
}

// Counting backwards
for (int i = 10; i >= 0; i--)
{
    Console.Write($"{i} ");
}
// 10 9 8 7 6 5 4 3 2 1 0
```

#### while

```csharp
int attempts = 0;
string password = "";

while (password != "secret123")
{
    Console.Write("Enter password: ");
    password = Console.ReadLine() ?? "";
    attempts++;

    if (attempts >= 3)
    {
        Console.WriteLine("Too many attempts.");
        break;
    }
}
```

#### do-while

```csharp
int number;
do
{
    Console.Write("Enter a positive number: ");
} while (!int.TryParse(Console.ReadLine(), out number) || number <= 0);

Console.WriteLine($"You entered: {number}");
```

#### foreach

```csharp
string[] fruits = { "Apple", "Banana", "Cherry", "Date" };

foreach (string fruit in fruits)
{
    Console.WriteLine(fruit);
}

// foreach with index using LINQ
foreach (var (fruit, index) in fruits.Select((f, i) => (f, i)))
{
    Console.WriteLine($"{index}: {fruit}");
}
```

#### break, continue, return

```csharp
for (int i = 0; i < 10; i++)
{
    if (i == 3) continue;  // skip 3
    if (i == 7) break;     // stop at 7
    Console.Write($"{i} ");
}
// Output: 0 1 2 4 5 6
```

---

### :pencil: Section 4 — Exercises

1. **FizzBuzz:** Print numbers 1–100. For multiples of 3 print "Fizz", for multiples of 5 print "Buzz", for both print "FizzBuzz".
2. **Guess the number:** Generate a random number between 1 and 100. Let the user guess repeatedly, telling them if the guess is too high, too low, or correct. Count the number of attempts.
3. **Simple menu:** Use a `do-while` loop to show a menu (1. Add, 2. Subtract, 3. Quit). Keep processing operations until the user chooses 3.

---

## Section 5 — Arrays and Collections <a name = "section-5"></a>

### 5.1 Arrays

Arrays have a **fixed size** set at creation time.

```csharp
// Declaration and initialization
int[] numbers = new int[5];               // [0, 0, 0, 0, 0]
int[] primes  = new int[] { 2, 3, 5, 7, 11 };
string[] days = { "Mon", "Tue", "Wed", "Thu", "Fri" };

// Access by index (zero-based)
Console.WriteLine(primes[0]);    // 2
Console.WriteLine(primes[^1]);   // 11 — last element (C# 8+)

// Length
Console.WriteLine(primes.Length); // 5

// Modify
numbers[2] = 42;

// Iterate
for (int i = 0; i < primes.Length; i++)
    Console.Write(primes[i] + " ");

foreach (int p in primes)
    Console.Write(p + " ");

// Useful Array methods
Array.Sort(numbers);
Array.Reverse(numbers);
int idx = Array.IndexOf(primes, 5); // 2

// Multidimensional
int[,] matrix = new int[3, 3];
matrix[0, 0] = 1;
matrix[1, 1] = 5;

int[,] grid = { { 1, 2, 3 }, { 4, 5, 6 }, { 7, 8, 9 } };
Console.WriteLine(grid[1, 2]); // 6

// Jagged arrays (array of arrays)
int[][] jagged = new int[3][];
jagged[0] = new int[] { 1, 2 };
jagged[1] = new int[] { 3, 4, 5 };
jagged[2] = new int[] { 6 };
```

---

### 5.2 List\<T\>

`List<T>` is the most commonly used collection — like an array but with **dynamic size**.

```csharp
using System.Collections.Generic;

List<string> names = new List<string>();

// Add
names.Add("Alice");
names.Add("Bob");
names.AddRange(new[] { "Charlie", "Diana" });

// Access
Console.WriteLine(names[0]);     // "Alice"
Console.WriteLine(names.Count);  // 4

// Remove
names.Remove("Bob");             // removes by value
names.RemoveAt(0);               // removes by index

// Check
Console.WriteLine(names.Contains("Charlie")); // True

// Sort and reverse
names.Sort();
names.Reverse();

// Find
string? found = names.Find(n => n.StartsWith("D")); // "Diana"

// Convert to array
string[] arr = names.ToArray();

// Initialize with values
var scores = new List<int> { 85, 92, 78, 95, 88 };
```

---

### 5.3 Dictionary\<TKey, TValue\>

Stores **key-value pairs**. Keys are unique.

```csharp
var phonebook = new Dictionary<string, string>();

// Add entries
phonebook.Add("Alice", "555-0101");
phonebook["Bob"] = "555-0202";   // alternative syntax

// Access
string alicePhone = phonebook["Alice"];

// Safe access — avoids KeyNotFoundException
if (phonebook.TryGetValue("Charlie", out string? phone))
    Console.WriteLine($"Charlie: {phone}");
else
    Console.WriteLine("Charlie not found.");

// Check
Console.WriteLine(phonebook.ContainsKey("Bob")); // True

// Remove
phonebook.Remove("Bob");

// Iterate
foreach (KeyValuePair<string, string> entry in phonebook)
    Console.WriteLine($"{entry.Key}: {entry.Value}");

// Shorthand with var
foreach (var (name, number) in phonebook)
    Console.WriteLine($"{name}: {number}");

// Count
Console.WriteLine(phonebook.Count);
```

---

### 5.4 HashSet\<T\>

A collection of **unique elements** with O(1) lookup.

```csharp
var set1 = new HashSet<int> { 1, 2, 3, 4, 5 };
var set2 = new HashSet<int> { 3, 4, 5, 6, 7 };

set1.Add(6);         // { 1, 2, 3, 4, 5, 6 }
set1.Add(3);         // no effect — 3 already exists

Console.WriteLine(set1.Contains(4)); // True

// Set operations
set1.UnionWith(set2);        // adds all from set2
set1.IntersectWith(set2);    // keeps only common elements
set1.ExceptWith(set2);       // removes elements in set2
```

---

### 5.5 Queue\<T\> and Stack\<T\>

```csharp
// Queue — First In, First Out (FIFO)
var queue = new Queue<string>();
queue.Enqueue("Task 1");
queue.Enqueue("Task 2");
queue.Enqueue("Task 3");

Console.WriteLine(queue.Peek());    // "Task 1" — look without removing
string next = queue.Dequeue();      // removes and returns "Task 1"

// Stack — Last In, First Out (LIFO)
var stack = new Stack<int>();
stack.Push(10);
stack.Push(20);
stack.Push(30);

Console.WriteLine(stack.Peek());    // 30
int top = stack.Pop();              // removes and returns 30
```

---

### :pencil: Section 5 — Exercises

1. Create a `List<int>` with 10 random numbers. Sort it, find the min, max, and average without using LINQ.
2. Build a simple word-frequency counter: given a sentence string, split it into words and count how many times each word appears using a `Dictionary<string, int>`.
3. Given two `List<string>` of names, find the names that appear in **both** lists (intersection) and names that appear in **only one** of them — implement both using `HashSet`.

---

## Section 6 — Methods <a name = "section-6"></a>

### 6.1 Defining and Calling Methods

```csharp
// Syntax: [modifier] [return_type] MethodName([parameters])
// {
//     // body
//     return value; // if not void
// }

// Simple method with return value
static int Add(int a, int b)
{
    return a + b;
}

// Void method — no return value
static void PrintSeparator(char ch = '-', int length = 40)
{
    Console.WriteLine(new string(ch, length));
}

// Calling
int sum = Add(3, 7);          // 10
PrintSeparator();              // uses defaults
PrintSeparator('=', 20);       // custom values
PrintSeparator(length: 10);    // named argument
```

---

### 6.2 Method Features

```csharp
// Expression-bodied method (C# 6+) — shorthand for single expressions
static int Square(int x) => x * x;
static string Greet(string name) => $"Hello, {name}!";

// Method overloading — same name, different parameters
static double Area(double radius) => Math.PI * radius * radius;
static double Area(double width, double height) => width * height;
static double Area(double a, double b, double c)  // triangle (Heron's formula)
{
    double s = (a + b + c) / 2;
    return Math.Sqrt(s * (s - a) * (s - b) * (s - c));
}

// params — variable number of arguments
static int Sum(params int[] numbers)
{
    int total = 0;
    foreach (int n in numbers) total += n;
    return total;
}
Console.WriteLine(Sum(1, 2, 3, 4, 5)); // 15

// out parameters — return multiple values
static bool Divide(int a, int b, out int quotient, out int remainder)
{
    if (b == 0) { quotient = 0; remainder = 0; return false; }
    quotient = a / b;
    remainder = a % b;
    return true;
}
if (Divide(17, 5, out int q, out int r))
    Console.WriteLine($"17 / 5 = {q} remainder {r}"); // 3 remainder 2

// ref parameters — pass by reference
static void Swap(ref int x, ref int y)
{
    int temp = x;
    x = y;
    y = temp;
}
int p = 10, s = 20;
Swap(ref p, ref s);
Console.WriteLine($"{p}, {s}"); // 20, 10
```

---

### 6.3 Lambda Expressions and Delegates

```csharp
// Delegate — a type that represents a method signature
delegate int Operation(int a, int b);

Operation add = (a, b) => a + b;
Operation mul = (a, b) => a * b;

Console.WriteLine(add(3, 4)); // 7
Console.WriteLine(mul(3, 4)); // 12

// Built-in delegate types
Func<int, int, int> subtract = (a, b) => a - b;   // has return value
Action<string> print = msg => Console.WriteLine(msg); // void
Predicate<int> isEven = n => n % 2 == 0;           // returns bool

// Using them
Console.WriteLine(subtract(10, 4)); // 6
print("Hello from Action!");
Console.WriteLine(isEven(6));  // True

// Passing methods as arguments
static int ApplyOperation(int x, int y, Func<int, int, int> operation)
    => operation(x, y);

Console.WriteLine(ApplyOperation(5, 3, (a, b) => a + b));   // 8
Console.WriteLine(ApplyOperation(5, 3, (a, b) => a * b));   // 15
Console.WriteLine(ApplyOperation(5, 3, Math.Max));           // 5
```

---

### :pencil: Section 6 — Exercises

1. Write an overloaded method `Max` that works with `int`, `double`, and `string` (alphabetically).
2. Create a method `ParseDate(string input, out int day, out int month, out int year)` that splits a date string like `"25/12/2024"` into its parts.
3. Write a method `Filter(List<int> numbers, Predicate<int> condition)` that returns a new list containing only elements that satisfy the condition. Test it with "greater than 10" and "is even".

---

## Section 7 — Object-Oriented Programming <a name = "section-7"></a>

### 7.1 Classes and Objects

```csharp
public class Person
{
    // Fields (private by convention — use properties for access)
    private string _name;
    private int _age;

    // Constructor
    public Person(string name, int age)
    {
        _name = name;
        _age  = age;
    }

    // Properties
    public string Name
    {
        get => _name;
        set => _name = value ?? throw new ArgumentNullException(nameof(value));
    }

    public int Age
    {
        get => _age;
        set
        {
            if (value < 0 || value > 150)
                throw new ArgumentOutOfRangeException(nameof(value));
            _age = value;
        }
    }

    // Auto-implemented property (shorthand)
    public string Email { get; set; } = string.Empty;

    // Read-only property
    public bool IsAdult => _age >= 18;

    // Method
    public void Introduce()
        => Console.WriteLine($"Hi, I'm {_name}, {_age} years old.");

    // Override ToString (from object)
    public override string ToString() => $"Person({_name}, {_age})";
}

// Creating objects
var alice = new Person("Alice", 30);
alice.Introduce();
Console.WriteLine(alice.IsAdult);  // True
Console.WriteLine(alice);          // Person(Alice, 30)

// Object initializer syntax
var bob = new Person("Bob", 25) { Email = "bob@example.com" };
```

---

### 7.2 Encapsulation

Encapsulation means **hiding internal state** and exposing only what is necessary through a public interface.

```csharp
public class BankAccount
{
    private decimal _balance;
    private readonly List<string> _transactions = new();

    public string Owner { get; }
    public decimal Balance => _balance; // read-only from outside

    public BankAccount(string owner, decimal initialBalance = 0)
    {
        Owner    = owner;
        _balance = initialBalance;
        _transactions.Add($"Account opened with {initialBalance:C}");
    }

    public void Deposit(decimal amount)
    {
        if (amount <= 0)
            throw new ArgumentException("Deposit amount must be positive.", nameof(amount));

        _balance += amount;
        _transactions.Add($"Deposited {amount:C} — Balance: {_balance:C}");
    }

    public void Withdraw(decimal amount)
    {
        if (amount <= 0)
            throw new ArgumentException("Withdrawal amount must be positive.");
        if (amount > _balance)
            throw new InvalidOperationException("Insufficient funds.");

        _balance -= amount;
        _transactions.Add($"Withdrew {amount:C} — Balance: {_balance:C}");
    }

    public IReadOnlyList<string> GetHistory() => _transactions.AsReadOnly();
}
```

---

### 7.3 Inheritance

```csharp
// Base (parent) class
public class Animal
{
    public string Name  { get; set; }
    public int    Age   { get; set; }

    public Animal(string name, int age)
    {
        Name = name;
        Age  = age;
    }

    // virtual — can be overridden in child classes
    public virtual void Speak()
        => Console.WriteLine($"{Name} makes a generic sound.");

    public virtual string Describe()
        => $"{Name} ({Age} years old)";
}

// Derived (child) class
public class Dog : Animal
{
    public string Breed { get; set; }

    // base() calls the parent constructor
    public Dog(string name, int age, string breed)
        : base(name, age)
    {
        Breed = breed;
    }

    // override — replace the parent implementation
    public override void Speak()
        => Console.WriteLine($"{Name} barks: Woof! Woof!");

    public override string Describe()
        => $"{base.Describe()} — Breed: {Breed}";
}

public class Cat : Animal
{
    public bool IsIndoor { get; set; }

    public Cat(string name, int age, bool isIndoor)
        : base(name, age) => IsIndoor = isIndoor;

    public override void Speak()
        => Console.WriteLine($"{Name} meows: Meoow~");
}

// Polymorphism — treat different types uniformly via base class
var animals = new List<Animal>
{
    new Dog("Rex",      3, "German Shepherd"),
    new Cat("Whiskers", 5, true),
    new Animal("Bird",  1)
};

foreach (var animal in animals)
{
    animal.Speak();  // calls the correct override for each
    Console.WriteLine(animal.Describe());
}
```

---

### 7.4 Interfaces

An **interface** defines a contract that classes must fulfill.

```csharp
public interface IShape
{
    // Properties (no implementation)
    string Color { get; set; }

    // Methods (no implementation)
    double Area();
    double Perimeter();

    // Default implementation (C# 8+)
    string Describe() => $"{Color} shape — Area: {Area():F2}, Perimeter: {Perimeter():F2}";
}

public interface IResizable
{
    void Scale(double factor);
}

// A class can implement multiple interfaces
public class Circle : IShape, IResizable
{
    public string Color { get; set; }
    private double _radius;

    public Circle(double radius, string color = "Red")
    {
        _radius = radius;
        Color   = color;
    }

    public double Area()      => Math.PI * _radius * _radius;
    public double Perimeter() => 2 * Math.PI * _radius;
    public void Scale(double factor) => _radius *= factor;
}

public class Rectangle : IShape, IResizable
{
    public string Color { get; set; }
    private double _width, _height;

    public Rectangle(double width, double height, string color = "Blue")
    {
        _width  = width;
        _height = height;
        Color   = color;
    }

    public double Area()      => _width * _height;
    public double Perimeter() => 2 * (_width + _height);
    public void Scale(double factor) { _width *= factor; _height *= factor; }
}

// Using the interface as the type
IShape shape = new Circle(5.0);
Console.WriteLine(shape.Describe()); // uses default implementation
```

---

### 7.5 Abstract Classes

An **abstract class** is halfway between a regular class and an interface — it can have both abstract methods and concrete implementations.

```csharp
public abstract class Vehicle
{
    // Properties with implementation
    public string Brand { get; set; }
    public int    Year  { get; set; }
    public int    Speed { get; protected set; }

    protected Vehicle(string brand, int year)
    {
        Brand = brand;
        Year  = year;
    }

    // Abstract method — NO implementation, MUST be overridden
    public abstract void StartEngine();
    public abstract double FuelCostPer100Km();

    // Concrete method — shared by all vehicles
    public void Accelerate(int amount)
    {
        Speed += amount;
        Console.WriteLine($"{Brand} accelerating... Speed: {Speed} km/h");
    }

    public override string ToString() => $"{Year} {Brand}";
}

public class ElectricCar : Vehicle
{
    private double _batteryCapacityKwh;

    public ElectricCar(string brand, int year, double batteryKwh)
        : base(brand, year)
    {
        _batteryCapacityKwh = batteryKwh;
    }

    public override void StartEngine()
        => Console.WriteLine($"{Brand}: Silent hum... Electric motor active.");

    public override double FuelCostPer100Km()
        => _batteryCapacityKwh * 0.8; // approx kWh per 100km
}

public class GasCar : Vehicle
{
    private double _engineLiters;

    public GasCar(string brand, int year, double engineLiters)
        : base(brand, year)
    {
        _engineLiters = engineLiters;
    }

    public override void StartEngine()
        => Console.WriteLine($"{Brand}: Vroom! {_engineLiters}L engine started.");

    public override double FuelCostPer100Km()
        => _engineLiters * 8; // approx liters per 100km
}
```

> **Abstract vs Interface:** Use an **abstract class** when classes share common state/behavior. Use an **interface** when you want to define a pure contract that unrelated classes can implement.

---

### 7.6 Static Members and Singleton

```csharp
public class MathHelper
{
    // Static constant
    public static readonly double GoldenRatio = 1.6180339887;

    // Static method — no instance needed
    public static bool IsPrime(int n)
    {
        if (n < 2) return false;
        for (int i = 2; i <= Math.Sqrt(n); i++)
            if (n % i == 0) return false;
        return true;
    }

    public static int Fibonacci(int n) =>
        n <= 1 ? n : Fibonacci(n - 1) + Fibonacci(n - 2);
}

Console.WriteLine(MathHelper.IsPrime(17)); // True
Console.WriteLine(MathHelper.Fibonacci(8)); // 21

// Singleton pattern — only one instance can exist
public sealed class AppConfig
{
    private static AppConfig? _instance;
    private static readonly object _lock = new();

    public string AppName { get; set; } = "MyApp";
    public string Version  { get; set; } = "1.0.0";

    private AppConfig() { }

    public static AppConfig Instance
    {
        get
        {
            lock (_lock)
            {
                _instance ??= new AppConfig();
                return _instance;
            }
        }
    }
}

AppConfig.Instance.AppName = "ProductsAPI";
Console.WriteLine(AppConfig.Instance.AppName); // "ProductsAPI"
```

---

### :pencil: Section 7 — Exercises

1. Design a `LibraryBook` class with `Title`, `Author`, `ISBN`, and `IsAvailable`. Add `Checkout()` and `Return()` methods that change availability.
2. Create an `IPayable` interface with `CalculatePay()`. Implement it in `FullTimeEmployee` (monthly salary) and `Contractor` (hourly rate × hours worked).
3. Build an abstract class `Shape` with abstract methods `Area()` and `Perimeter()`. Implement `Triangle`, `Circle`, and `Square`. Create a method that accepts a `List<Shape>` and prints the total area.
4. Implement a static class `StringUtils` with methods: `IsPalindrome(string)`, `CountVowels(string)`, and `Reverse(string)`.

---

## Section 8 — Generics and LINQ <a name = "section-8"></a>

### 8.1 Generics

Generics let you write **type-safe, reusable code** without knowing the specific type at write-time.

```csharp
// Generic method
static T GetMax<T>(T a, T b) where T : IComparable<T>
    => a.CompareTo(b) >= 0 ? a : b;

Console.WriteLine(GetMax(3, 7));          // 7
Console.WriteLine(GetMax(3.14, 2.71));   // 3.14
Console.WriteLine(GetMax("apple", "banana")); // banana

// Generic class
public class Pair<T1, T2>
{
    public T1 First  { get; set; }
    public T2 Second { get; set; }

    public Pair(T1 first, T2 second)
    {
        First  = first;
        Second = second;
    }

    public void Swap(out T1 f, out T2 s) { f = First; s = Second; }

    public override string ToString() => $"({First}, {Second})";
}

var point = new Pair<int, int>(3, 7);
var entry = new Pair<string, double>("Pi", 3.14);
Console.WriteLine(point); // (3, 7)
Console.WriteLine(entry); // (Pi, 3.14)

// Generic stack implementation
public class Stack<T>
{
    private readonly List<T> _items = new();

    public int Count => _items.Count;
    public bool IsEmpty => _items.Count == 0;

    public void Push(T item) => _items.Add(item);

    public T Pop()
    {
        if (IsEmpty) throw new InvalidOperationException("Stack is empty.");
        var item = _items[^1];
        _items.RemoveAt(_items.Count - 1);
        return item;
    }

    public T Peek() => IsEmpty
        ? throw new InvalidOperationException("Stack is empty.")
        : _items[^1];
}
```

---

### 8.2 LINQ — Language Integrated Query

LINQ provides a **uniform query syntax** for filtering, transforming, and aggregating data in collections.

```csharp
using System.Linq;

var numbers = Enumerable.Range(1, 20).ToList(); // 1..20

// --- FILTERING ---
var evens    = numbers.Where(n => n % 2 == 0);
var bigNums  = numbers.Where(n => n > 15);

// --- PROJECTION (transform) ---
var squares  = numbers.Select(n => n * n);
var strings  = numbers.Select(n => $"Item {n}");

// --- ORDERING ---
var desc     = numbers.OrderByDescending(n => n);
var words    = new[] { "banana", "apple", "cherry", "date" };
var sorted   = words.OrderBy(w => w);           // alphabetical
var byLength = words.OrderBy(w => w.Length).ThenBy(w => w);

// --- AGGREGATION ---
int sum    = numbers.Sum();
double avg = numbers.Average();
int max    = numbers.Max();
int min    = numbers.Min();
int count  = numbers.Count(n => n % 2 == 0); // 10

// --- CHAINING ---
var result = numbers
    .Where(n => n % 2 != 0)     // odd numbers
    .Select(n => n * n)          // square them
    .Where(n => n > 50)          // only > 50
    .OrderBy(n => n)             // sort ascending
    .Take(5);                    // first 5
// [81, 121, 169, 225, 289]

// --- ELEMENT ACCESS ---
int first  = numbers.First(n => n > 10);   // 11 — throws if not found
int? found = numbers.FirstOrDefault(n => n > 100); // null (default) if not found
bool any   = numbers.Any(n => n > 18);     // True
bool all   = numbers.All(n => n > 0);      // True

// --- GROUPING ---
var grouped = words.GroupBy(w => w.Length);
foreach (var group in grouped)
{
    Console.WriteLine($"Length {group.Key}: {string.Join(", ", group)}");
}

// --- WORKING WITH OBJECTS ---
var people = new List<(string Name, int Age, string City)>
{
    ("Alice",   30, "NYC"),
    ("Bob",     25, "LA"),
    ("Charlie", 35, "NYC"),
    ("Diana",   28, "LA"),
    ("Eve",     22, "NYC"),
};

// Complex query
var nycAdults = people
    .Where(p => p.City == "NYC" && p.Age >= 25)
    .OrderBy(p => p.Age)
    .Select(p => new { p.Name, p.Age });

// Query syntax (alternative to method syntax)
var query =
    from p in people
    where p.Age > 25
    orderby p.Name
    select new { p.Name, p.City };
```

---

### :pencil: Section 8 — Exercises

1. Using LINQ on a `List<int>`, write a single LINQ chain that: filters primes, sorts descending, skips the first 2, and takes the next 3.
2. Given a `List<string>` of product names, use LINQ to: group them by their first letter, count each group, and sort by group size descending.
3. Create a generic `Repository<T>` class that stores items in a `List<T>` and exposes `Add`, `Remove`, `FindById` (with a `Func<T, int>` key selector), and `GetAll`.

---

## Section 9 — Modern C# Features <a name = "section-9"></a>

### 9.1 Records (C# 9+)

Records are **immutable reference types** designed for data. They automatically generate `Equals`, `GetHashCode`, and `ToString`.

```csharp
// Record — immutable by default
public record Person(string Name, int Age);

var alice = new Person("Alice", 30);
var alice2 = new Person("Alice", 30);

Console.WriteLine(alice == alice2);    // True — value equality
Console.WriteLine(alice);             // Person { Name = Alice, Age = 30 }

// non-destructive mutation
var olderAlice = alice with { Age = 31 };
Console.WriteLine(olderAlice); // Person { Name = Alice, Age = 31 }
Console.WriteLine(alice.Age);  // 30 — original unchanged

// Record struct (value type)
public record struct Point(double X, double Y);
```

---

### 9.2 Pattern Matching

```csharp
// Type patterns
object obj = 42;
if (obj is int number)
    Console.WriteLine($"Integer: {number}");

// Switch expression with patterns
static string Classify(object o) => o switch
{
    int n when n < 0  => "Negative integer",
    int n when n == 0 => "Zero",
    int n             => $"Positive integer: {n}",
    double d          => $"Double: {d:F2}",
    string s          => $"String of length {s.Length}",
    null              => "Null",
    _                 => "Unknown"
};

// Property pattern
public record Order(string Status, decimal Total);

static string GetDiscount(Order order) => order switch
{
    { Status: "VIP",      Total: > 1000 } => "20% discount",
    { Status: "Regular",  Total: > 500  } => "5% discount",
    { Status: "VIP"                      } => "10% discount",
    _                                      => "No discount"
};

// List pattern (C# 11)
int[] arr = { 1, 2, 3 };
string desc = arr switch
{
    []          => "Empty",
    [var x]     => $"One element: {x}",
    [var x, var y] => $"Two elements: {x}, {y}",
    [1, 2, ..]  => "Starts with 1, 2",
    _           => "Other"
};
```

---

### 9.3 Async / Await

Asynchronous programming prevents blocking the current thread while waiting for I/O operations.

```csharp
using System.Net.Http;
using System.Threading.Tasks;

// async method — must return Task, Task<T>, or void (for event handlers only)
static async Task<string> FetchDataAsync(string url)
{
    using var client = new HttpClient();
    // await — suspends the method until the task completes, without blocking the thread
    string data = await client.GetStringAsync(url);
    return data;
}

// Multiple tasks in parallel
static async Task RunParallelAsync()
{
    var task1 = FetchDataAsync("https://api.example.com/users");
    var task2 = FetchDataAsync("https://api.example.com/products");

    // WhenAll — waits for ALL tasks to complete
    string[] results = await Task.WhenAll(task1, task2);
    Console.WriteLine($"Users: {results[0].Length} chars");
    Console.WriteLine($"Products: {results[1].Length} chars");
}

// Task.WhenAny — continue when the first task completes
static async Task<string> FastestResponseAsync(IEnumerable<string> urls)
{
    var tasks = urls.Select(url => FetchDataAsync(url));
    Task<string> first = await Task.WhenAny(tasks);
    return await first;
}

// Cancellation
static async Task LongOperationAsync(CancellationToken ct)
{
    for (int i = 0; i < 100; i++)
    {
        ct.ThrowIfCancellationRequested(); // cooperative cancellation
        await Task.Delay(100, ct);
        Console.WriteLine($"Step {i + 1}");
    }
}

// Usage
using var cts = new CancellationTokenSource(TimeSpan.FromSeconds(5));
try
{
    await LongOperationAsync(cts.Token);
}
catch (OperationCanceledException)
{
    Console.WriteLine("Operation was cancelled.");
}
```

---

### 9.4 Exception Handling

```csharp
// Basic try-catch-finally
try
{
    int[] arr = new int[3];
    arr[10] = 5; // IndexOutOfRangeException
}
catch (IndexOutOfRangeException ex)
{
    Console.WriteLine($"Index error: {ex.Message}");
}
catch (Exception ex) when (ex.Message.Contains("special")) // exception filter
{
    Console.WriteLine("Special case error");
}
catch (Exception ex)
{
    Console.WriteLine($"General error: {ex.Message}");
    throw; // re-throw preserving stack trace
}
finally
{
    Console.WriteLine("Always runs — great for cleanup.");
}

// Custom exception
public class ValidationException : Exception
{
    public string Field { get; }

    public ValidationException(string field, string message)
        : base(message)
    {
        Field = field;
    }
}

// Throwing
static void ValidateAge(int age)
{
    if (age < 0 || age > 150)
        throw new ValidationException("Age", $"Age {age} is out of valid range.");
}

// Using statement — auto-dispose (IDisposable)
using var file = new System.IO.StreamWriter("output.txt");
file.WriteLine("Hello from C#!");
// file.Dispose() is called automatically at the end of scope
```

---

### :pencil: Section 9 — Exercises

1. Create a `Product` record with `Id`, `Name`, `Price`, and `Category`. Make a list of 5 products and use pattern matching to classify each as "Cheap" (< $20), "Mid-range" ($20–$100), or "Expensive" (> $100).
2. Write an async method `DownloadAllAsync(List<string> urls)` that downloads all URLs concurrently and returns a list of `(url, contentLength)` tuples. Use `Task.WhenAll`.
3. Design a custom `NotFoundException` class that includes a resource type and ID. Write a method that throws it when an item is not found in a dictionary, then handle it gracefully in a `try-catch`.

---

## :books: References <a name = "references"></a>

| Resource | Link |
|----------|------|
| C# Documentation (Microsoft) | [docs.microsoft.com/dotnet/csharp](https://docs.microsoft.com/en-us/dotnet/csharp/) |
| C# Language Reference | [docs.microsoft.com/csharp/language-reference](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/) |
| .NET and C# for Beginners Roadmap | [roadmap.sh/ai/course](https://roadmap.sh/ai/course/net-and-c-for-beginners-a-comprehensive-guide) |
| Microsoft Learn — C# | [learn.microsoft.com/dotnet/csharp](https://learn.microsoft.com/en-us/dotnet/csharp/) |
| C# in Depth (Jon Skeet) | [csharpindepth.com](https://csharpindepth.com/) |
| .NET Interactive Notebooks | [github.com/dotnet/interactive](https://github.com/dotnet/interactive) |
| Tour of C# | [docs.microsoft.com/dotnet/csharp/tour-of-csharp](https://docs.microsoft.com/en-us/dotnet/csharp/tour-of-csharp/) |

---

## :page_with_curl: License

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)

This project is licensed under the MIT License.

---

<p align="center">Made with ❤️ for C# learners worldwide</p>
