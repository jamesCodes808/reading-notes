# File IO & Exceptions

## Reading and Writing Files in Python

- What makes up a file and why its important in Python

A file is made up of 3 parts. 
    1. Header: Contains the metadata of the file such as file size, type and name
    2. Data: Contains the contents of the file 
    3. End of File: Contains special characters that indicate the end of the file such as .jpg, .txt, etc.

Files are important in Python because they allow you to store and retrieve data from your computer's hard drive. This can be useful for a variety of tasks, such as reading data from a file to perform calculations or writing data to a file for long-term storage. 

You could prompt the user to input each number, but that would be tedious and time-consuming. Instead, you could store the numbers in a file and read them into your program using the following code:

```python

with open('numbers.txt', 'r') as f:
    numbers = [int(line) for line in f]

```

This code opens a file called 'numbers.txt', reads each line (which contains a single number), converts each line to an integer using the int() function, and stores the resulting list of numbers in the numbers variable.

- Basics of reading and writing files

To read a file, you can use the open() function with the 'r' (read) mode. This function returns a file object that you can then use to read the contents of the file. For example, you can read the contents of a file called 'example.txt' using the following code:

```python

with open('example.txt', 'r') as f:
    contents = f.read()


```

To write to a file, you can use the open() function with the 'w' (write) mode. This function also returns a file object that you can use to write data to the file. For example, you can write a string to a file called 'output.txt' using the following code:

```python

with open('output.txt', 'w') as f:
    f.write('Hello, world!')


```

## Exceptions 

Exceptions in Python are a way to handle errors that occur during the execution of a program. When an error occurs, Python will raise an exception, which is a type of object that contains information about the error.

You can use try and except statements to catch and handle these exceptions. For example, imagine you have a program that divides two numbers. If the user tries to divide by zero, Python will raise a ```ZeroDivisionError``` . You can catch this exception and handle it gracefully using the following code:

```python

try:
    result = num1 / num2
except ZeroDivisionError:
    print('Error: Cannot divide by zero.')


```

### Things I want to know more about

- Is there a way to include files without using an input form

> References
>
>[Reading and Writing Files in Python (Guide)](https://realpython.com/read-write-files-python/)
>
>[https://realpython.com/python-exceptions/](https://realpython.com/python-exceptions/)