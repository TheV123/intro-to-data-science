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

### Helpful References

* [Plotly Express Documentation](https://plotly.com/python/plotly-express/)
* [Plotly Graph Objects Documentation](https://plotly.com/python/graph-objects/)
* [Python Plotly Tutorial](https://www.datacamp.com/tutorial/python-plotly-express-tutorial)

