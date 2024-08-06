---
layout: page
title:  "Functions"
parent: "Level 1 - Introduction To Python and Data Analytics"
nav_order: 7
---

## Functions

Functional programming is a programming paradigm that involves breaking down a problem into simple, modular pieces in order to solve it. It is a programming `paradigm` (or model) that treats a computational problem as the evaluation of mathematical functions that take inputs, produce outputs, and **ideally** don't change state

The benefits of functional programming are as follows: 

1. **Modularity**: Functions allow us to break down complex problems into simpler pieces.
2. **Reusability**: Functions can be reused in different parts of a program, reducing code duplication.
3. **Testability**: Functions are easier to test because they are independent units of code.
4. **Predictability**: Pure functions (functions without side effects) are predictable and easier to understand.


### Functions Without Arguments

Lets define a simple function using the `def` keyword in python. The function is not executed unless it is `called`, then the code block of the function is executed every time it is called

Syntax:

```python
def [function_name](param1, param2, ...):
    #code block
    return value
```

```python
def say_hello():
    print("Hello")

say_hello()
say_hello()
```

Output:

```
Hello
Hello
```

### Functions With Arguments

Functions can have different behavior based on the `arguments` or `parameters` that are provided. A `pure` function will return the same result if the same `arguements` are passed and does not depend on any `state`. Passing arguments to functions allow them to reuse their computation logic towards new inputs.

```python
def greet(name):
    print(f"Hello {name}")

greet("Tom")
greet("Rahul")
```

Output:
```
Tom
Rahul
```

Multiple parameters can be passed in seperated by comma. When a function is `called`, the arguments given correspond to each of the parameters in the order they were provided

```python
def greet(first_name, last_name):
    print(f"Hello {first_name} {last_name}")

greet("John", "Doe")
first_name = "Tom"
last_name = "Hanks"
greet(last_name, first_name)
```

Output:
```
Hello John Doe
Hello Hanks Tom
```

Note that the variables `first_name` and `last_name` outside of the function do not correspond to the variables inside the function. Also note that the name of the paramaters passed does not matter, it is the **`order`** that matters

Functions that do not return anything are called `void` functions

### Function With Return

A function can return a value using the `return` statement. This allows the function to send data back to `main` (or wherever it was called) so that the data can be used for additonal computation or logic.

```python
def add(a, b):
    return a + b

result = add(3, 4)
print(result)  # Output: 7
```

A function can also return multiple values in the form of a `tuple` (which will be discussed later in the course). To access these return values, you assign them to multiple variables seperated by comma

```python
def arithmetic_operations(a, b):
    return a + b, a - b, a * b, a / b

addition, difference, product, quotient = arithmetic_operations(8, 4)
print(addition, difference, product, quotient)  # Output: 12 4 32 2.0
```

### Python Type Hinting
Functions can return multiple types of data in python, and function arguments are also `dynamic` (meaning that they are not of a specific type). This is great for reusing functions across multiple types of data but can lead to unforseen bugs

```python
def add_values(a,b):
    return a + b
print(add_values(1,2)) #integer type
print(add_values(1.2,2.4)) #float type
print(add_values("hello","there")) #string type
```

In this example, function add_value can be used with many different types of data use to the `dynamic` nature of Python. This is great when we want `add_value` to work with multiple different types of data without modifying the code logic

```python
def large_num(num1, num2):
    if num1 >= num2:
        return num1
    else:
        return num2
print(large_num(1,4)) #Output: 4
print(large_num(False, True)) #CRASH!!
```

In this example, however, the data passed into the function has unexpected behavior due to the `large_num` function not being able to handle data types such as `boolean`. This is a problem when you are trying to use functions and are not entirely sure what data type the function arguements can handle and are unsure of what type of data is `returned`

To assist with this, Python 3.10 introduct **Type Hints** which are a way to get `intellisense` and infer function argument and return types

```python
def large_num(num1: int | float, num2: int | float) -> int | float:
    if num1 >= num2:
        return num1
    else:
        return num2
print(large_num(1,4)) #Output: 4
print(large_num(False, True)) #CRASH!!
```

This still causes a crash when `large_num` is called with improper arguments as Python does not enforce `type checking` (more updates are being added to Python to improve this feature). However, it is a good tool to have to help programmers understand the intended behavior of a function

### Helpful References
* [Python Official Documentation on Functions](https://docs.python.org/3/tutorial/controlflow.html#defining-functions)
* [PEP 484 - Type Hints](https://peps.python.org/pep-0484/)
* [W3Schools - Python Functions](https://www.w3schools.com/python/python_functions.asp)