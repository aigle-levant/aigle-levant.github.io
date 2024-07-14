---
layout: default
title: java-variables
date: 2024-07-10
status: finished
tags: java, programming-languages, datatypes
---

## Java - Variables

**Variables** in Java are classified into primitive and reference variables. Since Java are **statically-typed**, they must be declared [with their type and all] before usage.

### Primitive variables

A **primitive variable** is any variable having a primitive [or pre-defined] data type. It stores as value any information related to it.

```java
int value = 10;
String name = "Michael Jackson";
```

>When we say ``int value = 10``, we mean 'reserve a location in memory called `value` and copy the value `10` to it'.

When we declare a primitive variable, the computer reserves memory to store the value assigned to the variable [the amount of storage required depends on the datatype].

- 2 lockers of size of datatype is reserved in memory for the value and the variable.
- After this, contents of the memory location storing the value are copied into memory location of the variable.
- Also, a variable's value is an address in memory [info. attached to it specifying how much data should be retrieved from its address and all that].

> Primitive variables are **immutable**. This means their internal state can't be changed, unlike reference variables. 

> This is due to their values being stored directly in that variable.

#### Primitive data types

These are the pre-defined data types found in Java.

- `int` : Integer; covers all non-fractional numeric values.
- `float` : Floating point; covers decimal numeric values up to 6 decimal points.
- `double` : Double-precision floating point; covers decimal numeric values up to 15 decimal points.
- `boolean` : Boolean; contains only 2 value - `true` or `false`.
- `char` : Character; covers all single characters in Unicode.
- `byte` : An 8-bit signed `int` that can store values ranging from -128 to 127.
- `short` : A 16-bit signed `int` that can store values ranging from -32768 to 32767.
- `long` : Long integer; covers non-fractional numeric values from -2^63 to 2^63 - 1.

### Reference variables

A **reference variable** points to an object and lets you access its value [i.e. it holds the memory address of that object in order to refer it, like a pointer].

Its value points to a location that contains information relating to the given variable.

```java
coffee java = new coffee("java", 35);
```

> Reference variables are **mutable**. This means their internal state is mutable, thanks to them being a reference to the variable's data.
