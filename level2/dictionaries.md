---
layout: page
title:  "Dictionaries"
parent: "Level 2 - Data Visualization Techniques"
nav_order: 1
---

## Dictionaries

Dictonaries, also called `objects` (Javascript) and `Hashsets` (Java) are data structures capable of storing data with complex relationships. It is the backbone of most complex data operations and can be used in conjunction with `dataframes` and `JSON` data. Dictionaries operate using a key value pair, where the key is used to access the value.

Dictonary keys are used to access the values of the dictionary. They must be immutable and unique. Typically, dictionary keys are strings or `uuids` (universal unique identifiers)

Dictionary values can be anything, including other dictionaries, arrays, or even complex objects.

```python
alice = {"name": "Alice", "age": 17, "grade": 11}

bob = dict(name="Bob", age=16, grade=10)
```

```python
players = {
    "joe": {"first_name": "joe", "last_name": "burrow"},
    "tom": {"first_name": "tom", "last_name": "brady"},   
}
```

### Accessing And Modifying Dictionaries

Dictionary values can be accessed using their keys, similar to accessing indices in an array. Accessing a value in a dictionary is a `constant time operation`, meaning that Python is able to access the reference of the value without having to search the dictionary for the value. This makes accessing and modifying keys and values of a dictionary very fast, making them a preffered data structure for algorithmns classes in college and solving coding questions.

``` python
#getting a value using a key
print(alice["name"])  # Output: Alice
print(alice.get("name"))  # Output: Alice

# Modifying a value
bob["age"] = 18
bob["grade"] += 1

# Adding a new key-value pair
bob["favoruite_subject"] = "Math"

#deleting a key-value pair
del bob["favoruite_subject"]
```

### Iterating Through Dictionary Keys and Values
Dictionaries can be iterated through easily by treating their keys and values as `sets` (which are simply lists with unique elements).

```python
mountains = {
        1 : "Mount Everest",
        2 : "K2",
        ...
}

#iterating through keys of the dictionary
for key in mountains:
    print(key)
```

Output

```
1
2
...
```

Using the keys, you can also iterate through the values

```python
mountains = {
        1 : "Mount Everest",
        2 : "K2",
        ...
}

#iterating through keys of the dictionary
for key in mountains:
    value = mountains.get(key)
    print(value)
```

Output

```
Mount Everest
K2
...
```

Alternatively, you can iterate through an `enumerated` set of keys and values using `.items()`

```python
# Iterate through key-value pairs
for key, value in mountains.items():
    print(f"{key}: {value}")
```

Output
```
1 : Mount Everest
2 : K2
```


### Helpful Dictionary Methods

| Method                          | Description                                                                                                |
| ------------------------------- | ---------------------------------------------------------------------------------------------------------- |
| `dict.clear()`                  | Removes all elements from the dictionary                                                                   |
| `dict.copy()`                   | Returns a shallow copy of the dictionary                                                                   |
| `dict.fromkeys(keys, value)`    | Creates a new dictionary with keys from the iterable and values set to value                               |
| `dict.get(key, default)`        | Returns the value for the specified key if key is in dictionary, else default                              |
| `dict.items()`                  | Returns a view object that displays a list of a dictionary's key-value tuple pairs                         |
| `dict.keys()`                   | Returns a view object that displays a list of all the keys in the dictionary                               |
| `dict.pop(key, default)`        | Removes and returns an element from a dictionary having the given key                                      |
| `dict.popitem()`                | Removes and returns the last inserted key-value pair as a tuple                                            |
| `dict.setdefault(key, default)` | Returns the value of a key if it exists, else inserts the key with the specified value                     |
| `dict.update([other])`          | Updates the dictionary with elements from another dictionary object or from an iterable of key-value pairs |
| `dict.values()`                 | Returns a view object that displays a list of all the values in the dictionary                             |


### Dictionaries and Dataframes
Pandas dataframes are closely related to dictionaries with a column representing each key of the dictionary

For example, this dataframe (represented via the table) can be represented using a dictionary

| Name    | Age | City          |
| ------- | --- | ------------- |
| Alice   | 30  | New York      |
| Bob     | 25  | San Francisco |
| Charlie | 35  | Los Angeles   |

```python
data = {
    "Name": ["Alice", "Bob", "Charlie"],
    "Age": [30, 25, 35],
    "City": ["New York", "San Francisco", "Los Angeles"]
}

```

Each row represents values of the dictionary associated by key, and the row index is the index of the value in the row array. This relationship is how dataframe columns can be accessed using `df[columnName]`

* This is a simplified way of explaining dataframes but for the purposes of this lesson it is sufficient, we will discuss dataframes in more detail in future lessons

As such, you can convert a dictionary to a dataframe as vice-versa.

```python
import pandas as pd

data = {
    "Name": ["Alice", "Bob", "Charlie"],
    "Age": [17, 18, 16],
    "Grade": [11, 12, 10]
}
#converting a dictionary to a dataframe
df = pd.DataFrame(data)

#converting a dataframe to a dictionary
dict_from_df = df.to_dict()
```

### Helpful References
1. [Python Dictionary Documentation](https://docs.python.org/3/tutorial/datastructures.html#dictionaries)
2. [Geeks For Geeks Dictionaries](https://www.geeksforgeeks.org/python-dictionary/)
3. [Dataquest - Python Dictionaries](https://www.dataquest.io/blog/python-dictionaries/)