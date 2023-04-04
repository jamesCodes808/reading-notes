# Python Pandas

### Explain the purpose and basic functionality of the Pandas library. What are some common operations that can be performed on data using Pandas, and how do they contribute to data analysis and manipulation?

Pandas is a python library that includes some essential tools used for data analysis. Some of the basic functions of the Pandas library is loading, preparing, analyzing, manipulating, joining, merge, reshape and pretty much anything with data. 

Some common operations that are performed with Pandas are:

Reading data:

```python
import pandas as pd

data = pd.read_csv('my_file.csv')

# can also do
# read_excel, read_clipboard, read_sql, etc

```

Writing Data:

```python
data.to_csv('my_new_file.csv', index=None)

# can also do
# .to_excel, .to_json, .to_pickle, etc.

```

Checking Data:

```python
# Print the first 3 rows of the data. Similarly to .head(), .tail() will look at the last rows of the data.
data.head(3)

# prints the 8th row
data.loc[8]

# prints the value of the 8th row on 'column_1'
data.loc[8, 'column_1']

# Subset from row 4 to 6 (excluded)
data.loc[range(4,6)]

```

Logical operations:

```python
# Subset the data thanks to logical operations. To use & (AND), ~ (NOT) and | (OR), you have to add “(“ and “)” before and after the logical operation.
data[data['column_1']=='french']
data[(data['column_1']=='french') & (data['year_born']==1990)]
data[(data['column_1']=='french') & (data['year_born']==1990) & ~(data['city']=='London')]

# Instead of writing multiple ORs for the same column, use the .isin() function
data[data['column_1'].isin(['french', 'english'])]


```

Basic Plotting (using the matplotlib package):

```python
# displays line graph 
data['column_numerical'].plot()

# displays a histo gram graph 
data['column_numerical'].hist()

# In Jupyter, needed in notebook before plotting
%matplotlib inline

```

Updating Data:

```python
# Replaces the 8th row at column_1 
data.loc[8, 'column_1'] = 'english'

# changes the values of multiple rows in one line
data.loc[data['column_1']=='french', 'column_1'] = 'French'

```

### What are the primary data structures in Pandas, and how do they differ in terms of use cases?

In Pandas, it seems like the primary data structures used are:

- 'DataFrames' - a 2D labeled data structure that consists of rows and columns, which is similar to a spreadsheet or SQL table. Each column in a DataFrame can have a different data type (integers, floating-point numbers, strings, etc.). A DataFrame can be seen as a collection of Series that share the same index.

- 'Series' - a 1D array-like object that can store data of any type,(integers, floating-point numbers, strings, Python objects, etc.). Each element in a Series is associated with an index, which can be used to access the elements.

Depending on the type of data you're working with and the operations you need to perform will decide which data structure you need to use. 

For example, if you are working with time-series data or any other data that can be represented as a one-dimensional array, you can use a Series. On the other hand, if you are working with tabular data that has multiple variables, you should use a DataFrame.


### Describe the process of loading a dataset into a Pandas DataFrame. What are some common file formats that can be used, and which Pandas functions are utilized to read these formats?

Loading a dataset into a Pandas DataFrame is a simple process that can be done in a few steps.

First, you need to have your data in a file format that Pandas can read. Some common file formats include CSV, Excel, JSON, and SQL databases.

Let's take CSV as an example. CSV stands for Comma Separated Values, and it's a simple file format that stores data as a table. Each row in the table represents a record, and each column represents a variable.

To load a CSV file into a Pandas DataFrame, you can use the read_csv() function. Here's an example:

```python
import pandas as pd

# Load CSV file into DataFrame
df = pd.read_csv('mydata.csv')

# Print first 5 rows of the DataFrame
print(df.head())

```

In this example, we're loading a CSV file called mydata.csv into a DataFrame called df. The read_csv() function automatically detects the column headers and the delimiter used in the file.

Once the data is loaded into a DataFrame, you can start working with it using various Pandas functions. For example, you can filter rows, select columns, group data, compute statistics, and more.

## Things I want to know more about
- More experience with Pandas and where we can use it when developing applications.

>References
>
>[What is Pandas? Why and How to Use Pandas in Python](https://www.youtube.com/watch?v=dcqPhpY7tWk&t=391s)
>
>[10 minutes to pandas](https://pandas.pydata.org/pandas-docs/stable/user_guide/10min.html)
>
>[pandas for Data Science](https://realpython.com/learning-paths/pandas-data-science/)