---
layout: page
title:  "Intro To Charts - Matplotlib"
parent: "Level 2 - Data Visualization Techniques"
nav_order: 4
---

## Intro To Charts - Matplotlib
Charts are used to display data in a visual format to make it easier to understand and interpret and are one of the key tools of data scientists. Charts are used to showcase data findings, reports, and comparisons. Charts can sometimes be made off of `evolving data`, data which can change at any moment. For example, take a dashboard which shows a company's live financials. This chart must be able to handle live data and change when the data changes. Charts must also be able to accurately represent large amounts of data in a method that is easy to understand and visually appealing. Finally, charts convey a message - and a good chart must approprirately convey its indented message wihout bias, cheap tricks, or misrepresenting data (https://vdl.sci.utah.edu/blog/2023/04/17/misleading/)

The important steps towards creating data driven charts are:
1. Understand the type of data that needs to be plotted
2. What type of graphs would fit the data best?
3. Data transformation and cleaning 
4. Chart plotting pipeline
5. Additional visual touches

### Types of Charts

| **Chart Type**   | **Description/Uses**                                                                                           |
| ---------------- | -------------------------------------------------------------------------------------------------------------- |
| **Line Chart**   | Displays trends over time or continuous data.                                                                  |
| **Bar Chart**    | Compares categorical data or shows differences between groups.                                                 |
| **Histogram**    | Shows the distribution of a dataset; useful for understanding frequency.                                       |
| **Scatter Plot** | Observes relationships or correlations between two continuous variables.                                       |
| **Box Plot**     | Displays the distribution of data based on five-number summary (min, Q1, median, Q3, max).                     |
| **Pie Chart**    | Represents proportions of a whole; ideal for displaying percentage breakdowns.                                 |
| **Heatmap**      | Visualizes matrix-like data; often used for correlation matrices or showing intensity.                         |
| **Area Chart**   | Similar to a line chart but with the area under the line filled; used to show cumulative data.                 |
| **Violin Plot**  | Combines aspects of box plots and density plots; shows data distribution and probability density.              |
| **Bubble Chart** | A variation of the scatter plot where data points are represented by bubbles; size indicates a third variable. |
| **Density Plot** | A smoothed version of a histogram; shows the distribution of a variable.                                       |


### Data Cleaning For Graphing

In order to work with plotting libraries like `matplotlib` or `plotly`, proper data cleaning must occur before attempting to create a chart. When examining the data, look for `NULL` values, empty columns, or data that appears `erroneous.` Additional grouping or data transformation including converting to the appropriate datatype (ex - string to datetime) might be required to create graphs. 

```python
#data filtering
df["Date"] = pd.to_datetime(df["Date"])
df = df[df["Date"] > pd.to_datetime("2010-01-01")]

#forcefully converting rows of the Population column to a numeric value
df['Population'] = pd.to_numeric(df['Population'], errors='coerce')
#deleting NA rows - if the to_numeric function fails it will reutrn NA
df_clean = df.dropna(subset=['Population'])
```

### Simple Plots Using Matplotlib

Matplotlib is a widely used Python library for creating static, animated, and interactive visualizations. It is beginner friendly and fast and most commonly used for creating simple plots that dont require much fancy animations or interactivity. 

To use matplotlib you must first install it using `pip`

```
pip install matplotlib
```

Here are some examples of simple plots

1. Line Plot

```python
import matplotlib.pyplot as plt

x = [1, 2, 3, 4, 5]
y = [2, 3, 5, 7, 11]

#creating a line plot using x and y data
plt.plot(x, y, marker='o')

#setting the x-axis label
plt.xlabel('X-axis')
#setting the y-axis label
plt.ylabel('Y-axis')
#setting the graph title
plt.title('Simple Line Plot')

#displaying the plot
plt.show()
```

2. Scatter Plot

```python
import matplotlib.pyplot as plt

x = [1, 2, 3, 4, 5]
y = [2, 3, 5, 7, 11]

#creating a scatter plot using x and y data with red dots
plt.scatter(x, y, color='red')

#setting the x-axis label
plt.xlabel('X-axis')
#setting the y-axis label
plt.ylabel('Y-axis')
#setting the graph title
plt.title('Simple Line Plot')

#displaying the plot
plt.show()
```

3. Bar Chart

```python
# Sample data
students = ['Student 1', 'Student 2', 'Student 3']
grades = [80, 99, 87]

#creating a bar plot using students and grades data
plt.bar(categories, grades, color='skyblue')

#setting the x-axis label
plt.xlabel('Students')
#setting the y-axis label
plt.ylabel('Grades')
#setting the graph title
plt.title('Grades On Midterm 1')

#displaying the plot
plt.show()
```

Plots can also be made using the column of a dataframe instead of passing in data as an array

4. Pie chart

```python
#creating a bar plot using Population and Country columns from df
plt.pie(df["Population"], labels=df["Country"], autopct='%1.1f%%', startangle=140)

#setting the graph title
plt.title('Population Percentage By Country')

#displaying the plot
plt.show()
```

However, for speed and optimization purposes, it is beneficial to convert dataframe columns to `numpy arrays` before plotting

```python

population = df["Population"].to_numpy()
countries = df["Country"].to_numpy()
#creating a bar plot using population and countries arrays
plt.pie(population, labels=countries, autopct='%1.1f%%')
```

### Helpful References

* [Matplotlib Documentation](https://matplotlib.org/stable/contents.html)
* [Matplotlib Tutorials on Matplotlib.org](https://matplotlib.org/stable/tutorials/index.html)
* [Matplotlib Cheatsheet](https://github.com/matplotlib/cheatsheets)
