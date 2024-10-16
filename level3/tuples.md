---
layout: page
title:  "Tuples"
parent: "Level 3 - SQLite and Introduction To Git"
nav_order: 1
---

## Tuples

Tuples are ordered and `immutable` form of data in Python. Specifically, they are a collection of objects seperated by commas and are very similar to `lists` in terms of indexing. Tuples can store objects of multiple types and the content inside can be accessed via its `index`. Where lists and tuples differ is that once declared, a tuple cannot be modified in any way, a concept known as `immutability`


```python
mytuple = (1, 2, 3, 4, 5)
print(f"First element: {mytuple[0]}")
print(f"Last element: {mytuple[-1]}, {mytuple[len(mytuple) -1]}")
```

These are operations that would cause an ERROR when working with tuples since tuples are IMMUTABLE and as such cannot be modified.

```python
# ERROR
mytuple[1] = 'five'
del mytuple[1]
```

### Traversing Tuples

Since tuples work with indices, same as lists, they can be traversed the same way as lists.

Using a while loop with indices

``` python
i = 0
while i < len(mytuple):
    print(mytuple[i])
    i+= 1
```

Or using a Python for loop

```python
for i in mytuple:
    print(i)
```

### Tuples Use Cases
While `immutability` might seem like a crutch for tuples, it is actually a great feature that helps ensure data `integrity`. As such, tuples are great for dealing with data that SHOULD NOT be changed in cases such as
*  Representing fixed-length records (for database entry)
*  Storing immutable data points
*  Storing collections of immutable global variables
*  Returning multiple variables from a function


Tuples are commonly used when returning multiple variables from a function to ensure that the data being returned is not accidentally changed or modified. A returned tuple from a function can also be `destructured` into its individual elements

```python
import math

def square_info(side):
    area = side ** 2
    perimeter = side * 4
    diagonal = side * math.sqrt(2)
    
    return (area, perimeter, diagonal)

area, perimeter, diagonal = square_info(5)
print(f"Area : {area}, Perimeter: {perimeter}, Diagonal: {diagonal}")
```

Output
```
Area : 25, Perimeter: 20, Diagonal: 7.0710678118654755
```

Tuples are also commonly used in built-in python functions such as `enumerate` and `zip`

```python
fruits = ('apple', 'banana', 'cherry', 'dates')
for index, fruit in enumerate(fruits):
    print(f"Fruit #{index} : {fruit}")
```

```Output
Fruit #0 : apple
Fruit #1 : banana
Fruit #2 : cherry
Fruit #3 : dates
```

```python
points = [(1,2), (3,4), (5,6), (7,8)]
x,y = zip(*points)
print(x)
print(y)
```

Output
```
(1, 3, 5, 7)
(2, 4, 6, 8)
```

### Helpful Tuple Methods

| Method/Operation    | Description                                                       | Example                      | Output               |
| ------------------- | ----------------------------------------------------------------- | ---------------------------- | -------------------- |
| `len()`             | Returns the number of items in the tuple                          | `len((1, 2, 3))`             | `3`                  |
| `count()`           | Returns the number of times a specified value occurs in a tuple   | `(1, 2, 2, 3).count(2)`      | `2`                  |
| `index()`           | Searches the tuple for a specified value and returns the position | `('a', 'b', 'c').index('b')` | `1`                  |
| `+` (concatenation) | Combines two or more tuples                                       | `(1, 2) + (3, 4)`            | `(1, 2, 3, 4)`       |
| `*` (repetition)    | Creates a new tuple by repeating the original tuple               | `(1, 2) * 3`                 | `(1, 2, 1, 2, 1, 2)` |
| Slicing             | Extracts a portion of the tuple                                   | `(1, 2, 3, 4)[1:3]`          | `(2, 3)`             |
| `in` operator       | Checks if an item exists in the tuple                             | `3 in (1, 2, 3)`             | `True`               |
| `max()`             | Returns the item with the highest value in the tuple              | `max((1, 5, 3))`             | `5`                  |
| `min()`             | Returns the item with the lowest value in the tuple               | `min((1, 5, 3))`             | `1`                  |
| `sum()`             | Calculates the sum of all items in the tuple (numeric items only) | `sum((1, 2, 3))`             | `6`                  |
| `sorted()`          | Returns a new sorted list from the elements in the tuple          | `sorted((3, 1, 2))`          | `[1, 2, 3]`          |

### Helpful References
1. [Python Tuple Documentation](https://docs.python.org/3/tutorial/datastructures.html#tuples-and-sequences)
2. [Geeks For Geeks Tuples](https://www.geeksforgeeks.org/tuples-in-python/)
3. [Real Python Tuple Guide](https://realpython.com/python-tuple/)