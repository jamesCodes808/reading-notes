# Ten Thousand Game 1: Random Module and Risk Analysis

## Random Module in Python

The Random Module at its core allows you to generate random numbers in a given range, get a random element in a list, create random strings and numbers while providing access to functions that support many other operations. 

## Random Functions in Python

First off, in order to use Random functions in Python you have to:

```python
import random

```

Some of the built in Random module functions are:

#### random():
Returns a random floating number between 0 and 1. To return a larger number, multiply random() to a larger value. Example, to get a random number between 0 and 20:

```python
import random
random.random() * 20
```

#### randint(): 
Used to get a random integer within a specified range.

Input: Takes 2 numbers as its input arguments, first input is the start of the range, second is end of the range. 

Return: A random integer within that range. Example, to get a number between 0 and 5, we use randint(0,5)

```python
import random
print random.randint(0,5)

```

#### choice():
Used to select and return a random element from a collection object such as a set, tuple, list, etc. 

Input: Collection object (set, tuple, list, etc.)

Return: A random element from that collection object

```python
import random
a_list = [1,5,False,'thing',2130234,'another thing']
random.choice(a_list)
```

#### shuffle():
Used to randomly shuffle elements in a list, in place.

Input: List data collection

Return: Shuffled version of that list

```python
import random
a_list = ["item1","item2","item3"]
shuffled_list = random.shuffle(a_list)

```


#### randrange():
Used to select a random element given a range of start, stop and optionally a step.

Input: A start (index where to start), stop (index where to stop), optional step (increment by)

Return: A random number from the specified range.

```python
import random
a_list = [0,1,1,2,3,5,8,13,21]
print(random.radrange(0, a_list.length, 2))
```

## Risk Analysis

There are three main steps in the overall risk analysis.

First, is Risk Analysis. 
Risk analysis is the process of identifying and assessing potential risks that could impact a project, business, or organization.

Some of those possible risks are:

1. Use of new hardware
2. Use of new technology
3. Use of new automation tool
4. The sequence of code
5. Availability of test resources for the application

Second is Risk Identification:
Risk identification involves identifying potential threats and vulnerabilities that could lead to negative consequences. These potential threats can be sorted in different sets:

1. Business Risks: Most common risk that usually comes from your company or customer, not the code.

2. Testing Risks: Makes use of software testing tools on the platform being used

3. Premature Release Risk: Risks associated with releases that have not been tested fully

4. Software Risks: Risks that involve the software development process

Third is Risk Assessment:
Risk assessment involves evaluating the likelihood and potential impact of each identified risk. These risks must be approached very carefully and dealt with in a programmatic way. 

There are three perspectives of Risk Assessment:

- Effect – To assess risk by Effect. In case you identify a condition, event or action and try to determine its impact.

- Cause – To assess risk by Cause is opposite of by Effect. Initialize scanning the problem and reach to the point that could be the most probable reason behind that.

- Likelihood – To assess risk by Likelihood is to say that there is a probability that a requirement won’t be satisfied.

How to perform risk analysis:

1. Searching the risk

2. Analyzing the impact of each individual risk

3. Measures for the risk identified

## Things I want to know more about

- I want to know how to use the Random modules on collections other than lists like objects, sets, etc. and when to use them.



>References
>
>[How to Use the Random Module in Python](https://www.pythonforbeginners.com/random/how-to-use-the-random-module-in-python)
>
>[What is Risk Analysis in Software Testing and how to perform it?](https://www.edureka.co/blog/risk-analysis-in-software-testing/)
>