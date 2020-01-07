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

Converting one datatype into another is known as type casting or, type-conversion. For example, if you want to store a 'long' value into a simple integer then you can type cast 'long' to 'int'. You can convert the values from one type to another explicitly using the cast operator as follows

```C#
<data_type> 
```

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

## Structs

Structures or **Structs** allow you to create a single variable that holds related data of various types. For example you may want to keep track of information about several books in a library. Each book may have the following attributes –

* Title
* Author
* Genre

A book structure may look as follows:

```C#
struct Books {
   public string title;
   public string author;
   public string genre;
};  
```

You can create many instances of a struct, just like with classes. A structure may be used in code as follows:

```C#
Books book1;

book1.title = "The Way of Kings";
book1.author = "Brandon Sanderson";
book1.genre = "Epic Fantasy";
```

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

## Resources

* [Tutorialspoint C#](https://www.tutorialspoint.com/csharp/index.htm)
* [Brackeys C# Playlist](https://www.youtube.com/playlist?list=PLPV2KyIb3jR6ZkG8gZwJYSjnXxmfPAl51)
