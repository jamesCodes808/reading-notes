# Pythonisms

## What are dunder methods in Python, and how do they allow for the customization of built-in behavior in classes? 
Provide an example of a common dunder method and its purpose.

Dunder methods in Python, short for "double underscore" methods, are special methods that allow us to customize the behavior of built-in operations in classes. These methods are also known as magic methods or special methods.

Dunder methods are enclosed in double underscores (__) at the beginning and end of their names. They are automatically called by Python in response to certain events or operations. By implementing these methods in our classes, we can define how our objects should behave when certain operations are performed on them.

One common dunder method is `__init__`. It is used to initialize objects when they are created from a class. This method is called automatically when we create a new instance of a class, and it allows us to set up the initial state of the object.

Here's an example of how the `__init__` method works:

```python
class Car:
    def __init__(self, brand, model):
        self.brand = brand
        self.model = model

my_car = Car("Tesla", "Model S")
print(my_car.brand)  # Output: Tesla
print(my_car.model)  # Output: Model S

```

Some other commonly used dunder methods include `__str__` for string representation, `__eq__` for equality 
comparison,`__len__` for determining the length, and `__add__` for addition.


## Explain the concept of an iterator in Python. How do you create a custom iterator using the iter() and next() 
methods, and why are they important for enabling iteration in a class?

An iterator is an object that allows us to traverse through a collection of elements or values one by one. It 
provides a way to access the elements of an object sequentially without exposing the underlying implementation details. Iterators are widely used in Python for looping over data structures such as lists, tuples, dictionaries, and even custom objects.

To create a custom iterator in Python, we need to define a class that implements the `__iter__()` and `__next__()` methods. The `__iter__()` method initializes the iterator and returns itself, while the `__next__()` method returns the next element from the iterator.

```python
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

class LinkedList:
    def __init__(self):
        self.head = None

    def append(self, data):
        new_node = Node(data)
        if not self.head:
            self.head = new_node
        else:
            current = self.head
            while current.next:
                current = current.next
            current.next = new_node

    def __iter__(self):
        self.current = self.head
        return self

    def __next__(self):
        if self.current is None:
            raise StopIteration
        data = self.current.data
        self.current = self.current.next
        return data

```

## What is a generator in Python, and how does it differ from a regular function? Illustrate your answer with an 
example of a generator function using the ‘yield’ keyword.

A generator is a special type of function that allows us to generate a sequence of values, one at a time, instead of 
computing and returning all the values at once. The main difference between a generator and a regular function is that a generator uses the `yield` keyword instead of the `return` keyword to produce a value. When a generator function is called, it returns an iterator object that can be used to iterate over the generated values.

An example of a simple generator function that generates even numbers: 

```python
def even_numbers(limit):
    num = 0
    while num <= limit:
        yield num
        num += 2

for number in even_numbers(10):
    print(number)

# Output: 0, 2, 4, 6, 8, 10

```

## Define decorators in Python and explain their primary use case. How can you create and apply a custom decorator to 
a function or method? Provide a simple example to demonstrate this concept.

Decorators are a way to modify the behavior of functions or methods without changing their source code. They allow 
you to wrap a function inside another function, adding some extra functionality to it. Decorators are defined using the `@` symbol followed by the name of the decorator function or class, and they are placed just before the function or method definition.

Some of the primary use cases for decorators is to add common functionalities, such as logging, timing, or input 
validation, to multiple functions or methods in a clean and reusable way. 

To create a custom decorator, you can define a function or class that takes the function being decorated as an argument, adds the desired functionality, and returns the modified function. Then, you can apply the decorator to a function or method by using the `@` symbol followed by the name of the decorator above the function or method definition.

```python
def uppercase_decorator(func):
    def wrapper(*args, **kwargs):
        result = func(*args, **kwargs)
        return result.upper()
    return wrapper

@uppercase_decorator
def greet(name):
    return f"Hello, {name}!"

print(greet("John"))  # Output: HELLO, JOHN!

```

## Things I want to know more about

- I want to be able to use these concepts in my code more often, especially with DSA
- Is the __next__ the same thing as the built in .next?

> References
> 
> [Dunder Methods](https://dbader.org/blog/python-dunder-methods)
> 
> [Iterators](https://dbader.org/blog/python-iterators)
> 
> [Generators](https://dbader.org/blog/python-generators)
> 
> [What are Generators](https://realpython.com/lessons/what-are-python-generators/)
> 
> [Decorators](https://realpython.com/primer-on-python-decorators/)