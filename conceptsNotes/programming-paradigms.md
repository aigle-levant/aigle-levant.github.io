---
layout : default
---

## Programming paradigms

A **programming paradigm** [paradigm - standard; perspective] is a way [usually high-level] in which a program / programming language can be organised. In short, they're a set of ideals and guidelines.

Each paradigm has structures, features, opinions, etc. on how a certain problem should be solved.

Some programming paradigms are :

- Imperative programming
- Procedural programming
- Functional programming
- Declarative programming
- Object-oriented programming

### Imperative programming

It is a paradigm where we give detailed instructions to the computer to execute in a particular order.

- **Imperative** - absolutely necessary


> If we want to bake a cake, we HAVE to follow the steps in order, else we'll end up with a glob-like mess!

### Procedural programming

It is derived from imperative programming. Here, we ease the mental workload of the user by dividing the program into a couple of functions.

This promotes modularity and keeps the code organised.

> If we're building a calculator program, it is wise to turn most of our program into functions so that we can modify stuff in them.

### Functional programming

It is the third paradigm. Here, we notice elements of bourgeoise in functions as they're treated as first-class citizens.

- This means that they can be assigned to variables, passed as arguments, return from functions.
- It requires majority of the program written in functions [just like its predecessor].

```none
def function3(param):
return function2() #possible
a = function() #possible

function2(function()) #again, possible
```

#### Pure functions

Functions that depend only on its own input to generate its result [this one is an example of a self-sufficient pers...ahem, function].

- Given the same input, it'll always generate the same output. No side-effects included.

### Declarative programming

It is the paradigm where we abstract our complexities away. Here, the instructions are focused on the result rather than how the computer should do the task [unconventional methods are welcome].

> React is a good example of this; it combines JS and HTML.

### Object-oriented programming

Perhaps the most important programming paradigm out of them all, OOP is used to design a program using classes and objects.

#### Objects

**Objects** are entity whose state and behaviour are known. They can be tangible [like the laptop you're typing on] or intangible [like IDLE where you program].

>You have a mechanical pencil. Brustro and 0.5 are written against the metal casing. When you open it, a eraser fit and a lead comes out of it. You click the cap and the lead comes out. You can write and draw with it.
>
>State - Its brand, lead size, contents, type of material
>
>Behaviour - Writing and drawing, clicking the cap

#### Class

A **class** defines the **attributes** of **objects** and their **commands**. It acts as a blueprint for any object that is instantiated from it.

>Houses are the instances [or objects, since they're the same thing] of the class house with attributes such as wall-colour, roof, building materials, BHK, etc.
