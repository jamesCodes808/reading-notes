# Welcome to 401

## Pain Vs. Suffering


- What’s your perspective?

My perspective of the pain that goes into mentally and physically pushing yourself to learn, absorb, progress and build a solid foundation in a fast paced learning and working environment is that sometimes it is necessary. I have gone through a lot of pain in mostly all of my positions. I seldom held a job where I wasn't being challenged to grow or endure some type of pain for progress.

- Why are you doing this?

I am doing this because of my personality type and ambition. I cannot have a job that is unfulfilling and not challenging me to learn and grow. I also am doing this to achieve my dream job and obtain a better life and environment for me and my daughter.

- Do you want what comes at the end of this journey?

I want what comes at the end of this journey and will continue to keep striving to obtain what comes after the end of the journey.

- Are you doing this for you?

I am doing this mainly for myself but also for my daughter. 


## Basics of Big O 

- What is it?

Big O notation is used in computer science to describe the complexity or performance of an algorithm. Such as its execution time required, space used and describes the worst-case scenario.

- Different Levels of Big O Notation

O(1) - an algorithm that will always have the same execution time regardless of input data set size.

```java

bool IsFirstElementNull(IList<String> elements)
{
    return elements[0] == null;
}

```

<br>

O(N) - an algorithm with performance that grows in a linear fashion directly proportionate to the input data set size. 

```java

bool ContainsValue(IEnumerable<string> elements, string value)
{
    foreach (var element in elements)
    {
        if (element == value) return true; 
    }     
    return false; 
}

```

O(N^2) - an algorithm with performance that is directly proportionate to the size of the input data set size squared. When there are deeper nested iterations (for loops, conditional statements) the algorithm big O notation results in O(N^3), O(N^4) and so on...

```java

bool ContainsDuplicates(IList<string> elements)
{
    for (var outer = 0; outer < elements.Count; outer++) 
    {
        for (var inner = 0; inner < elements.Count; inner++) 
        { 
            // Don't compare with self 
            if (outer == inner) continue;             
            
            if (elements[outer] == elements[inner]) return true; 
        }
    }    
    return false;
}

```

O(2^N) - an algorithm that doubles in growth for each addition to the input data set size. An example is the calculation of Fibonacci number.

```java 

int Fibonacci(int number)
{
    if (number <= 1) return number;
       
    return Fibonacci(number - 2) + Fibonacci(number - 1); 
}

```


## Things I want to know more about

- A deeper understanding of Big O and algorithms. I definitely want to at least be comfortable enough to reference it by memory

> References
>
>[Pain vs. Suffering](https://codefellows.github.io/code-401-python-guide/curriculum/class-01/notes/pain_suffering)
>
>[Beginner's guide to Big O](https://robbell.io/2009/06/a-beginners-guide-to-big-o-notation)