---
layout: page
title:  "Working With Date and Time Data"
parent: "Level 2 - Data Visualization Techniques"
nav_order: 3
---

## Working With Date and Time Data

Date and time data is one of the most common types of data that data scientists will deal with. Datetime data is often used in creating `timeseries` graphs which are a way of analysing a sequence of data points over an interval of time. There are multiple types of date and time data in Python and it helpful to know of multiple types as they each serve different purposes. 

### The Time Module

The time module in Python provides useful functions for working with time data. The main feature of this module is `time.time()` which return the current time with microsecond precision. Working with time data can often be confusing due to timezones, `time.time()` allows for an universal way to track time.

```python
import time

epoch_milli = round(time.time() * 1000)
print(epoch_milli)
```

This code is an example of `epoch milli`, a common method of keeping track of time in programming. This returns the time since the `UNIX Epoch` (Jan 1, 1970 UTC). Regardless of what timezone, or what device you run this on it will give the same time. This makes `epoch milli` very useful when dealing with user data across multiple timezones.

The time module is also used for system related time operations, including `time.sleep()` which suspends execution for a given number of seconds and supports timezone data


### Useful Time Functions

| Function                 | Description                                                                                                                               |
| ------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------- |
| `time.time()`            | Returns the current time in seconds since the Epoch (January 1, 1970).                                                                    |
| `time.sleep(seconds)`    | Suspends execution for the given number of seconds.                                                                                       |
| `time.localtime([secs])` | Converts a time expressed in seconds since the Epoch to a local `time.struct_time`. If no argument is provided, it uses the current time. |
| `time.gmtime([secs])`    | Converts a time expressed in seconds since the Epoch to a UTC `time.struct_time`. If no argument is provided, it uses the current time.   |
| `time.process_time()`           | Returns the CPU time used by the process.                                   |
| `time.timezone`                 | The difference in seconds between UTC and local standard time.              |

### The Datetime Module

The datetime module is one of the most commonly used modules in python for dealing with dates and supports timezones and conversion between timezones. It also allows for easy operations with dates such as "adding" and "subtracting" dates

```python
now = datetime.now()
print(f"Current datetime: {now}")

specific_date = datetime(1999, 10, 12, 23, 10)
print(f"October 12, 1999 at 11:10 pm : {specific_date}")
```

`datetime.now()` returns the current date and time depdending on the system which it is run from, and can be different based on the system's timezone and clock settings. 

To "add" or "subtract" dates the `timedelta` function can be used to describe a period of time

```python
future_date = now + timedelta(days=10) #IMPORTANT
print(f"10 days from now: {future_date}")
```

Pandas has its own variantion of `datetime` data through the use of several functions such as `to_datetime()`

```python
df["Date"] = pd.to_datetime(df["Date"]) #converts a column to datetime

print(df["Date"].dtype) #Output: datetime64[ns]
```

This gives greater control over the data and helpful operations can be performed using the pandas datetime data such as accessing the month, week, or day of the week


```python
df["Year"] = df["Date"].dt.year #Creates a new column Year with the year value of the Date column
df["Month"] = df["Date"].dt.month #Creates a new column Month with the year value of the Date column
```

Datetime objects can be created from strings and vice versa

```python
#Converting a string into a date object
date_obj = datetime.strptime("1999-12-14", "%Y-%m-%d")
print(date_obj) #Output: 1999-12-14 00:00:00

#Presenting a date object as a string
print(date_obj.strftime("%Y-%m-%d")) #Output: 1999-12-14
print(date_obj.strftime("%A")) #Output: Tuesday
```

### Useful Datetime Functions 

| Function                                 | Description                                                                         |
| ---------------------------------------- | ----------------------------------------------------------------------------------- |
| `datetime.now()`                         | Returns the current local date and time.                                            |
| `datetime.today()`                       | Returns the current local date and time, similar to `datetime.now()`.               |
| `datetime.utcnow()`                      | Returns the current UTC date and time.                                              |
| `datetime.strptime(date_string, format)` | Parses a string into a `datetime` object according to a specified format.           |
| `datetime.strftime(format)`              | Converts a `datetime` object to a string according to a specified format.           |
| `datetime.date(year, month, day)`        | Creates a `date` object representing the specified year, month, and day.            |
| `datetime.time(hour, minute, second)`    | Creates a `time` object representing the specified hour, minute, and second.        |
| `datetime.combine(date, time)`           | Combines a `date` object and a `time` object into a `datetime` object.              |
| `datetime.replace()`                     | Returns a new `datetime` object with replaced values for specified fields.          |
| `datetime.timedelta()`                   | Represents the difference between two dates or times.                               |
| `datetime.weekday()`                     | Returns the day of the week as an integer, where Monday is 0 and Sunday is 6.       |
| `datetime.isoweekday()`                  | Returns the day of the week as an integer, where Monday is 1 and Sunday is 7.       |
| `datetime.isoformat()`                   | Returns the date and time in ISO 8601 format.                                       |
| `datetime.timetuple()`                   | Returns a `time.struct_time` object, useful for interacting with the `time` module. |

### Helpful References

* [Python `time` Module Documentation](https://docs.python.org/3/library/time.html)  
* [Python `datetime` Module Documentation](https://docs.python.org/3/library/datetime.html)  
* [Python `datetime` Objects - How to Use](https://realpython.com/python-datetime/)  
* [Python `time` Module - An In-Depth Guide](https://realpython.com/python-time-module/)  
