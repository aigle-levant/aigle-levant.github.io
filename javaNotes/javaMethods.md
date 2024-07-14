---
layout: default
title: java-introduction
date: 2024-07-07
status: finished
tags: java, programming-languages, functions
---

## Java - Methods

> Never keep any statement **after** the return statement as it will be unreachable. A program considers any program [with a return value] as terminated when it reaches the return statement.

### Objects as method parameters

We can use an object as a parameter in our class program. It helps us to use it to make decisions and changes [like we do in the below program to determine if the person can buy the coffee or not].

Remember, a key part of encapsulation is using private instance variables. We can access them via methods in their class.

```java
public class coffee
{
private String brand;
 private int price;
 private int budget;

 public coffee(String brand, int price, int budget)
 {
  this.brand = brand;
  this.price = price;
  this.budget = budget;
 }

 public int getBudget()
 {
  return this.budget;
 }
 public boolean canBuyCoffee(coffee order)
 {
  if (order.getBudget()<this.price)
  {
   return false;
  }
  return true;
 }
}
```

### Object as object variable

Objects can refer other objects. We have 2 classes - one for our coffee and other for our customer details. We decide to combine both of them for convenience.

``coffee`` object contains 2 references - one to its class, the other to the ``customerDetails`` object.

```java
customerDetails order = new customerDetails("Mary Jane", "221 Baker Street, London", 07878397442);
coffee javaOrder = new coffee("Java", 35, order);
```

### Object of same type as method parameter

> A method may return a value in more than one place. This means we don't need to use only one return statement while writing a method!

If we want to do operations with 2 objects [such as comparison, etc.], we use a method in one of the object's class.

```java
customerDetails order = new customerDetails("Mary Jane", "221 Baker Street, London", 07878397442, "Java");
coffee javaOrder = new coffee("Java", 35, order);

if (order.getBrand().equals(javaOrder.getBrand()))
{
 System.out.println(javaOrder);
}
else
{
 System.out.println("Invalid");
}
```

### Method overloading

We can create multiple version of a given method and fulfil the principle of inheritance. Note that the parameters must be different from the original method.

- It's useful if we want alternate version of our method to work with user-input.

Also in the original method, we can call our over-loader method ``raisePrice`` and pass arguments for ``inflationAmount`` [in other words, we use the child method in the parameter-less parent method].

```java
public void raisePrice()
{
 this.price ++;
 //or
 this.raisePrice(1);
}
public void raisePrice(int inflationAmount)
{
 this.price += inflationAmount;
}
```

When we call this method in our main function, we can either choose to pass something as an argument, or just leave it as it is [letting its value be 1].

```java
//program written before
raisePrice(); //pass argument 1 to method
raisePrice(25); //pass argument 25 to method
```
