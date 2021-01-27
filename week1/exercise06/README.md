# Class Instant, Method and Property

## instruction
```cs
using System;

    class Program
    {
        public static void Main(string[] args)
        {
            var fn = new Hello("Hello .NET");
            fn.Say();
        }        
    }
}


    class Hello
    {
        private readonly string _message;
        public Hello(string message) {
            _message = message;
        }

        public void Say()
        {
            Console.WriteLine($"Hello {message}");
        }
    }

```