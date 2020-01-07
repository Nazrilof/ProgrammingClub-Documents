# Classes in C# Cont.

This document continues the notes on classes [from last week](https://gist.github.com/Nazrilof/d9b3db20aee9cedd226f5ac9ea08f40b).

**NOTE** This week, I'm using a new method to more clearly show you the syntax of what we're talking about. For each section, I'll have a general template that looks something like this: `class <child_class> : <parent_class> { ...`. The items surrounded by `<` and `>` are items you would fill in with your own name (ex. `<parent_class>` becomes `Shape`). The `...` simply means more code that isn't relavent, just as you'd expect it to.

Some quick programming vocab: **members** are the properties and/or methods that make up a class.
Also, I've been using "property" to describle what is officially called a **field** in C#. I'll consider changing this in the future.

**Table of Contents**
* [Static Properties](#Static-Properties)
* [Static Methods](#Static-Methods)
* [Inheritance](#Inheritance)
* [Access Modifiers](#Access-Modifiers)
  * [Public](#Public)
  * [Private](#Private)
  * [Protected](#Protected)
* [Resources](#Resources)

## Static Properties

Regardless of how many instances of a class are created, there will only be one copy of any **static** members. These can be accessed directly on a class, without creating an instance of it. [Here](http://tpcg.io/B8J0mT) is an excellent example from Tutorialspoint demonstrating how this works. The syntax is simply adding the keyword static after the access modifier (`<access_modifier> static ...`).

```C#
class ExampleClass {
  public static int num = 1;
}
```

## Static Methods

Static methods share many attributes with static properties. However, the *main* distinction between them and standard methods is static methods can only access static properties. The suntax is essentially the same as static properties.

## Inheritance

**Inheritance** is a very important and useful feature of classes. It allows you to create a new class that "inherits" properties and methods from a **parent class**. This class is called a **child class**. These are also sometimes called the **base** and **derived** classes, respectively. The class a child or derived class inherits from is denoted as: `class <child_class> : <parent_class> { ...`.

Try this out for yourself, make a basic parent class with some propertied and methods, then create a child with some additional properties and methods. Then, create a new instance of the child class and try accessing some of the parent's properties and methods on it. The following example uses a car and a type of car, another common example is a general shape and a specific one, like a rectangle.

```C#
class Car { // Parent class
  public string color = "Blue";
  public int year = 1984;
  public string location = "Garage";
  
  public void drive (string destination) {
   location = destination;
  }
}

class Sedan : Car { // Child class
 public int maxPassengers = 5;
 public bool trunkOpen = false;
 
 public void toggleTrunk () {
  trunkOpen = !trunkOpen;
 }
}
```

## Access Modifiers

Classes, methods, and properties (and some others) all have an **accessibility level**. This controls if outside code can access it. **Access Modifiers** specifies the relation to the class that is necessary for accessing the member element (syntax: `<access_modifier> <return_type> <variable_name> = ...;`). This section will discuss the most common access modifiers: **Public**, **Private**, and **Protected**.

### Public

Public members can be accessed by any other code in the project.

```C#
class ExampleClass {
  public string color = "Very Light Grey";
}
```

Check out [this page](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/public) for how this is useful and more examples.

### Private

Private members can only be access by code in the same class (or struct, but we havent done those yet).

```C#
class ExampleClass {
  private string color = "Very Light Grey";
}
```

Check out [this page](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/private) for how this is useful and more examples.

### Protected

Protected members can only be accessed from code within the same class or a class that is derived from that class (i.e. a child class).

```C#
class ExampleClass {
  protected string color = "Very Light Grey";
}
```

Check out [this page](https://docs.microsoft.com/en-us/dotnet/csharp/language-reference/keywords/protected) for how this is useful and more examples.

## Resources

* [Tutorialspoint C# Classes](https://www.tutorialspoint.com/csharp/csharp_classes.htm)
* [Tutorialspoint C# Inheritance](https://www.tutorialspoint.com/csharp/csharp_inheritance.htm)
* [C# Docs – Static Classes and Static Class Members](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members)
* [C# Docs – Access Modifiers](https://docs.microsoft.com/en-us/dotnet/csharp/programming-guide/classes-and-structs/access-modifiers)