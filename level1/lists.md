---
layout: page
title:  "Lists"
parent: "Level 1 - Introduction To Python and Data Analytics"
nav_order: 8
---

## Introduction

Lists are one of the most versatile data types available in Python. They allow you to store multiple items in a single variable and can contain elements of different data types. Lists are based off of `arrays` which are defined as a data structure consisting of a collection of elements (values or variables), each identified by at least one array index or key. While Python does not have built in support for arrays, the data science `modules` we will use later on in this course will utilize them

### Index
Lists are accessed through `index` values - these correspond to each indivual `element` or item in the list. The index values start at `0` and go upto the list's `length - 1`.

```python
fruits = ["apple", "banana", "cherry"]

print(fruits[0])  # Output: apple
print(fruits[2])  # Output: cherry
```

Lists are also `mutable`, meaning that they can be modified. We can change an individual element in the list using its index

```python
fruits[1] = "blueberry"
print(fruits)  # Output: ['apple', 'blueberry', 'cherry']
```

Python also has support for `negative indices` which are similar to positive indices but start at the last value with an index of `-1`

```python
# Accessing the last item
print(fruits[-1])  # Output: cherry
print(fruits[-2])  # Output: banana

```
### Lists vs Arrays
* Lists can store multiple data types while arrays are designed to store only elements of the same data type
* Lists can be resized automatically as more elements are added while arrays have a set size
* Arrays are more memory efficient and provide faster accessing and computation

### List Methods

| Method      | Description                                                               | Example                                         |
| ----------- | ------------------------------------------------------------------------- | ----------------------------------------------- |
| `append()`  | Adds an element to the end of the list                                    | `fruits.append("date")`                         |
| `extend()`  | Extends the list by appending elements from an iterable                   | `fruits.extend(["elderberry", "fig", "grape"])` |
| `insert()`  | Inserts an element at a specified position                                | `fruits.insert(1, "banana")`                    |
| `remove()`  | Removes the first occurrence of a specified element                       | `fruits.remove("banana")`                       |
| `pop()`     | Removes and returns the element at the specified position                 | `last_fruit = fruits.pop()`                     |
| `clear()`   | Removes all elements from the list                                        | `fruits.clear()`                                |
| `index()`   | Returns the index of the first occurrence of a specified element          | `index = fruits.index("cherry")`                |
| `count()`   | Returns the number of occurrences of a specified element                  | `count = fruits.count("apple")`                 |
| `sort()`    | Sorts the elements of the list in ascending order (or using a custom key) | `fruits.sort()`                                 |
| `reverse()` | Reverses the order of the list                                            | `fruits.reverse()`                              |
| `copy()`    | Returns a shallow copy of the list                                        | `fruits_copy = fruits.copy()`                   |

### List Traversal

`Traversal` is going through each of the items in a list or collection and is typically done using a loop

Traversing a list with a `for` loop can be done using the `in` keyword
```python
nums = [1.1, 2.2, 3.3]

for i in nums:
    print(i)
```

Traversing a list with a `while` loop can be done using the index value of each element and a loop counter

```python
list1 = [True, False, True, 999]
i = 0

while i < len(list1):
    print(list1[i])
    i += 1
```

### Matrices
Lists can contain other lists inside of them through `nesting`. These are commonly called `matrices`.

```python
matrix1 = [
    [1, 2, 3],
    [4, 5, 6],
    [7, 8, 9]
]

maxtrix2 = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]
```

Both of these matrices are the same but it is sometimes helpful to represent a `nested list` in a 2d format so that it is easier to visualize

Accessing elements in 2d lists will also require 2 indices: one to access the outer list, and one to access the element inside. It is helpful to think of these accessors similar to `rows` and `columns` of a matrix

```python
row = 1
col = 2
print(matrix[row][col])  # Output: 6

row = 0
col = 1
print(matrix[row][col])  # Output: 2
```
Remember, there is no limit to the amount of nesting that a list can have and large forms of data in python can have many levels of nested lists. Thus, 2d, 3d, 4d... matrices are possible in Python

```python
3d_matrix = [
    [
        [1,   2,  3],
        [4,   5,  6]
    ],
    [
        [7,   8,  9],
        [10, 11, 12]
    ],
    [
        [13, 14, 15],
        [16, 17, 18]
    ]
]
```
* Note the spaces and indentation is just for visual effect, it is not necessary to make a matrix

### Matrix Traversal

In order to through a matrix you will need to have a loop for each layer, or level of nesting that the matrix has. For a 2d matrix, this will require 2 loops: one to traverse the rows and one to traverse the columns

```python
for row in matrix:
    for element in row:
        print(element, end=" ")
    print()
```

### Helpful References
* [Geeks For Geeks - Lists](https://www.geeksforgeeks.org/python-lists/)
* [Google Developers - Python Lists](https://developers.google.com/edu/python/lists)