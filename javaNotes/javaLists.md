---
layout: default
title: java-lists
date: 2024-06-28
status: finished
tags: java, programming-languages, lists
---

## Java - ArrayList

**Lists** in Java can be created using the utility ``ArrayList``. To use it in our program, we import it and then create an object of its class. 

While creating the ``ArrayList`` object, we specify the type of elements we'd store in it along with its name.

```java
import java.util.ArrayList;

public class Test
{
    public static void main(String[] args)
    {
        ArrayList <String> list = new ArrayList<>();
    }
}
```

We can use our ``ArrayList`` object as a parameter like this:

```java
public static void discount(ArrayList <coffee> menu)
{
//statements
}
```

## Operations

We can perform the following operations using our ``ArrayList`` object in Java :

``add(itemName)`` : Adds an items to the list
``remove(index)`` : Removes the item located at index in the list
``remove(dataType.valueOf(itemName))`` : Removes the item from list
``get(index)`` : Returns the item located at index in list
``indexOf(itemName)`` : Returns the index of the first occurrence of item in list
``size()`` : Returns the size of the list
``contains(itemName)`` : Checks if a value exists in a list or not. Returns a Boolean value depending on it.

If we try to retrieve information from a non-existent place, `IndexOutOfBoundsException` error occurs. It often happens when we retrieve beyond the size of a list.

>**Remember :** Index always starts from 0, not 1!

## References

A **reference** is the value of a list variable that points to the location that contains that information.

When a method copies a list for its own usage [we do this by adding it to its parameters], it receives the references from the list's copy, and thus, **reference to the real value of a reference-type variable** as well.

- Using this, the method can modify the value of the original variable [here, its the list].
- The list used as parameter for a method is the same list used in program to call that method.

### Variable types in Java

Variables in Java are divided into 2 categories :

- Value type [primitive] : These hold their actual values
- Reference type : Contain a reference to the location that contains the value[s] relating to that variable

Hence, when we create a list, `ArrayList` assumes that all the variables contained in it are reference types.

### For-each loop

To iterate an ``ArrayList`` object, we could use a [[Java - Loops#For loop|for-loop]]. A flaw with this method is that we'll have to keep track of the list index while iterating [plus un-needed complexity for such a simple action].

```java
//assume we've created an ArrayList object
//of type String named brands
for (int i=0; i<brands.size();i++)
{
    System.out.println(i);
}
```

Or, we could even go for a [[Java - Loops#While loop|while loop]] - an even lengthier option!

```java
//assume we've created an ArrayList object
//of type String named brands
int i = 0;
while (i<brands.size())
{
    String name = brands.get(i);
    System.out.println(name);
    i++;
}
```

Or, we could go for an easier method by using **for-each loop**. It acts like a for-loop where we print each item of a list, except it doesn't require you to use its index.

We mainly use it if we want to display every item in a list.

```java
//assume we've created an ArrayList object
//of type String named brands
for (String i:list)
{
    System.out.println(i);
}
```

## Objects containing lists

Objects can also contain lists in them.

We can have ``ArrayLists`` as our instance variables. In the constructor, we assign new ``ArrayList`` to them [using ``this`` prefix]. Now we can do ``ArrayList`` operations using our instance variables.

```java
public class coffee
{
	private ArrayList<String> brands;
	private ArrayList<Integer> prices;
	
	public coffee()
	{
		this.brands = new ArrayList<>();
		this.prices = new ArrayList<>();
	}

	public void addCoffee(String brandName, int priceTag)
	{
		if (!(this.brands.contains(brandName)))
		{
			this.brands.add(brandName);
			this.prices.add(priceTag);
		}
	}
	public void removeCoffee(String brandName)
	{
		this.prices.remove(brandName);
	}
	public void removeCoffee(int index)
	{
		this.prices.remove(index);
	}
	public void printMenu()
	{
		System.out.println("Coffee | Price");
		for (int i=0; i<brands.size();i++)
		{
			System.out.println(brands.get(i) + " | " + prices.get(i));
		}
	}
}
```

>If you want to remove an element from list as you return it, try this : ``return listName.remove(i)``

### Objects in an instance variable list

If a list is an object's instance variable, it can also contain objects as long as the type of objects in the list are specified when we define the list.

In our class ``coffee``, we create an ``ArrayList`` object of type ``customer``. We can use it in our methods as we please.

```java
public class coffee
{
	private String brand;
	private double price;
	private ArrayList <customer> order;

	public coffee(String brand, double price)
	{
		this.brand = brand;
		this.price = price;
		this.order = new ArrayList<>();
	}
	public boolean canPurchase(customer order)
	{
		if (order.getBudget()<this.price)
		{
			return false;
		}
		return true;
	}
}
```

#### Printing an object from a list

```java
//coffee class
public String toString()
{
	String str = "";
	for (coffee i: order)
	{
		str = str + i.getBrand() + '\n';
	}
	return "Coffee: " + this.brand + '\n' + "Price: " + this.price + '\n' + str
}
```

#### Clearing an object's list

```java
//coffee class
public void clearOrder()
{
	this.order.clear();
}
```

#### Sum from objects of a list

This returns -1 if the list is empty.

```java
public double sumOfOrders()
{
	if (order.isEmpty())
	{
		return -1;
	}
	int sum = 0;
	for (coffee i: order)
	{
		sum += i.getPrice();
	}
	return sum;
}
```

#### Retrieving specific object from list

```java
//coffee class
public coffee getLocation()
{
	if (this.order.isEmpty())
	{
		return null;
	}
	coffee obj = this.order.get(1);
	for (coffee i:this.order)
	{
		if (!(obj.isEmpty()))
		{
			obj = i;
		}
	}
	return obj;
}
```
