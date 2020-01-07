# Arrays

So far we've worked with several variable types including integers (int) and strings (string). C#, like most programming languages, has a feature known as arrays. These allow us to create a numbered "list" of items stored in one variable.


**Table of Contents**
* [Initalizing](#Initalizing)
* [Getting](#Getting)
* [Updating](#Updating)
* [Wrap Up](#Wrap-Up)
* [Resources](#Resources)

## Initalizing

Declaring an array starts off the same as any other variable: by declaring the data type. This is immediately followed by a set of square brackets `[]` and then a space. After this, as usual, you put the name and an equals sign. On the right of the equal sign is `new` followed by the data type again and square brackets, this time with the number of items that will be in the array. Here's an example:

```C#
string[] names = new string[3];
```

Now this will create an array, but it will be empty. If you want to create an array that already has data in it, you can do the following:

```C#
string[] names = new string[3] { "Cabine", "Eshu", "Dillid" };
```

## Getting

If you want to retrieve data from the array, you put the name of the array (in the example from before it's `names`) followed by square brackets with the **index number**. The **index number** is a number, starting from 0, assigned to each item in the array in order. For example, the item with index 0 in the previous example is `Cabine`. Here's an example of getting an item from an array:

```C#
string[] names = new string[3] { "Cabine", "Eshu", "Dillid" };

names[0] // Should be Cabine
```

Now this is all nice, but how about an example of this in action:

```C#
string[] names = new string[3] { "Cabine", "Eshu", "Dillid" };

Console.WriteLine(names[0] + " is one of the ten fools");
```

## Updating

Just like we can get an item from an array, we can modify it as well. This is pretty similar to getting, so here's an example:

```C#
string[] names = new string[3] { "Cabine", "Eshu", "Dillid" };

names[0] = "Talenelat'Elin";
```

## Wrap Up

Arrays will be quite useful to us when we are making our game. Here's a final example putting everything together:

```C#
string[] names = new string[3] { "Cabine", "Eshu", "Dillid" };

Console.WriteLine(names[0]); // Should be Cabine

names[0] = "Talenelat'Elin";

Console.WriteLine(names[0]); // Should be Talenelat'Elin
```

## Resources

* [Brackeys Video](https://www.youtube.com/watch?v=RQ0JHMGiobo)
* [Quick Overview](https://www.youtube.com/watch?v=BDfO1ryG6Rc)