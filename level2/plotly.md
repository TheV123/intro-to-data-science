---
layout: page
title:  "Intro To Charts - Plotly"
parent: "Level 2 - Data Visualization Techniques"
nav_order: 5
---


## Intro To Charts - Plotly

Plotly is a powerful library that excels at creating animated and interactive charts and graphs. It also supports multiple export formats and is commonly used in websites. It is also simple to use and highly customizable, providing for great control over animation, interactive elemements (ex. buttons, sliders, groups), and has multiple cool colorschemes

To get started make sure to install plotly and all of its requirements

```
pip install plotly
```

### Creating Simple Charts

Lets import the plotly library. Oftentimes this is used in combination with the `pandas` and `numpy` libraries for appropriate data transformation

```python
import plotly.express as px
import pandas as pd
import numpy as np
```

Once the data has been imported and transformed(please see previous lesson on Intro To Charts - Matplotlib for more details) a plotly plot can be assigned to a figure.

```python
fig = px.scatter()
fig.add_scatter(x=amzn_df["Date"], y=amzn_df["High"], mode="markers", color='red') #adds a chart of Date vs High to the grid
fig.add_scatter(x=amzn_df["Date"], y=amzn_df["Low"], mode="markers") #adds a chart of Date vs Low to the grid
#note that both of these `traces` occupy the same grid
```

Multiple `traces`, or groups of data, can be added to a single plot by defining the charted data in seperate lines using the `add_(plotname)`. This will automatically change the color of each trace and add a `legend` where you can show/hide an individual trace

Title and chart axis can be be edited using the `update_layout` function and can be shown using the `show` function

```python
fig.update_layout(title="Amazon Stock Information", xaxis_title="Date", yaxis_title="Dollars ($)")
fig.show()
```

### Plotly Graph Objects

Often when dealing with more complicated data, animated data, and having multiple types of plots in the same grid, the `graph_objects` module can be used from plotly

```python
import plot.graph_objects as go
```

Making a figure in `graph_objects` is quite similar to `express`, but traces are added by adding seperate `go plots`

```python
fig = go.Figure()

# adding multiple line plots to the same grid
fig.add_trace(go.Scatter(x=[1, 2, 3, 4], y=[10, 15, 13, 17], mode='lines', name='Series 1'))
fig.add_trace(go.Scatter(x=[1, 2, 3, 4], y=[12, 9, 15, 12], mode='lines', name='Series 2'))

fig.update_layout(title='Simple Line Plot', xaxis_title='X Axis', yaxis_title='Y Axis')
fig.show()
```

This is great for when different types of plots have to be added to the same figure. This example adds a line chart with a `sine curve` to a bar chart.

```python
import plotly.graph_objects as go
from plotly.data import tips #this is a sample dataset from plotly

df = tips()
#groups by 'day' and sums all the values of each day
summed_values = df.groupby(by="day", as_index=False).sum(numeric_only=True)

#assigns the days of the week to numbers so that the line plot and the bar chart can have the same axis
day_order = {"Thur": 0, "Fri": 1, "Sat": 2, "Sun": 3} 
summed_values["order"] = summed_values["day"].map(day_order)
summed_values = summed_values.sort_values(by="order")
```

Adding in the traces

```python
fig = go.Figure()

# Add bar chart
fig.add_trace(go.Bar(
    x=summed_values["day"],
    y=summed_values["size"],
    name="Total number of diners",
))

# Add line plot
fig.add_trace(go.Scatter(
    x=summed_values["day"],
    y=summed_values["total_bill"],
    name="Total bill amount",
    mode="lines+markers",
    yaxis="y2"
))

```

When updating the title and grid scale, each individual trace can be customized

```python
fig.update_layout(
    xaxis_title="Day of Week",
    yaxis_title="Number of Diners",
    yaxis2=dict(title="Total Bill Amount", overlaying="y", side="right"), #this edits the axis of the line plot
)

```

### Plotly Chart Examples

`px.data` has several datasets that are built to demonstrate plotly's capabilities. These datasets have been cleaned and are easy to animate

```python
df = px.data.gapminder()
df_2007 = df[df['year'] == 2007]

```

Choropleth plots are used to visualize data in a map or grid basis using colors to show values. The colorscheme can be modified using the `color_continious_scale` (for numeric data) or `color_discrete_scale` (for categorical data) parameters

```python
choropleth_plot = px.choropleth(df_2007,
                         locations='iso_alpha',
                         color='lifeExp',
                         hover_name='country',
                         title='Life Expectancy by Country in 2007',
                         color_continuous_scale=px.colors.sequential.Plasma)
choropleth_plot.show()
```

Scatter plots can be used to showcase many features of a dataset - the size of the dots as well as their color can be modified as well as data on the x and y axis. The `size` parameter can be used to variably scale the size depending on the value of a feature. The `color` parameter can be used to assign a color to a dot based on a category or value.  

```python
scatter_plot = px.scatter(df_2007, x='gdpPercap', y='lifeExp', size='pop', color='continent', hover_name='country', log_x=True, size_max=60)

scatter_plot.update_layout(
    xaxis_title='GDP Per Capita (Logarithmic)',
    yaxis_title="Life Expectancy (years)"
)
scatter_plot.show()
```

### Animated Plots

Plots using data from `px.data` can be animated easily by providing an `animation_frame` argument. A slider will be automatically created for animated plots but can be modified in the `update_menu` parameter in the `update_layout` function. 

```python
animated_plot = px.scatter(df, x='gdpPercap', y='lifeExp', size='pop', color='continent', hover_name='country', log_x=True, size_max=60, animation_frame='year', animation_group='country', range_x=[200, 100000], range_y=[25, 90])

animated_plot.update_layout(
    title="GDP Per Capita vs Life Expectancy Over Time",
    xaxis_title='GDP Per Capita (Logarithmic)',
    yaxis_title="Life Expectancy (years)"
)
animated_plot.show()
```

For external dataframes, individual frames of data need to be added to be animated on. 

```python
import plotly.graph_objects as go
import numpy as np

# Generate sample data
x = np.linspace(0, 10, 100)
y = np.sin(x)

fig = go.Figure(
    data=[go.Scatter(x=x[:1], y=y[:1], mode='lines', line=dict(color='red', width=2))]
)

# create frames for animation by iterating through the data
frames = [go.Frame(data=[go.Scatter(x=x[:i+1], 
                                    y=y[:i+1], 
                                    mode='lines', 
                                    line=dict(color='red', 
                                    width=2))])
          for i in range(1, len(x))]

# add frames to the figure
fig.frames = frames

```

A button or slider needs to be added to play the animation

```python
fig.update_layout(
    updatemenus=[dict(
        type='buttons',
        showactive=False,
        buttons=[dict(label='Play',
                      method='animate',
                      args=[None, dict(frame=dict(duration=50, redraw=True), fromcurrent=True)])]
    )]
)
```

### Helpful References

* [Plotly Express Documentation](https://plotly.com/python/plotly-express/)
* [Plotly Graph Objects Documentation](https://plotly.com/python/graph-objects/)
* [Python Plotly Tutorial](https://www.datacamp.com/tutorial/python-plotly-express-tutorial)
* [Animated Plots in Plotly](https://plotly.com/python/animations/)

