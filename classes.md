# Classes in C#

**Table of Contents**
* [Basics](#Basics)
* [Properties](#Properties)
* [Methods](#Methods)
* [Constructor](#Constructor)
  * [Parameterized Constructor](#Parameterized-Constructor)
* [Destructor](#Destructor)
* [Resources](#Resources)

## Basics

A class is an abstract peice of data that contains peices of data that is used in reference to the main peice of data. For example, you could have a class of car with a color and you can get that color by saying "color of car" rather than just car. A class has an identity: the name that is used to reference the class, properties: peices of information about the thing represented by the class, and methods: things the class does.

Just like when we were creating methods, we will be going outside of the main method to define a class. However, we will also be going outside of the **main class**. Repl, by default, does not include a "namespace", but you would be staying inside of that if it were included (don't worry about this for now).

Defining a class is quite simple; it has a similar structure to declaring a variable. You start by putting the keyword `class` followed by whatever you want to name it (just like a variable). It is conventional to capitalize the first letter of a class and any following words (ex: "Planet Earth" becomes "PlanetEarth"), though this is not required.

(This example includes the entire file, but future examples will only show the relavent code)

```C#
using System;

class Car { // This is a new class

}

class MainClass {
  public static void Main (string[] args) {
  
  }
}
```

We now have an empty class called `car`. To use it in our code we will create a new **instance** of the class. This is done by declaring a variable, but the data type will be the name of your class (ex: `Car`) and the keyword `new` followed by the name of the class with parenthesis after it (ex: `Car()`).

```C#
class MainClass {
  public static void Main (string[] args) {
    Car myCar = new Car();
  }
}
```

## Properties

Now that we've created a class, we may want to store some data in it. To do that you'll be defining something called a **property**. Think of properties as variable that have been attatched to a class. The name "property" hints at how it is used: think of a blue car. It can be said that a property of the car is the color blue.

```C#
class Car {
  public string color = "Blue";
}
```

The car class now has a property called `color`. To access this property on our instance of the car, we'll put the name of our variable (ex: `myCar`) followed by a `.` and the name of the property.

```C#
class MainClass {
  public static void Main (string[] args) {
    Car myCar = new Car();
    
    Console.WriteLine(myCar.color);
    // can also set the color this way (ex: myCar.color = "Red";)
  }
}
```

## Methods

Just like we can attatch variables to classes, we can do the same with methods. In fact, this is exactly what we've done with methods in the past. We've just been adding them to the `Main` class instead of our custom class. 

```C#
class Car {
  public string color = "Blue";
  
  public void setColor(string newColor) {
    color = newColor;
  }
}
```

Now we have a method that will change the color of the car. We can access it very similarly to a property.

```C#
class MainClass {
  public static void Main (string[] args) {
    Car myCar = new Car();
    
    Console.WriteLine(myCar.color); // Should be "Blue"
    
    myCar.setColor("Red");
    
    Console.WriteLine(myCar.color); // Should be "Red"
  }
}
```

## Constructor

We may want to do something as we're creating an instance. To start, we'll create a special method called a **constructor** which will run when the instance is created.

```C#
class Car {
  public string color = "Blue";
  
  public Car() { // This is the constructor
    Console.WriteLine("A new instance of Car has been created");
  }
  
  public void setColor(string newColor) {
    color = newColor;
  }
}
```

### Parameterized Constructor

We may want to, for example, set a property to a specified value as the instance is created. To do this we'll pass a **parameter** into the constructor, just like with arguments in methods. This has a fancy name that you don't need to know: **Parameterized Constructor**.

```C#
class Car {
  public string color;
  
  public Car(string col) {
    Console.WriteLine("A new instance of Car has been created");
    
    color = col;
  }
  
  public void setColor(string newColor) {
    color = newColor;
  }
}
```

Now when we create an instance of the class, we'll add a value for the parameter between the parenthesis.

```C#
class MainClass {
  public static void Main (string[] args) {
    Car myCar = new Car("Yellow");
    
    Console.WriteLine(myCar.color); // Should be "Yellow"
    
  }
}
```

## Destructor

Similar to constructors (run when created): we can create a **destructor**, which will run when the instance is destroyed. To do this we create a method without public and just a `~` with no space after it.

```C#
class Car {
  public string color;
  
  public Car(string col) {
    Console.WriteLine("A new instance of Car has been created");
    
    color = col;
  }
  
  ~Car() { // Destructor
   Console.WriteLine("A physicist assumed spherical car...");
  }
  
  public void setColor(string newColor) {
    color = newColor;
  }
}
```

## Resources

* [Written Tutorial on Classes](https://www.tutorialspoint.com/csharp/csharp_classes.htm)
* [Brackeys Classes](https://www.youtube.com/watch?v=s2hHjpZaSyI)