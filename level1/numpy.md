---
layout: page
title:  "Intro To Numpy"
parent: "Level 1 - Introduction To Python and Data Analytics"
nav_order: 9
---

## Introduction

NumPy, is a powerful library for numerical computing in Python. It provides support for large, multi-dimensional arrays and matrices, along with a collection of mathematical functions to operate on these arrays. 

### Why Use Numpy?

Pyhon lists are great - they offer dynamic types, resize automatically, and have helpful methods. However, they are quite slow due to their `heterogeneous` nature. By nature, Python stores data types as `Objects` allowing for attributes and methods for these data types. However, this ends up having slow and memory intensive. Numpy is written in `C`, and deals with data in their `primitive` form, leading to faster computations and less memory usage. It also has support for a greater variety of numeric types than Python does. As such, it a requirement for a lot of leading data analysis and data visualization packages in Python

### Installing & Importing Numpy

To use NumPy, you need to install it first. You can install NumPy using `pip` (Python Package Index)
``` bash
pip install numpy
pip show numpy
```
To use NumPy in your program, you can import it at the top of the program
```python
import numpy
```

You can optionally specify a shorthand name to call your import
```python
import numpy as np
```

### Numpy Arrays

Numpy arrays can be specified with multiple dimensions just like Python lists. When working with Numpy, it is often helpful to view multi dimensional arrays like Matrices. 

```python
import numpy as np

arr_1d = np.array([1, 2, 3, 4, 5])

print("Array:\n", arr_1d)
print("Shape:", arr_1d.shape)
print("Number of dimensions:", arr_1d.ndim)

```
Output
```
Array:
 [1 2 3 4 5]
Shape: (5,)
Number of dimensions: 1
```

```python
arr_2d = np.array([[1, 2, 3], [4, 5, 6], [7, 8, 9]])

print("Array:\n", arr_2d)
print("Shape:", arr_2d.shape)
print("Number of dimensions:", arr_2d.ndim)
```

Output
```
Array:
 [[1 2 3]
 [4 5 6]
 [7 8 9]]
Shape: (3, 3)
Number of dimensions: 2
```
* The number of dimensions of an array can be accessed using the `ndim` attribute
* The shape of an array can be accessed using the `shape` attribute
* The type of an array can be accessed using the `dtype` attribute

### Slicing and accessing elements

Slicing and accessing elements in numpy is similar to that of Python. Elements of higher dimensional arrays can also be accessed easily through specifying indices as a list

```python
arr1 = np.array([9,8,7,6,5,4])
#slicing
print(arr1[0:2])
print(arr1[0:-1]) # start - end
```
```python
a = np.array([[1, 2, 3, 4], [5, 6, 7, 8], [9, 10, 11, 12]]
print(a[1, 3]) # Output: 8
```

### Array Operations and Functions

```python
# Element-wise operations
arr = np.array([1, 2, 3, 4, 5])
print("Array:", arr)
print("Array * 2:", arr * 2)
print("Array + 3:", arr + 3)
```
Output
```
Array: [1 2 3 4 5]
Array * 2: [ 2  4  6  8 10]
Array + 3: [4 5 6 7 8]
```

| Function         | Description                                                    | Example Code                                        |
| ---------------- | -------------------------------------------------------------- | --------------------------------------------------- |
| `np.array`       | Creates a NumPy array from a list                              | `arr = np.array([1, 2, 3, 4, 5])`                   |
| `np.zeros`       | Creates an array filled with zeros                             | `zeros_array = np.zeros((2, 3))`                    |
| `np.ones`        | Creates an array filled with ones                              | `ones_array = np.ones((2, 3))`                      |
| `np.arange`      | Creates an array with a range of values                        | `range_array = np.arange(0, 10, 2)`                 |
| `np.linspace`    | Creates an array with evenly spaced values                     | `linspace_array = np.linspace(0, 1, 5)`             |
| `np.reshape`     | Reshapes an array without changing its data                    | `reshaped_array = arr.reshape((1, 5))`              |
| `np.concatenate` | Joins two or more arrays along an existing axis                | `concatenated_array = np.concatenate((arr1, arr2))` |
| `np.sum`         | Computes the sum of array elements                             | `sum_array = np.sum(arr)`                           |
| `np.mean`        | Computes the mean of array elements                            | `mean_array = np.mean(arr)`                         |
| `np.median`      | Computes the median of array elements                          | `median_array = np.median(arr)`                     |
| `np.std`         | Computes the standard deviation of array elements              | `std_array = np.std(arr)`                           |
| `np.dot`         | Computes the dot product of two arrays                         | `dot_product = np.dot(arr1, arr2)`                  |
| `np.transpose`   | Transposes the dimensions of an array                          | `transposed_array = np.transpose(arr_2d)`           |
| `np.where`       | Returns elements chosen from `x` or `y` depending on condition | `selected_elements = np.where(arr > 3, arr, -1)`    |
| `np.unique`      | Finds the unique elements of an array                          | `unique_elements = np.unique(arr)`                  |
| `np.sort`        | Sorts the elements of an array                                 | `sorted_array = np.sort(arr)`                       |

### Np.Where
The `np.where` functions allows you to select elements from an array based on a condition and also optionally replace elements that do not meet the condition. It could also be used to select certain indices of the array

```python
arr = np.array([1, 2, 3, 4, 5, 6, 7])
print("Original Array:", arr)

condition = (arr > 3) & (arr < 6)
print("Condition:", condition)

indices = np.where(condition)
print("Indices of selected elements:", indices)
```
Output: 
```
Original Array: [1 2 3 4 5 6 7]
Condition: [False False False  True  True  False False]
Indices of selected elements: (array([3, 4]),)
```
* `&` represents bitwise and
* `|` represents bitwise or

### Reshaping Arrays

The `np.reshape` function is used to give a new shape to an array. The new shape must be compatible with the original shape, and the total number of elements must remain the same.

```python
arr = np.array([1, 2, 3, 4, 5, 6])
print("Original Array:", arr)

# Reshaping to 2x3
reshaped_array = arr.reshape((2, 3))
print("Reshaped Array (2x3):\n", reshaped_array)

# Reshaping to 3x2
reshaped_array = arr.reshape((3, 2))
print("Reshaped Array (3x2):\n", reshaped_array)
```
Output
```
Original Array: [1 2 3 4 5 6]
Reshaped Array (2x3):
 [[1 2 3]
  [4 5 6]]
Reshaped Array (3x2):
 [[1 2]
  [3 4]
  [5 6]]
```

### Helpful References
* **[NumPy Official Documentation](https://numpy.org/doc/stable/user/absolute_beginners.html)**
* [W3 Schools Numpy Introduction](https://www.w3schools.com/python/numpy/numpy_intro.asp)