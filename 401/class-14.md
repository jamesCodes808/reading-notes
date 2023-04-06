# Data Visualization

### What are the key differences between Matplotlib, Seaborn, and Bokeh libraries in terms of their features and use cases? Provide an example of a specific visualization that is more suitable for each library.

Matplotlib, Seaborn, and Bokeh are all libraries used for data visualization in Python, but they have some key differences in terms of their features and use cases.

Matplotlib is a versatile library that provides a wide range of plot types and customization options, making it a popular choice for creating static visualizations. It has a large user base and extensive documentation, making it relatively easy to learn and use. An example of a visualization that is more suitable for Matplotlib would be a line chart that shows the trend of a stock price over time:

```python
import matplotlib.pyplot as plt

x = [1, 2, 3, 4, 5]
y = [10, 12, 8, 15, 20]

plt.plot(x, y)
plt.title('Stock Price Trend')
plt.xlabel('Time')
plt.ylabel('Price')
plt.show()

```

Seaborn, on the other hand, is a library that is specifically designed for statistical data visualization. It provides a high-level interface for creating attractive and informative statistical graphics. Seaborn has built-in support for various statistical plots such as scatterplots, lineplots, barplots, and histograms, making it a popular choice for exploratory data analysis. An example of a visualization that is more suitable for Seaborn would be a scatterplot that shows the relationship between two variables.

```python
import seaborn as sns
import pandas as pd

df = pd.read_csv('data.csv')
sns.scatterplot(x='age', y='income', data=df)
sns.set_style('darkgrid')
sns.set_palette('dark')
sns.set(rc={'figure.figsize':(10,8)})
plt.title('Income vs. Age')
plt.show()

```

Bokeh is a library that is used for creating interactive visualizations that can be displayed in web browsers. It provides a set of tools for creating interactive plots, dashboards, and data applications. Bokeh is ideal for creating visualizations that allow users to interact with data in real-time. An example of a visualization that is more suitable for Bokeh would be an interactive heatmap that shows the correlation between various features of a dataset.

```python
from bokeh.io import output_file, show
from bokeh.layouts import gridplot
from bokeh.plotting import figure
from bokeh.models import ColumnDataSource
from bokeh.transform import linear_cmap
import pandas as pd

df = pd.read_csv('data.csv')
source = ColumnDataSource(df)

corr = df.corr()
values = corr.values.tolist()
features = corr.columns.tolist()

p = figure(title='Correlation Heatmap',
           x_range=features, y_range=features,
           tools='hover,save', toolbar_location='below')

mapper = linear_cmap(field_name='value', palette='Spectral11', low=-1, high=1)
p.rect(x='x', y='y', width=1, height=1,
       source=source,
       fill_color=mapper,
       line_color=None)

p.xaxis.major_label_orientation = 1
p.xaxis.axis_label = 'Features'
p.yaxis.axis_label = 'Features'

output_file('heatmap.html')
show(p)

```

### In the Seaborn library, what are the main functions to create relational, categorical, and distribution plots? Briefly explain the purpose of each type of plot and provide an example use case.

Seaborn is a Python library used for data visualization. It has many functions to create different types of plots. Here are some of the main functions to create relational, categorical, and distribution plots:

- Relational Plots: Seaborn provides functions to create scatter plots, line plots, and regression plots. These plots help to understand the relationship between two or more variables.

Example:

```python
import seaborn as sns
tips = sns.load_dataset("tips")
sns.scatterplot(x="total_bill", y="tip", data=tips)
```

This code will create a scatter plot of the "total_bill" column on the x-axis and the "tip" column on the y-axis from the "tips" dataset.

- Categorical Plots: Seaborn provides functions to create categorical plots such as box plots, violin plots, and swarm plots. These plots help to understand the distribution of categorical variables.

Example:

```python
import seaborn as sns
tips = sns.load_dataset("tips")
sns.boxplot(x="day", y="total_bill", data=tips)
```

This code will create a box plot of the "total_bill" column on the y-axis and the "day" column on the x-axis from the "tips" dataset.

- Distribution Plots: Seaborn provides functions to create distribution plots such as histograms, kernel density plots, and rug plots. These plots help to understand the distribution of continuous variables.

Example:

```python
import seaborn as sns
tips = sns.load_dataset("tips")
sns.histplot(data=tips, x="total_bill")

```
This code will create a histogram of the "total_bill" column from the "tips" dataset.


### Discuss the role of the Seaborn Cheat Sheet in a Python developer’s workflow. What are some key sections or elements featured in the cheat sheet that can help a developer quickly reference Seaborn functionalities?

The role of the Seaborn Cheat Sheet can be used as a reference to the many ways to display the visualization of data. I can see it being extremely useful since there are so many different types of graphs to plot for data.

Some key sections that I see being helpful for my work flow and reference is the 'Categorical Plots' section and the Basics/Data section. With these 2 sections it should not be too hard getting started. 

## Things I want to know more about

I definitely want to learn more about the further customization of these data plots from seaborn that I saw in the cheat sheet. Also, further my knowledge on using this in combination with pandas to create beautiful charts.

I also want to know when is it preferred to use sklearn's LinearRegression model over seaborn's? Or do we just usually use the more powerful tool, in this case, seaborn.

>References
>
>[matplotlib-tutorial](https://github.com/rougier/matplotlib-tutorial)
>
>[Seaborn tutorial](https://seaborn.pydata.org/tutorial.html)
>
>[Bokeh tutorial](https://hub.gke2.mybinder.org/user/bokeh-bokeh-notebooks-t20j4lpw/notebooks/tutorial/00%20-%20Introduction%20and%20Setup.ipynb)
>
>[Seaborn Cheat Sheet](https://s3.amazonaws.com/assets.datacamp.com/blog_assets/Python_Seaborn_Cheat_Sheet.pdf)