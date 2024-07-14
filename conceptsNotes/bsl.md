
# Beginner Student Language

> Last updated : 2024-07-14

## Expressions

Every **expression** in BSL starts with the operators at first with operands following up. This can expressed by the formula : ``(<operator> <operands>)``

```bsl
(+ 3 4)
//7
(- 25 2)
//23
```

For even more complex expressions, we use more round brackets.

```bsl
(+ 3 (* 2 3))
//9
(/ 12 (* 2 3))
//2
```

> In BSL, we refer operators as **primitives** and operands as **expressions**.

Comments are made in BSL using `;` [which makes it wildly different from any other programming language].

We have functions in BSL.

```bsl
(sqr 3) //9
(sqrt 25) //5
```

> Square roots of 2, 3, etc. give irrational numbers that are represented as ``#i`` then the number.

A **primitive call** is any expression with open parentheses and name of a primitive operator. The nested parentheses are considered as operands as a whole.

Then we look into each operand of a primitive call and find the same pattern and sit up amused at this simplistic pattern.

```bsl
(+ 2 (* 3 4))
```

We follow the following steps to evaluate a primitive call [generally from left to right] :

- All operands are to be reduced to values.
- Apply operator or primitive to values.

## Strings and images

Calls to string and image primitives work similar to calls to number primitives.

```bsl
"hello world!"
```

We can concatenate strings together like this :

```bsl
(string-append "Ada" " " "Lovelace") //"Ada Lovelace
```

We get the length of string like this :

```bsl
(string-length "icon") //4
```

We have substrings [parts of string]. The index starts from 0.

```bsl
(substring "Malibu" 1 3) //"ali"
(substring "Malibu" 0 4) //"Mali"
```

To use images, we use the following command :

```bsl
(require imagePath) //here we use 2htdp/image as path
```

``circle`` primitive is an image primitive which we can create using : ``(circle radius "solid" "colour")``
``rectangle`` primitive is another image primitive which has the format : ``(rectangle l w "state" "colour")``
``text`` primitive produces a image text with the format : ``(text "message" fontSize "colour)``

``above`` primitive lets you stack images [received as arguments] on top of other. ``beside`` primitive lets you stack images next to each other. ``overlay`` primitive lets you stack images on each other.

## Constant definition

Constant definitions make values re-usable by people. They promote **readability** and **changeability**.

```bsl
(define CONST value)
(any expression involving CONST)
```

To evaluate a constant definition, we check the definition and record the value and the name associated with it [that is called a variable]. Constant names have to be unique to a value and can't be repeated.

When the name is encountered anywhere afterwards, the name changes into the value associated with it.

```bsl
(define NUM 10)
(* (* NUM 2) (* NUM 3))
//(* 20 30)
//600
```

Our values can be anything - string, images, numbers, etc. We've to be careful enough not to use them incorrectly.

## Function definitions

**Functions** are mechanisms to write programs that produce different values when they're called. They help to eliminate duplicate code [remember : Don't Repeat Yourself].

They work similar to functions in maths.

```bsl
(define (functName parameter)
//body of the function with parameter
)
(functName arg)
```

The **parameter** is the changing value which the function uses in its body. We pass arguments to the function to replace the parameter with our value in the function.

A language with only functions is cumbersome to program. Hence, we've functions as well as strings, images, numerical values, etc.

## Booleans and if expressions

Boolean holds only 2 values : either ``true`` or ``false``. To get Boolean output, we'd use comparison operators or predicates [<, >, <=, >=, =, etc.]

**Predicates** are primitives that produce a ``true`` or ``false`` value.

```bsl
(define WIDTH 100)
(define HEIGHT 200)
(> WIDTH HEIGHT) //false
(< WIDTH HEIGHT) //true
(string=? "foo" "bar") //false
(< (image-width imageDef) (image-width imageDef2))
```

If expressions consist of a condition followed by a true and false answer. Their condition has to produce a Boolean value [hence it's usually a predicate].

Also, the answer has to evaluate to either true answer or false answer. It throws an error if it's anything else.

```bsl
(if condition
//return if true
//reutrn if false)
```

``and`` operator ensures that both the conditions have to be satisfied and they produce Boolean values. If any one of the conditions produce `false`, the entire expression is `false` [a method called short-circuiting].

```bsl
(if (and (condition) (condition)))
```

## Stepper

Stepper goes through each step of evaluation of expression produced a certain value. It's used to check out why a function isn't producing the value it should, at times.

## Other primitives

There are 2 ways to discover a primitive :

- Make a guess
- Look up and scroll [just look up somewhere - stackOverFlow, Google, documentation, etc.]
