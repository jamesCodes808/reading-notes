# Ten Thousand 4: Dunder Methods - Statistics - Probability

### What is the purpose of dunder methods in Python? Provide an example of a commonly used dunder method.

Dunder methods allow us to emulate the same behavior as built-in types. One of the most commonly used dunder methods that I have seen is using a `__init__`. This initializes an object with a constructor so it can have built-in objects and default values. An example would be a user class. The user class will have a default name of 'user' and default account type of 'guest'.

```python
class Person:
    
    def __init__(self, name='user', account_type='guest'):
        self.name = name
        self.account_type = account_type

```


### In the video “AI Guru makes $238,800 with misleading paid course,” what was the main ethical issue raised concerning the use of developers’ work, and how might this have been avoided?

The main ethical issue that I noticed in this video is how he misleads and lies about a lot of features of the courses he offers such as how many people were allowed in the course (which he tried to hide from people), a refund policy that never existed (which he added in after people were asking for it), and most importantly, the plagiarism of uncredited authors of code that he stole from in order to monetize from it. 

This probably could have been avoided if proper attributions were made to the developers that he stole 'starter code' from.  

### Describe the Python statistics module and give an example of a function within the module that can be used to perform a common statistical operation.

The statistics module can be imported along with tools to help calculate averages and measures of central location, measures of spread and relations between two inputs. An example of a function within the statistics module that can be used to perform a common statistical operation is the `mean()` function. 

```python
import statistics

data = [1, 2, 3, 4, 5]

mean_value = statistics.mean(data)

print("The mean of the data is:", mean_value)
```

## Things I  want to know more about

- How and when to use the other common functions in the statistics module

- How to give proper attribution to a developer's code so I don't end up like Siraj

- Using more dunder methods

> References
> 
>[Enriching Your Python Classes With Dunder (Magic, Special) Methods](https://dbader.org/blog/python-dunder-methods)
>
>[AI Guru makes $238,800 with misleading paid course. doesn't credit developers. | Siraj Raval FGF](https://www.youtube.com/watch?v=7jmBE4yPrOs)
>
>[Tutorial: Basic Statistics in Python — Probability](https://www.dataquest.io/blog/basic-statistics-in-python-probability/)