---
layout: base-layout.njk
title: Java - OOP
---

## Classes

In Java, classes are a **public** entity. They are usually declared in a separate file from the main program.

```java
public class coffee
{
    private String name;
    private double price;
}
```

> Every class we create [even the ready-made ones] inherits the class ``Object``. This is why we can pass an instance of a class as a parameter to a method and why ``toString`` and ``equals`` methods exist.

### Constructor

A constructor is automatically created if it's not defined for a class [however, it will be an empty constructor that does nothing].

In Java, the constructor has the **same name as the class**. Its parameters are the **instance variables** we declared before [if we want, we can change the name in the parameters].

- After that, we pass the parameters to our instance variables, which are referred by ``this.var``.

```java
public class coffee
{
    private String name;
    private double price;
 
    public coffee(String name, double price)
    {
        this.name = name;
        this.price = 0;
    }
}
```

We then create objects in our main program using the command `new`. The arguments passed here will be assigned to the instance variables of the objects [thus, defining its state].

```java
public class Main
{
    public static void Main(String[] args)
    {
    coffee espresso = new coffee("espresso", 35);
    }
}
```

#### Constructor overloading

It is the technique of having two or more constructors in the same class. We can use them to create objects with different parameters.

``` java
public class coffee
{
    private String name;
    private double price;

    public coffee(String name)
    {
    this.name = name;
    }
    public coffee(String name, double price)
    {
    this.name = name;
    this.price = 0;
    }
}
```

We cannot have two constructors with the exact same parameters or with same structure
In this case, we can't have 2 constructors with the same String and int parameters, even if they were different variables.

``` java
//assume class coffee is created with instance variables -> name, price, quality
public coffee(String name, int price)
{
    this.name = name;
    this.price = price;
}

//we can't do this
public coffee(String name, int quality)
{
    this.name = name;
    this.quality = quality;
}
```

#### Calling constructors

A constructor can be called from another constructor using ``this`` prefix. We use it to follow the principle of ``Don't Repeat Yourself``.

```java
//assume class coffee is created with instance variables -> name, price, quality
public coffee(String name, int price, int quality)
{
 this.name = name;
 this.price = price;
 this.quality = quality;
}
public coffee(String name, int price)
{
 this(name, price, 0);
}
```

### Public and private entities

A **public entity** is visible to the outside world. We can access and modify it.

Whereas a **private entity** is hidden and forces the users of the class to access it through specified means only. Usually we hide the instance variables of a class.

- This is possible thanks to the concept of encapsulation.

#### Static

**Static** is a modifier that indicates that the method doesn't belong to an object [we don't need an object to access it] and can't be used to access variables that belong to objects.

We use this modifier if the method is receiving the variables as parameters [case in point - main method].

## Strings and objects

We use the method ``toString()`` to return a string representation of our object.

```java
public class coffee
{
 //program
 public String toString()
 {
  //return statement
 }
}
```

This, we can call in our main function by the print statement. When we do so, Java parses the statement as below, thanks to abstraction.

```java
System.out.println(espresso);

//becomes
System.out.println(espresso.toString());
```

### Equality between objects

To check if two objects are equal [i.e. having the same content], we have to create a method that does that - receiving an object as parameter. We check if the variables are the same and in place and if the object is an instance of our class.

Then we convert the passed object into our class and then compare each object variable [belonging to our object] with it.

> This is the order of checking between 2 objects :

> - Addresses
> - Types
> - Value of object variables

Let's say an object variable is a String. We use the String `equals()` method to compare them.

```java
public boolean equals(Object compareOrder)
{
 //variables in same position
 if (this == compareOrder)
 {
  return true;
 }
 //if object type is not same
 if (!(compareOrder instanceof coffee))
 {
  return false;
 }
 //converting object into coffee type
 coffee checkOrderIsCorrect = (coffee) compareOrder;
 //comparing object variables
 if (this.brand.equals(checkOrderIsCorrect.brand)
 && this.price.equals(checkOrderIsCorrect.price))
 {
  return true;
 }
 return false;
}
```

## Storing in a list

We create an ``ArrayList`` object with its type being the class name [since object's type is its class].

```java
ArrayList <coffee> menu = new ArrayList<>();
```

Now we proceed to add objects in 3 ways :

```java
//indirectly
coffee espresso = new coffee("Espresso", 20.00);
menu.add(espresso); //directly

//directly
menu.add(new coffee("Espresso", 20.00));

//user-input [assume scanner is imported]
System.out.println("Coffee name: ");
String name = scanner.nextLine();
System.out.println("Coffee price: ");
double price = scanner.nextDouble();
menu.add(new coffee(name, price));
```

We use a for-each loop to print the list.

```java
for (coffee item:menu)
{
 System.out.println(item);
}
```

### Checking equality in lists with objects

The ``contains`` method uses the ``equals`` method [which we define for objects] for comparison. Let's assume we have an ``equals`` method in our class ``coffee`` that compares order with our menu to see if we got it right.

```java
//assume class coffee and everything else is defined
public boolean equals(Object comparingOrder)
{
 if (this==comparingOrder)
 {
  return true;
 }
 coffee compare = (coffee) comparingOrder
 if (this.brand.equals(compare.brand) &&
 this.price==compare.price &&
 this.customerName.equals(compare.customerName))
 {
  return true;
 }
 return false;
}
```

Now we use it to compare with a list of orders :

```java
ArrayList <coffee> orderList = new ArrayList<>();

```

## Reference variable in OOP

> Refer -> [[Java - Variables#Reference variables|Reference variables]] & [[Java - Methods#Objects|Objects and methods]]

When we call a constructor, we return a reference [info. about the location of object data] to an object.

Consider the following - we have an object ``espresso`` whose ``price`` is set to 25. We create a new object ``java`` and assign the value of ``espresso`` to it [this means its price is also 25!].

We then increase the `price` of ``java`` by 20 [total price is 45]. But when we print ``espresso``, we get the same price as ``java``!

- It is because an object's internal state isn't copied while assigning it as value to a variable.

```java
coffee espresso = new coffee("espresso", 25);
coffee java = espresso;
java.raisePrice(20);
```

### ``null`` value of a reference variable

An object whose reference variable is `null` [or is not referenced by anything] is called a **garbage variable**. It is taken care of by Java's automatic garbage collector.

- If garbage collection didn't happen, these objects would wastefully take up space until end of program execution.

When we print a variable that references to ``null``, it just says ``null`` [nothing more, nothing less]. But if we try to call a method on that variable, Java throws a ``NullPointerException`` error at us [of course, what can you do with a variable that references to *nothing*?].

```java
coffee espresso = new coffee("espresso", 35);
espresso = null;
espresso.raisePrice(); //throws exception
```
