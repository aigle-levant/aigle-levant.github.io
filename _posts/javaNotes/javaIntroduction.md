---
layout: default
title: java-introduction
date: 2024-06-14
status: finished
tags: java, programming-languages, io
---

## Java - Introduction

``` java
System.out.println("Hello world!");
//this prints out Hello world!
```

Let's expand this further into...

```java
public class helloworld
{
    public static void main(String[] args)
    {
        System.out.println("Hello world!");
    }
}
```

> Alright, now that's a huge program for a mere 'hello world'! Why is that so?

### Java and its quirks

Java is verbose when compared to Python, C, JS, etc.

Compare our previous code with...

```python
print("Hello world!")
```

and

```c
#include <stdio.h>
int main (void)
{
    printf("Hello world!");
}
```

Short and simple do not belong in the books of this language. This makes it a slightly difficult choice for any beginner programmer, but an excellent choice for enterprises [they NEED that verbosity as it makes clear a lot of stuff!].

Let's go back to our code:

```java
public class helloworld
{
    public static void main(String[] args)
    {
        System.out.println("Hello world!");
    }
}
```

> Just like C and C++, you use a main function. But, unlike them, you also have to define a class, whose name is the same as the file name. Note that our file name, in this example, would be ``helloworld.java``.

``helloworld`` contains a main function [or method,s which we'll be using from now onwards] within which a print statement lies.

When we execute the program, we find another file next to our ``.java`` file with ``.class`` extension. Here lies the ``helloworld`` class; you may see that the code is the same in both of them.

#### Print statement

The print statement contains the parameter [anything that goes in the round brackets] 'Hello world!' and returns it as output when we print it.

Remember, ``System.out.println()`` is for printing something, then skipping a line after it. Use ``System.out.print()`` to print without newline.

### Accepting input from user

Java uses a tool ``Scanner`` to read input from the system [as in, reading input typed from keyboard and such]. To use it, we've to import it [one of this language's quirks is that we import A LOT].

```java
import java.util.Scanner;

public class testing
{
    public static void main(String[] args)
    {
        Scanner scanner = new Scanner(System.in);
    }
}
```

> We've imported the scanner utility [the scanner tool] into our program. Now we've to actually use it in the program.

We create an object named ``scanner`` of ``Scanner`` class in the main method. Every time we import an utility in Java, we've to create an object for its class [Scanner utility is of Scanner class, etc.].

This object produces values scanned from an input stream [user-input], whose source is from our keyboard [i.e. standard input].

Now let's make some changes to our code...

```java
import java.util.Scanner;

public class testing
{
    public static void main(String[] args)
    {
        Scanner scanner = new Scanner(System.in);
        System.out.println("Enter a number: ");
        int num = scanner.nextInt();
        System.out.println("Your number is: " + num);
    }
}
```

> We ask the user for input. Then, we create an object [basically a variable here] of type Integer and assign the scanner to it. After that, we print out our message and concatenate [join] our objects to it.

``scanner.nextInt()`` is the longer version of ``Integer.valueOf(scanner.nextLine())``. The scanner produces a String value, which we don't need here. Instead, we convert the input from scanner into integer either directly [nextInt()] or indirectly [Integer.valueOf(scanner.nextLine())].

- However, if you need String input, just assign ``scanner.nextLine()`` to the String object.

## References

> <https://java-programming.mooc.fi/>
