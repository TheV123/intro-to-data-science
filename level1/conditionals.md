---
layout: page
title:  "Conditionals"
parent: "Level 1 - Introduction To Python and Data Analytics"
nav_order: 5
---

## Introduction

Conditional statements in Python allow you to execute certain pieces of code based boolean values (`True` and `False`). These statements are fundamental for controlling the flow of a program and directing the execution of code to blocks where you want to handle certain logic. The primary conditional statements in Python are `if`, `elif`, and `else`.

## The `if` Statement

The `if` statement is used to test a condition. If the condition evaluates to `True`, the block of code inside the `if` statement is executed. If the condition evaluates to `False`, the block of code is skipped.

```python
if (boolean expression):
    #code block
```

```python
number = 10
if number > 0:
    print("The number is positive.")
```

Output

```
The number is positive
```
In this example, the condition `number > 0` evaluates to `True`, so the code block inside the if statement is executed.


## The `else` Statement

The `else` statement is used to execute a block of code if the condition in the `if` statement evaluates to `False`. If the `if` statement evaluates to `True`, the `else` statement is skipped

```python
if (boolean expression):
    #code block
else (boolean expression):
    #code block
```

```python
number = -5
if number > 0:
    print("The number is positive.")
else:
    print("The number is negative.")
```

Output

```
The number is negative
```
In this example, the condition `number > 0` evaluates to `False`, so the code block inside the if statement is skipped and the code block inside the `else` is evaluated


### The `elif` Statement
The `elif` statement (`else if` in most other programming languages) is used to check multiple conditions. If the condition for `if` is `False`, it checks the condition of the next `elif` block and so on. If all the conditions are `False`, the `else` block is executed.

```python
if (boolean expression):
    # code block
elif (booleean expression):
    # code block
...
else:
    # code block
```

```python
number = -1
if number > 0:
    print("The number is positive.")
elif number < 0:
    print("The number is negative.")
else:
    print("The number is zero.")
```

Output
```
The number is negative
```

In this example, the first condition `number > 0` evaluates to `False`, so it checks the next condition `number < 0`, which also evaluates to `True`. Therefore, the code block inside the `elif` statement is executed.