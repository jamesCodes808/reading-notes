# JupyterLab and NumPy

### What are the key features and benefits of Jupyter Lab, and how does it differ from Jupyter Notebook?

JupyterLab is a web-based ui for Project Jupyter that allows you to work with text editors, terminals, custom components and Jupyter notebooks. 

Jupyter notebooks are documents that combine live runnable code with data, Markdown, equations (LaTeX), images, interactive visualizations and other rich output.

Some of the key features of Jupyter Lab are:
Text, code consoles and terminals - A scratchpad fo running code interactively, this can be linked to a notebook kernel as the computation log.

Kernel-backed documents - This allows for code in text files (Markdown, Python, R, LaTeX, etc.) to run interactively in a Jupyter kernel.

Notebook cells - Can output and mirror cells into their own tab, and side by side with a notebook. Has simple dashboards and interactive controls. 

Multiple views - Has many different views for documents and different editors. Enables live editing of documents with a live preview.

### What are the main functionalities provided by the NumPy library, and how can it be useful in Python programming, particularly for scientific computing and data manipulation tasks?

NumPy is a Python library that is widely used for numerical computing. It provides support for large, multi-dimensional arrays and matrices, as well as a variety of mathematical functions that can be applied to these arrays. Some of the key functionalities of NumPy include:

- Multi-dimensional array support: NumPy provides a powerful N-dimensional array object that can hold data of any type, including numbers, strings, and other Python objects. This allows for efficient computation on large datasets.

- Mathematical operations: NumPy provides a wide range of mathematical functions for operations such as trigonometry, algebra, and statistics. These functions operate on arrays of data, making it easy to perform complex mathematical operations on large datasets.

- Broadcasting: NumPy provides a mechanism called broadcasting, which allows for efficient computation on arrays of different shapes and sizes. Broadcasting can be used to perform operations on arrays with different dimensions or shapes, which can be useful in scientific computing tasks.
- Indexing and slicing: NumPy provides a powerful indexing and slicing mechanism that allows for efficient access to specific elements of arrays. This can be used to extract specific subsets of data from large arrays, or to manipulate data in various ways.

- Linear algebra: NumPy provides a comprehensive set of linear algebra functions, such as matrix multiplication, eigenvalue and eigenvector computation, and more. These functions can be used for a variety of scientific computing tasks, such as machine learning and data analysis.

With these features and its powerful array object and mathematical functions make it easy to perform complex computations on large datasets, and its linear algebra functions can be used for a wide range of scientific computing tasks.


## Explain the basic structure and properties of NumPy arrays, and provide examples of how to create, manipulate, and perform operations on them.

NumPy arrays are like lists in Python, but they have some special properties that make them more efficient for numerical computing. 

NumPy arrays can be multi-dimensional, meaning that they can have multiple rows and columns. The basic structure of a NumPy array is a collection of elements of the same data type.

To create a NumPy array, you can use the numpy.array() function. Here's an example:

```python
import numpy as np

# Create a 1-dimensional NumPy array
my_array = np.array([1, 2, 3, 4, 5])

# Create a 2-dimensional NumPy array
my_2d_array = np.array([[1, 2, 3], [4, 5, 6], [7, 8, 9]])

```

To manipulate NumPy arrays, you can use indexing and slicing just like you would with lists. Here are some examples:

```python
import numpy as np

# Create a 1-dimensional NumPy array
my_array = np.array([1, 2, 3, 4, 5])

# Access an element in the array
print(my_array[0])  # Output: 1

# Access a slice of the array
print(my_array[1:4])  # Output: [2, 3, 4]

# Assign a new value to an element in the array
my_array[2] = 10
print(my_array)  # Output: [1, 2, 10, 4, 5]


```

NumPy also provides many built-in functions for performing operations on arrays. Here are some examples:


```python
import numpy as np

# Create a 1-dimensional NumPy array
my_array = np.array([1, 2, 3, 4, 5])

# Add 5 to each element of the array
new_array = my_array + 5
print(new_array)  # Output: [6, 7, 8, 9, 10]

# Multiply each element of the array by 2
new_array = my_array * 2
print(new_array)  # Output: [2, 4, 6, 8, 10]

# Compute the sum of all elements in the array
total = np.sum(my_array)
print(total)  # Output: 15

```

## Thing I want to know more about

- I want to get a deeper understanding of the shortcut syntaxes of slicing as I see that it can be used in so many ways and how powerful it is. 

> References
>
>[Jupyter lab overview](https://jupyterlab.readthedocs.io/en/stable/getting_started/overview.html)
>
>[NumPy Tutorial: Data Analysis with Python](https://www.dataquest.io/blog/numpy-tutorial-python/)
>
>[NumPy Tutorial](https://www.tutorialspoint.com/numpy/index.htm)
