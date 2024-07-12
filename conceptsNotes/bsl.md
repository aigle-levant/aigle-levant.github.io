# Beginner Student Language

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


## Exercises

### Exercise 1

Pythagorean theorem : ``(sqrt (+ (sqr a) (sqr b)))``

```bsl
(sqrt (+ (sqr a) (sqr b)))
```
