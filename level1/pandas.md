---
layout: page
title:  "Intro To Pandas"
parent: "Level 1 - Introduction To Python and Data Analytics"
nav_order: 10
---

## Introduction

Pandas is a powerful library for data manipulation and analysis. It provides data scientists with high-performance, easy-to-use data structures and tools for working with structured data. It is one the main tools in a data scientist's toolbelt when handling with large amounts of data.

### Installing & Importing Pandas

To use Pandas, you need to install it first. You can install Pandas using `pip`
``` bash
pip install pandas
pip show pandas
```
To use Pandas in your program, you can import it at the top of the program
```python
import pandas
```

You can optionally specify a shorthand name to call your import
```python
import pandas as pd
```

### Dataframes

The dataframe is the primary data structure used in pandas which features a table style view resembling a `spreadsheet` or an `SQL table`. It is a 2 dimensional data structure containing rows representing different `records` and columns representing different `catagories`

```python
data = {'Name': ['Alice', 'Bob', 'Charlie'],
        'Age': [25, 30, 35],
        'City': ['New York', 'San Francisco', 'Los Angeles']}
df = pd.DataFrame(data)
```

Dataframes work similar to `dictionaries`, a concept that will be discussed more in detail in a later lesson. However, each column of a dataframe is also acts similar to an `array`. It is easiest to view a dataframe as kind of an array of dictionaries, each with a key corresponding to a column

### Getting Data
There are a lot of useful websites available for data scientists insterested in finding data for research, projects, or presentations.


### Reading CSV Files

CSV Files are one of the most common forms of storing `relational data` (being structured data with columns). CSV files are often represented through `spreadsheets`.

```python
# Reading a CSV file
df = pd.read_csv('./countries of the world.csv')

# Writing to a CSV file
df.to_csv('output.csv', index=False) #writes without the row number
```

### Viewing Dataframes

```python
# Display the first 10 rows
df.head(10)

# Display the last 10 rows
df.tail(10)

# Display basic statistics of numerical columns
df.describe()

# Display the amount of rows and columns in DataFrame
print(df.shape)

# Get information about the DataFrame
df.info()
```

### Data Selection

```python
# Select a single column
df['Country']

# Select multiple columns
df[['Country', 'Population']]

# Select rows by index value
df.loc[0:5]
```

### Data Filtering And Sorting

Like numpy's `where` function, pandas allows for filtering data frames through conditional indexing. Conditional filtering works using `bitwise` operators and multiple conditions can be passed in to render

```python
highly_populated_nations = df[df["Population"] > 75000000]

low_populated_rich_nations = df[(df["Population"] < 75000000) & (df["GDP ($ per capita)"] > 20000)]
```

Sorting can be done using the `sort_values` method that allows you to sort the data by one or more columns. Additionaly, pandas also offers `nlargest` and `nsmallest` functions as a quick way to filter out the minimum or maximum values in a column

```python
df_sorted = df.sort_values(by='Population', ascending=False)
print(df_sorted[['Country', 'Population']].head())
```

```python
top_5_gdp = df.nlargest(5, 'GDP ($ per capita)')
df['Population Density'] = df['Population'] / df['Area (sq. mi.)']
bottom_5_density = df.nsmallest(5, 'Population Density')
```

### Helpful References
* [Pandas Official Documentation](https://pandas.pydata.org/docs/)
* [10 Minutes to Pandas](https://pandas.pydata.org/docs/user_guide/10min.html)
* [Pandas Cheat Sheet](https://pandas.pydata.org/Pandas_Cheat_Sheet.pdf)