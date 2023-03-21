# Data Structures and Algorithms


- What is 1 of the more important things you should consider when deciding which data structure is best suited to solve a particular problem?

One of the more important things to consider is what you want your data structure to do and how you want it to expand. For example, if memory is not a problem and you want to create a data structure that has easily searchable data, you could go with an array. 

If you have a data structure that is only used for a waiting line or something like a help ticket, you can use a queue or stack. 

It all depends on the use case of the data in a certain feature or application.

- How can we ensure that we’ll avoid an infinite recursive call stack?

We have to make sure that we write the function correctly and have a combination of a base case and a recursive case in the recursive function. 

The base case is when the function does not call itself and the recursive case is when the function calls itself. 

Ultimately you want it to have a base case that ends the function called before the recursive case, which calls the function again.

Example: 

```python

def countdown(i):
    print i
    # base case
    if i <= 1:
        return
    # recursive case
    else: 
        countdown(i-1)

```

## Things I want to know more about

I want to know more about the application of these data strutures and get more hands on experience on them.

> References
> 
>[Recursion in software development](https://www.youtube.com/watch?v=vPEJSJMg4jY)
>
>[DATA STRUCTURES you MUST know (as a Software Developer)](https://www.youtube.com/watch?v=sVxBVvlnJsM)
>
>[Big O Notation](https://www.youtube.com/watch?v=v4cd1O4zkGw)
>
>[Basic Data Structures](https://towardsdatascience.com/8-common-data-structures-every-programmer-must-know-171acf6a1a42?gi=d6f66f16e8dd)
>
>[Why you should learn Big-O and stop hacking your way through algorithms](https://triplebyte.com/blog/why-you-should-learn-big-o-and-stop-hacking-your-way-through-algorithms)