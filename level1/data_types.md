---
layout: page
title:  "Variables And Data Types"
parent: "Level 1 - Introduction To Python and Data Analytics"
nav_order: 3
---

## Variables in Python
A variable in Python is a name that refers to a memory location where data is stored. Unlike some other programming languages, Python does not require explicit declaration of variables. A variable is created the moment you first assign a value to it.

### Creating Variables

```python
x = 5
y = "John"
print(x)
print(y)
```

In the example above, `x` is an integer variable, and `y` is a string variable. Python variables do not need to be declared with any particular type and can even change type after they have been set because it is a [dynamically typed language](#dynamically-typed-languages)

This is opposed to a language like Java which only has static types and requries you to define the type of the variable upon initialization

```java
    int x = 9;
    String y = "Hello";
```

#### Multiple Assignments

You can assign multiple variables in a single line:

```python
x, y, z = -9, 22.2, "hello"
print(x)
print(y)
print(z)
```


#### Multiple Assignments

You can assign multiple variables in a single line:

```python
x, y, z = -9, 22.2, "hello"
print(x)
print(y)
print(z)
```

## Data Types

Data types describe the type of value a variable can have and the mathematical, logical, or relational operations that can be performed on it without causing an error. In Python, different data types are used to store and compute different types of data. The `type()` function will print out the type of the variable passed to it

### Basic Data Types

1. **Integers**: Whole numbers, positive or negative
    ```python
    x = 10
    print(type(x))  # Output: <class 'int'>
    ```

2. **Floats**: Numbers with a decimal point (also called a floating point)
    ```python
    y = 10.5
    print(type(y))  # Output: <class 'float'>
    ```

3. **Booleans**: Represents `True` or `False`
    ```python
    b = True
    print(type(b))  # Output: <class 'bool'>
    ```


### Sequence Types

1. **Strings**: A sequence of characters.
    ```python
    s = "Hello, World!"
    print(type(s))  # Output: <class 'str'>
    ```

2. **Lists**: Ordered, mutable collections of items.
    ```python
    lst = [1, 2, 3, "Python"]
    print(type(lst))  # Output: <class 'list'>
    ```
3. **Tuples**: Ordered, immutable collections of items.
    ```python
    tpl = (1, 2, 3, "Python")
    print(type(tpl))  # Output: <class 'tuple'>
    ```

### Mapping Types

1. **Dictionaries**: Unordered collections of key-value pairs.
    ```python
    d = {"name": "John", "age": 30}
    print(type(d))  # Output: <class 'dict'>
    ```

There are many other data types present in Python and its' libraries and they will be covered later on in this course

### Dynamically Typed Languages

Python is a dynamically typed language, which means that the type of a variable is determined at runtime. Genereally, dynamically typed lanauages offer more flexibility but are often error prone due to the types of variables changing. The later versions of Python work to enforce static typing to a certain extent (which will be covered later on in the course)

```python
x = 5
print(type(x))  # Output: <class 'int'>
x = "Hello"
print(type(x))  # Output: <class 'str'>
```

### Helpful Links
- [Python Variables - W3Schools](https://www.w3schools.com/python/python_variables.asp)
- [Python Data Types - GeeksforGeeks](https://www.geeksforgeeks.org/python-data-types/)
- [Python Variables and Data Types - Programiz](https://www.programiz.com/python-programming/variables-datatypes)
