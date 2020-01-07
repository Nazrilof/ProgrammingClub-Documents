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
