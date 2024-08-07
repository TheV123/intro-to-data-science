---
layout: page
title:  "Strings"
parent: "Level 2 - Data Visualization Techniques"
nav_order: 2
---

## Strings

Strings are a common data type used store in text, numeric, and symbol values. They are versitile and complex data can be extracted from strings (such as emails, tokens for LLMs, and so much more). In older programming languages like C, strings were often represented as an array of characters, or `char array[size]`. Strings have gotten more complex throughout the years with most programming languages natively supporting it and offering string `immutability` and tracking string length automatically.

### Characters
 While Python does not support the `char` datatype (representing a single character), many packages such as numpy do support it. Still, Python does follow common `unicode` conventions when dealing with character and string type. This allows python to represent symbols and even emojis as a string.
```python
smiley = "😀"
laugh = "😂"

print(text) #Output: 😀
print(smiley) #Output: 😂

```

Characters and strings can also be compared using their `ASCII` value. `ASCII` is a numeric (hexadecimal) value assigned to symbols and characters so that computers can understand them under the hood.
* Since computers only operate in `binary`, or 1s and 0s, representing symbols or letters in computers became difficult because you could not simply convert a number from a decimal base to a binary base. `ASCII` is a standardized appraoch of assigning values to these symbols and letters. `Unicode` then expanded upon `ASCII` and is the most widely used encoding standard used today.

```python
a = "a"
b = "b"
print(a > b) #Output: False
print(a < b) #Output: True
```

### String Manipulation

In Python, strings do support `+` and `*` operations. `+` operator is a form of `concatnation`, which alows for two strings to be joined together. `*` operator allows you to repreat a string

```python
print(smiley * 10) #Output: 😀😀😀😀😀😀😀😀😀😀
print(smiley + laugh + smiley) #Output: 😀😂😀
```

### String Slicing, Indexing, and Traversal

Using the analogy that strings are just an array of characters, we can also use array/list operations to slice, index, and traverse through strings. However, strings do not support item reassignment due to them being `immutable`

``` python
hello = "Hello"
print(hello[0]) #Output: H
print(hello[-1]) #Output: o
print(hello[0:3]) #Output: Hel

#traversing string
for char in hello:
    print(char)

hello[0] = "y" #This will cause an ERROR
print(hello)
```

### Helpful String Methods

| Method                        | Description                                                                                          |
| ----------------------------- | ---------------------------------------------------------------------------------------------------- |
| `str.capitalize()`            | Returns a copy of the string with its first character capitalized                                    |
| `str.endswith(suffix)`        | Returns True if the string ends with the specified suffix                                            |
| `str.find(sub)`               | Returns the lowest index in the string where substring sub is found                                  |
| `str.index(sub)`              | Returns the lowest index in the string where substring sub is found, raises ValueError if not found  |
| `str.isalnum()`               | Returns True if the string is alphanumeric                                                           |
| `str.isalpha()`               | Returns True if the string is alphabetic                                                             |
| `str.islower()`               | Returns True if all characters in the string are lowercase                                           |
| `str.isnumeric()`             | Returns True if the string is numeric                                                                |
| `str.isupper()`               | Returns True if all characters in the string are uppercase                                           |
| `str.lower()`                 | Returns a copy of the string converted to lowercase                                                  |
| `str.lstrip()`                | Returns a copy of the string with leading whitespace removed                                         |
| `str.replace(old, new)`       | Returns a copy of the string with all occurrences of substring old replaced by new                   |
| `str.strip()`                 | Returns a copy of the string with leading and trailing whitespace removed                            |

There are a lot more string methods - be sure to check out the documentation for them

### Helpful References
1. [Python Strings Documentation](https://docs.python.org/3/library/string.html)
2. [Geeks For Geeks Strings](https://www.geeksforgeeks.org/python-string/)
3. [Real Python - Strings and Character Data](https://realpython.com/python-strings/)