---
layout: default
title: java-arrays
date: 2024-06-30
status: finished
tags: java, programming-languages, arrays
---

## Java - Arrays

Arrays are the ancestors of [[Java - Lists|ArrayList]].

Unlike ArrayList, we don't have to import anything and create a separate object for it to work - arrays are natively supported in Java!

## Creating an array

We can create an array by two ways - either we create it with the elements, or we specify the datatype and size to add them later.

```java
String[] brands = {"espresso", "java", "latte"};

String[] brands = new String[2];
```

### Referring from an array

The reference of an array is the information about the location of the data [i.e. its index].

When we use ``brands[1]`` to access the String ``java``, we mean [go to the beginning of the array and then move forward 1 time. Then return a chunk of data the size of the variable.].

### Using array index for operations

We can use array index to add, access, modify elements.

```java
//adding elements
brands[0] = "espresso";
brands[1] = "java";

//modifying elements
brands[0] = "latte";

//accessing elements
System.out.println(array[0]);
System.out.println(array[1]);
```

#### Accessing the end of the list

Sometimes, we'd want to access the end of the list. We can already do this in ``ArrayList`` using ``IndexOf()``, but now we want to do it with arrays.

If you use negative indices in array [like you would do in python], Java throws an ``ArrayIndexOutOfBoundsException`` error at you. This is because Java doesn't support them in the first place.

- If it were supported, there may be problems such as a program reading the whole memory reserved for itself, index switching to max supported length if unchecked [see Integer Overflow], etc.

We use the workaround of using ``length`` [not a method call] to get the size of the array and subtracting 1 from it.

```java
int lastIndex = brands.length - 1;
```

#### Variable size

## Using an array

### As parameter

You can use arrays as method parameters like this :

```java
public static String printMenu(String[] brands)
{
//statements
}
```
