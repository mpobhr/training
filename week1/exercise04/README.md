# Multiple class and reference

## instruction
```cs
using System;

class Program
{
    public static void Main(string[] args)
    {
        Hello.Say("Hello .NET 5.0");
    }
}

class Hello
{
    public static void Say(string message)
    {
        Console.WriteLine($"Hello {message}");
    }
}
```