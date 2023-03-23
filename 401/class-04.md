# Classes and Recursive Thinking

## Basics of Classes and Objects

Classes are like blueprints for creating objects. An object is an instance of a class. Think of a class as a cookie cutter and an object as a cookie. The cookie cutter defines the shape and characteristics of the cookie, while each cookie is a unique instance that can have different flavors or toppings. Here is an example using a Person class and creating Person objects with that class.

```python

class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    def walk(self):
        print(f"{self.name} is walking.")

person1 = Person("Alice", 25)
person2 = Person("Bob", 30)

print(person1.name) # Output: "Alice"
person2.walk() # Output: "Bob is walking."

```

## Thinking Recursively

Thinking recursively in Python involves solving a problem by breaking it down into smaller, simpler problems that can be solved in a similar way. The process of recursion involves a function calling itself repeatedly until a base case is reached where the function stops calling itself and returns a result. 

This technique is useful when dealing with problems that can be broken down into similar subproblems, such as traversing a tree or searching a maze. Recursion is an important concept in programming because it allows us to write clean, concise code that is easier to read and understand. An example would be the factorial function that we did:

```python

def factorial(n):
    if n == 1:
        return 1
    else:
        return n * factorial(n - 1)

```

## Things I want to know more about

- Better understanding of recursion and when to use it over not using it

> References
> 
>[Classes and Objects](https://www.learnpython.org/en/Classes_and_Objects)
>
>[Thinking Recursively in Python](https://realpython.com/python-thinking-recursively/)