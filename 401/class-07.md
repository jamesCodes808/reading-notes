# Ten Thousand 2: Scope 

## Scope in Python

In most programming languages the scope of a name defines the area in a program where that name can be accessed. 
This can include functions, variables, objects, lists, etc. Usually a name is only accessible by other code in its scope
like a function using a temp variable in its code block. Scope is important for avoiding name collisions and unpredictable 
behavior in code. In programming, there are two main scopes, global and local. Amongst others, 
python resolves names using the so-called LEGB rule, which is named after the Python scope for names. 
The letters in LEGB stand for Local, Enclosing, Global, and Built-in. Here’s a quick overview of what these terms mean:

### global

The names that you define in this scope are available to all your code.

### nonlocal

A special scope that exists only in nested function. 
The scope is visible from the code of the inner and enclosing functions.
This is a special scope that is between global and local scope.

## Reading Q's

- Explain the concept of variable scope in Python and describe the difference between local and global scope. 
Provide an example illustrating the usage of both.

Variable scope is the first and most simple rule for scopes. It is that the scope of a variable/name depends on the place
in your code where you have created that variable. 

The difference between local and global scope is that global scope variables are available to all of the code while local 
scope is only available to code where this variable was created. 

An example would be, how this global_variable can be accessed from all functions but the local_var can only be accessed
in the local_func() where it was created.
```python
global global_variable
global_variable = "you can use me anywhere"


def local_func():
    local_var = "i can only be accessed in this function"
    print(local_var)
    print(global_variable)
    
def some_other_func():
    print(global_variable)


```

- How do the global and nonlocal keywords work in Python, and in what situations might you use them?

The way that the global keyword works in python is by binding a variable name to the keyword 'global' then on the next line, assigning it some data:
```python
global dice
dice = [1,2,3,4,5,6]
```

The way that the nonlocal keyword works in python is when you nest functions inside of other functions,
that variable is then binded to the keyword 'nonlocal':
```python
def outer():
    outer_var = 'i am outer'
    def inner():
        nonlocal inner_var 
        inner_var = 'i am enclosing'
        print(outer_var) # this will work as its locally scoped to outer() and accessible to inner()
        print(inner_var) # this will work as it is in the enclosing scope of inner() 
    print(inner_var) # when trying to call this variable, it will not work and gives an 'unreferenced' error because it is in the enclosing scope of inner()
    
```

This is useful when you want to get better encapsulation of data and restrict direct access of this data to the function enclosing the other function.

## Big O

- In your own words, describe the purpose and importance of Big O notation in the context of algorithm analysis.

It is important because we can calculate which algorithm is the least time-consuming through big O notation. This will help us decide
which algorithm to use in a certain situation. when there is big data involved, these big O space and time complexities are so important to 
ensuring that time and space are being used at the most efficient level.

- Based on the Rolling Dice Example, explain how you would simulate a dice roll using Python. 
Describe how you would use code to calculate the probability of rolling a specific number (e.g., the probability of rolling a 6) over a large number of trials.

Based on the examples, I would simply import random module and use the randint(1,6) function with arguments of 1 through 6. 
then I would use a for loop in the range of about 100 rolls, and catch each roll that equaled a certain number, I would then divide that total number by the number of rolls 
to calculate the probability, just like this:

```python
import random
count = 0

def roll_dice():
    return random.randint(1,6)
        
for i in range(1,51):
    if roll_dice == 3:
        count += 1

probability = (count/50) * 100

print(f"the probability of rolling a 3 is {probability}%")

```

## Things I want to know more about

- definitely want to learn more about enclosing/local scope

>References
>
> [Python Scope](https://realpython.com/python-scope-legb-rule/)
> 
> [Rolling Dice Examples](https://artofproblemsolving.com/wiki/index.php/Basic_Programming_With_Python#Random)