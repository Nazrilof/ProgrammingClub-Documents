# Misc. C# Stuff

Just a couple things to wrap up core C# features.

**Table of Contents**
* [Casting](#Casting)
* [Enums](#Enums)
* [Structs](#Structs)
* [Interfaces](Interfaces)
* [Generics](#Generics)
* [Resources](#Resources)

## Casting

Converting one datatype into another is known as type casting or, type-conversion. There are two types of casting: Implicit and explicit casting. For example, if you want to store a 'long' value into a simple integer then you can type cast 'long' to 'int'. You can convert the values from one type to another explicitly using the cast operator in explicit casting as follows

```C#
<new_data_type> <variable_name> = (<new_data_type>) <value>;
```

For example you could do,

```C#
double myDouble = 9.78;
int myInt = (int) myDouble;    // Manual casting: double to int

Console.WriteLine(myDouble);   // Outputs 9.78
Console.WriteLine(myInt);      // Outputs 9
```

Implicit casting is automatic.

Implicit Casting Conversions:
char -> int -> long -> float -> double

Explicit Casting Conversions:
double -> float -> long -> int -> char


## Enums

The enum keyword is a new data-type pre-defined in C#. An enumeration is a set of named integer constants. An enumerated type is declared using the enum keyword. The value of the constant is always – unless directly specified otherwise – the position that the constant takes in the enum starting at zero. For example, if you had an enum with the data {The, Earth, Is, Flat}, the keyword The would give the value zero, Earth one, etc.

An enum is defined with the following syntax:

```C#
enum <enum_name> { <List of items seperated by commas> };
```

For example, and enum that lists the days of the week would look like

```C#
enum Days { Sun, Mon, tue, Wed, thu, Fri, Sat };
```

You can define the constant values from the default by doing ending it with a '=' followed by the constant value. For example, if you wanted the enum to start at 1, you could do
```C#
enum Days {
    Sunday = 1
    Monday = 2,
    Tuesday = 3,
    Wednesday = 4,
    Thursday = 5,
    Friday = 6,
    Saturday = 7
};
```
(Note that generally you would not want the enums to start at a non-zero value in a context such as this)

You could simplify this example by removing the "= {pos}" from everything after Sunday as values after will carry the value directly after the previous, it would better to do:
```C#
enum Days {
    Sunday = 1
    Monday,
    Tuesday,
    Wednesday,
    Thursday,
    Friday,
    Saturday
};
```

This would create the exact same enum as in the previous example

If you want to get the value of the enum, you do so by accessing <enum_name>.<item_name> and cast it to an int, for example to get the position in the week of Wednesday from our first example and put in a variable, you would do:
```C#
int wedPos = (int) Days.Wed + 1; // The "+ 1" is because of the enum starting at 0
```

## Structs



## Interfaces

Interfaces allow you to specify names and data types of members of a class. Here's an example of a simple interface:

```C#
public interface Example {
  int amount;
  void addOne();
}
```

Interfaces can be used to force classes to use data types for different variable names. This can be done in the same way a class inherits from another class.

```C#
public interface Example {
  int amount;
  void addOne();
}

public class ExampleClass : Example {
  public int amount;
  
  public Example(int sAmount) {
    amount = sAmount
  }
  
  public void addOne() {
    amount++;
  }
}
```

## Generics

Generics allow you to write a class or method that can work with any data type (integers, chars, etc.). For example, you could create an array that can hold any one type of data, which is specified when you want to use it later in your code. The following is a relatively simple application of this example.

```C#
public class MyGenericArray<T> {
  private T[] array;

  public MyGenericArray(int size) {
     array = new T[size + 1];
  }
  public T getItem(int index) {
     return array[index];
  }
  public void setItem(int index, T value) {
     array[index] = value;
  }
}
```

When used in the code, the data type can be specified 

## Resources

* [Tutorialspoint C#](https://www.tutorialspoint.com/csharp/index.htm)
* [Brackeys C# Playlist](https://www.youtube.com/playlist?list=PLPV2KyIb3jR6ZkG8gZwJYSjnXxmfPAl51)
