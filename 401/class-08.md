# Ten Thousand 3

## List Comprehensions

- What is the basic syntax of Python list comprehension, and how does it differ from using a for loop to create a list? Provide an example of a list comprehension that squares the elements in a given list of integers.
    
The basic syntax for list comprehension includes three things,
1. An expression inside of square brackets. expression
2. An object that the expression is going to work on. item
3. An iterable list of objects to build a new list from. list
And it loooks like this: 

```python
new_list = [expression for item in list]
# an example of using it to convert values of a dice to integers
rolled_dice = [int(i) for i in rolled_dice]
```

The only difference from list comprehension and using a for loop to use an expression to create a list is its speed 
and elegance for doing the same thing. 

```python
# an example of using list comprehension to square the elements in a given list of integers
squared_list = [pow(i,2) for i in list]
```

## Decorators

- What is a decorator in Python?
A decorator wraps a function which modifies its behavior.

- Explain the concept of decorators in Python. How do they work, and what are some common use cases for them? Provide an example of a simple decorator function from the reading.

The way that decorators work is you have 4 pieces:
1. A 'root level' function that takes a function in as an argument 
2. An inner function defined inside of the 'root level' function and returned based on a conditional 
3. A 'decorator' function that's been passed into the 'root level' function
4. Invoking of the 'decorator' function inside the 'root level' functions inner function

Some common use cases for a decorator is when you want to activate a function based on the user being logged in or 
not, to time a function, debugging code and registering plugins.
```python
# an example of decorators being used to check if a user is logged in
def login_required(func):
    def wrapper(request, *args, **kwargs):
        if not request.user.is_authenticated:
            return redirect('login')
        return func(request, *args, **kwargs)
    return wrapper

@login_required # this is the same as doing restricted_view = login_required(restricted_view)
def restricted_view(request):
    # do something if user is authenticated
```

## Things I want to learn more about

- How I can implement decorators in my code and more hands on practice using them

>References
> 
> [List Comprehensions in Python](https://www.pythonforbeginners.com/basics/list-comprehensions-in-python)
> 
> [Primer on Python Decorators](https://realpython.com/primer-on-python-decorators/)