# Polymorphism

- Polymorphism in OOP provides the ability to have a class that can have many implementations with the same name.
- There are two types of polymorphism
  1. Static / Compile Time
  1. Dynamic / Runtime

## Static Polymorphism

- Static polymorphism is also known as early binding
- Method overloading allows us to access methods that have the same name but perform different actions
- Look at the following example below

```csharp
public class Animal
  // Here we have two functions called Type, but with different params
  public string Type(string mammal)
  {
    return "Is a mammal";
  }
  public string Type(string reptile, bool hasTail)
  {
    return "Is a reptile";
  }

class Program
{
  static void Main(string[] args)
  {
    Animal name = new Animal();
    // We are able to use name.Type and are able to access either function
    // This is static polymorphism
    string mammal = name.Type("Cow");
    string reptile = name.Type("Turtle", true)
  }
}
```

## Dynamic Polymorphism

- Also known as late binding
- Method overriding is also used here
- We use inheritance to access properties of the inherited class
- Look at the following example

```csharp
public class Drawing
{
    public virtual double Area()
   {
         return 0;
   }
}

// We override with the Drawing class to be able to
public class Circle : Drawing
{
    public double Radius { get; set; }
    public Circle()
    {
        Radius = 5;
    }
    public override double Area()
    {
        return (3.14) * Math.Pow(Radius, 2);
    }
}

public class Square : Drawing
{
    public double Length { get; set; }
    public Square()
    {
        Length = 6;
    }
    public override double Area()
    {
        return Math.Pow(Length, 2);
    }
}

class Program
{
    static void Main(string[] args)
    {

        Drawing circle = new Circle();
        Console.WriteLine("Area :" + circle.Area());

        Drawing square = new Square();
        Console.WriteLine("Area :" + square.Area());
    }
}

```
