# Namespace

## instruction
```cs
using System;

namespace First
{
    class Program
    {
        public static void Main(string[] args)
        {
            Second.Hello.Say("Hello .NET 5.0");
        }        
    }

    class Hello {

    }
}

namespace Second
{
    class Hello
    {
        public static void Say(string message)
        {
            Console.WriteLine($"Hello {message}");
        }
    }
}
```