---
layout: post
title: java-introduction
date: 2024-06-14
status: ongoing
---

> Resource used:
>
> <https://java-programming.mooc.fi/>

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

## Java and its quirks

Java is verbose when compared to Python, C, JS, etc.

Compare our previous code with...

```python
print("Hello world!");
```

and

```c
#include <stdio.h>
int main (void)
{
    printf("Hello world!");
}
```

Short and simple do not belong in the books of this language. This makes it a slightly difficult choice for any beginner programmer, but an excellent choice for enterprises [they NEED that verbosity!].

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

> Note that our file name, in this case, would be helloworld.java

When you create a file in Java, its name gets automatically [or manually if you don't use an IDE] assigned as a class name.

Here, ``helloworld`` is the name of a public class in your program. It contains a main function [or method, which we'll be using from now onwards] within which print statement lies.

We shall look deeper into classes and public / private stuff here.
