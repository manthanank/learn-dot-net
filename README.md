# Learn Dot Net

### **Introduction to .NET**

.NET is a free, open-source, cross-platform framework developed by Microsoft for building applications. It supports multiple programming languages like C#, VB.NET, and F#. The framework provides a unified environment for creating a wide range of applications, such as:

- **Desktop Applications** using Windows Forms or WPF.
- **Web Applications** using ASP.NET Core.
- **Mobile Applications** using Xamarin.
- **Cloud Services** using Azure.

**Key Components:**

1. **Common Language Runtime (CLR):** Manages code execution, memory, and garbage collection.
2. **Base Class Library (BCL):** A collection of reusable classes, interfaces, and value types.
3. **.NET SDK:** A set of tools and libraries to build applications.

### **Hands-on Demo**

**Scenario:** Create a simple console application to demonstrate .NET basics.

1. Install .NET SDK from [dotnet.microsoft.com](https://dotnet.microsoft.com/).
2. Create a new project:

   ```bash
   dotnet new console -n HelloWorldApp
   cd HelloWorldApp
   dotnet run
   ```

3. Modify the `Program.cs`:

   ```csharp
   Console.WriteLine("Hello, .NET World!");
   ```

4. Execute it using:

   ```bash
   dotnet run
   ```

### **Looping Control Structure**

**Types of Loops:**

1. **For Loop:**

   ```csharp
   for (int i = 0; i < 5; i++)
   {
       Console.WriteLine($"Iteration {i}");
   }
   ```

2. **While Loop:**

   ```csharp
   int i = 0;
   while (i < 5)
   {
       Console.WriteLine($"Iteration {i}");
       i++;
   }
   ```

3. **Do-While Loop:**

   ```csharp
   int i = 0;
   do
   {
       Console.WriteLine($"Iteration {i}");
       i++;
   } while (i < 5);
   ```

4. **Foreach Loop:**

   ```csharp
   string[] fruits = { "Apple", "Banana", "Cherry" };
   foreach (var fruit in fruits)
   {
       Console.WriteLine(fruit);
   }
   ```

### **Boxing and Unboxing**

- **Boxing:** Converting a value type to a reference type.

   ```csharp
   int num = 10;
   object obj = num;  // Boxing
   ```

- **Unboxing:** Extracting a value type from an object.

   ```csharp
   int unboxedNum = (int)obj;  // Unboxing
   ```

### **Method Overloading**

Defining multiple methods with the same name but different parameters.

```csharp
class Calculator
{
    public int Add(int a, int b) => a + b;
    public double Add(double a, double b) => a + b;
}
```

### **Constructors**

A constructor initializes an object of a class.

```csharp
class Person
{
    public string Name { get; }
    public Person(string name) { Name = name; }
}
```

### **Static Methods**

Static methods belong to the class, not an instance.

```csharp
class MathUtil
{
    public static int Square(int num) => num * num;
}
```

### **Inheritance**

Derived classes inherit members of the base class.

```csharp
class Animal { public void Eat() => Console.WriteLine("Eating"); }
class Dog : Animal { public void Bark() => Console.WriteLine("Barking"); }
```

### **Polymorphism**

1. **Compile-time Polymorphism (Method Overloading).**
2. **Runtime Polymorphism (Method Overriding).**

   ```csharp
   class Parent { public virtual void Speak() => Console.WriteLine("Parent speaks."); }
   class Child : Parent { public override void Speak() => Console.WriteLine("Child speaks."); }
   ```

### **String vs StringBuilder**

1. **String:** Immutable.

   ```csharp
   string str = "Hello";
   str += " World";  // New string is created.
   ```

2. **StringBuilder:** Mutable.

   ```csharp
   StringBuilder sb = new StringBuilder("Hello");
   sb.Append(" World");  // Modifies the existing object.
   ```

### **Exception Handling**

Handle runtime errors using try-catch-finally.

```csharp
try
{
    int result = 10 / 0;
}
catch (DivideByZeroException ex)
{
    Console.WriteLine(ex.Message);
}
finally
{
    Console.WriteLine("Execution finished.");
}
```

### **Abstract Class**

An abstract class provides a blueprint for derived classes.

```csharp
abstract class Shape
{
    public abstract double CalculateArea();
}
class Circle : Shape
{
    public double Radius { get; set; }
    public override double CalculateArea() => Math.PI * Radius * Radius;
}
```

### **Connected Architecture and SQL Command**

Connected architecture communicates directly with the database using `SqlConnection` and `SqlCommand`.

```csharp
using System.Data.SqlClient;

string connectionString = "your_connection_string";
using (SqlConnection connection = new SqlConnection(connectionString))
{
    connection.Open();
    SqlCommand command = new SqlCommand("SELECT * FROM Users", connection);
    SqlDataReader reader = command.ExecuteReader();
    while (reader.Read())
    {
        Console.WriteLine(reader["Username"]);
    }
}
```

### **LINQ and Lambda Expressions**

**LINQ (Language-Integrated Query):**

```csharp
int[] numbers = { 1, 2, 3, 4, 5 };
var evenNumbers = numbers.Where(n => n % 2 == 0);
```

**Lambda Expressions:**

```csharp
Func<int, int> square = x => x * x;
Console.WriteLine(square(5));  // Output: 25
```
