---
layout: page
title:  "Variables And Data Types"
parent: "Level 1 - Introduction To Python and Data Analytics"
nav_order: 6
---

## Introduction

Loops are a fundamental concept in programming that allow you to execute a block of code repeatedly. Python provides two primary types of loops: the `while` loop and the `for` loop.

## The `while` Loop

The `while` loop in Python continues to execute a block of code as long as a specified condition is `True`.

```python
while (boolean expression):
    # Code to execute repeatedly
```

```python
count = 0
while count < 5:
    print("Count is:", count)
```

Output

```
5
5
5 ...
```

This results in an `infinte loop` since the condition has no way of becoming false. `count` will always be `< 5` since it does not change at any point in throughout the loop.

An `infinte loop` could also be written as:

```python
while True:
    # infintely repeating code  block
```

#### Loop counter

```python
count = 0
while count < 3:
    print("Count is:", count)
    count += 1 #increment
```

Output

```
0
1
2
```

Now that counter has been `incremented`, it causes the condition to become `False` once `count >= 3` causing the loop to stop

Loops can also be `decremented` by using the `-=` operator and it is also traditional to use the variable `i` for a counter

```python
i = 10
while i > 0:
    print(i)
    i -= 1  # decrement
```

Loop counter can also be changed by various forms of `conditions` and other `assignment operators`. Try to see how many times this loop would run and what its output would be!

```python
i = 2
while i < 100:
    if i % 10 == 0:
        print("horray!")
    else:
        print(i)
    i *= 3
```

* Note that the `%` (modulo) operator calcualtes the `reminder` of a division operation.



## Lists

`Lists` are `sequences` which are used to stored multiple values. They can also be definied with a combination of multiple different `data types`

```python
list1 = [1, 2, 3, 4, 5] #list of integers
list2 = ["hello", "hi", "how", "are", "you"] #list of strings
list3 = [1, 2.4, False, "x"] #list with mixed data types

```

Lists are very important to store multiple values in a single variable and will be discussed in greater detail in the upcoming lessons

## The `for` Loop

The `for` loop is fundamentally different in python compared to other programming languages and this course will cover it more in detail in an upcoming lesson. For the purpose of this lesson, we will use a `for` loop to iterate through a `sequence`

```python
fruits = ["apple", "banana", "cherry"]
for fruit in fruits:
    print(fruit)
```

Output:

```
apple
banana
cherry
```

### Range Function

To use the `for` loop in order to count to a certain value you need to use the `range()` function. The `range()` function generates a `sequence` of `numbers` upto, but not including a certain value. The `range` function starts off at `0` as is tradition with most programming languages

```python
for i in range(5):
    print(i)
```

Output:

```
0
1
2
3
4
```

In order to specify other ranges of values to print, you can pass in a second value to the `range()` function to specify the value where it starts at (**inclusive**) and stops at (**not inclusive**)

```python
for i in range(1, 10):
    print(i)
```

Output:
```
1
2
3
...
9
```

You can also pass in an additional `step` value which changes the `increment` or `decrement` of the range function. Try to see what this code does by running it on your IDEs!

```python
for i in range(100, 10, -2):
    print(i)
```

## Helpful References
* [Python While Loops](https://www.geeksforgeeks.org/python-while-loop/)
* [Python For Loops](https://www.geeksforgeeks.org/python-for-loops/)
* [Python range() Function](https://cs.stanford.edu/people/nick/py/python-range.html)