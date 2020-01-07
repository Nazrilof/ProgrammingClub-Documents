# Misc. C# Stuff

Just a couple things to wrap up core C# features.

**Table of Contents**
* [Enums](#Enums)
* [Structs](#Structs)
* [Interfaces](Interfaces)
* [Generics](#Generics)
* [Resources](#Resources)

## Enums



## Structs



# Interfaces

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



## Resources

* [Tutorialspoint C#](https://www.tutorialspoint.com/csharp/index.htm)
* [Brackeys C# Playlist](https://www.youtube.com/playlist?list=PLPV2KyIb3jR6ZkG8gZwJYSjnXxmfPAl51)
