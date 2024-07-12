
# Object-oriented programming

Perhaps the most important programming paradigm out of them all, OOP is used to design a program using classes and objects.

OOP is about isolating concepts into separate entities and building a program from small & distinct objects. Abstraction is a core part of this principle.

## Basic principles of OOP

### Encapsulation

It is a principle where we hide how objects are implemented from the outside world. Only select information is available publicly while the rest are private.

- Provides security and control over state changes.
- Reduces error caused by unwanted changes.
- Through this, objects hide their internal operations. To access their functionality, we use its methods.

### Inheritance

It is a principle that enables developers to create new classes based on existing classes.

- The existing class is referred to as the parent.
- Reduces workload needed; we can make changes here and there instead of starting from scratch.

### Polymorphism

It is a principle that allows objects of different classes to perform actions [with the same name] using different code.

- Promotes usage of common methods.
- Works hand-in-hand with [inheritance](#inheritance) [we can use the parent class as a template for other classes and have a common method to do a common action].

> **Poly**: Many;
> **Morph**: Changing the state of something

### Abstraction

It is a key concept of programming where we ignore the less important details of our code [which doesn't really affect the key feature of our program]. It is an expansion of [encapsulation](#encapsulation).

## Classes

A **class** defines the **attributes** of **objects** and their **commands**. It acts as a blueprint for any object that is instantiated from it.

It defines the what type of object can be created from it as well as its state and actions.

- **Attributes** are the information related to objects. They're also called **instance variables**. They specify the **internal state of the object**.
- **Commands [or methods]** are pieces of source code written inside a class that has been named and can be called. They're used to modify the internal state of an object instantiated from a class. They specify **what an object does**.

> ``Mansion, apartment, bungalow, etc.`` are the instances [or objects, since they're the same thing] of the class ``House`` with attributes such as wall-colour, roof, building materials, BHK, etc.

### Object

An **object** is an instance of a class [or rather, a way to introduce the class to our program]. Its state and actions performed are defined by its attributes and methods.

They can be tangible [like the laptop you're typing on] or intangible [like IDLE where you program].

- **State** refers to the data value of an object. This is maintained in one or more variables.
- **Behaviour** is the functionality of an object. This is implemented using methods.
- **Entity** is an object that is both unique and can be identified. This contains information.

Objects are **mutable**; their state can be changed by making an assignment to one of their instance variables.

> You have a mechanical pencil. Brustro and 0.5 are written against the metal casing. When you open it, a eraser fit and a lead comes out of it. You click the cap and the lead comes out. You can write and draw with it.
>
>State - Its brand, lead size, contents, type of material
>
>Behaviour - Writing and drawing, clicking the cap

#### Attributes

**Attributes** are information related to the object. Since their values can change and they affect an instance [object and instance are the same thing; colour me confused], we call these **instance variables**.

- The **state of an object** is the value of its instance [or internal] variables at any given point of time.

>Imagine we have a class ``Car`` with the object ``Ferrari``. The instance [or internal] variables such as fuel, mileage, condition, etc. reflect the state of the object at a particular time.

#### Methods

**Methods** are code written inside a class that are given a name and can be called using the object [after instantiation].

- They modify the internal state of an object after instantiation.
- They specify **what an object does**.

Objects interact with each other through method calls - these request information from objects and give them instructions to perform an action.

### Constructor

It is a method that creates an object from its instance variables.
