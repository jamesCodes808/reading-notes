# Testing and Modules

## Testing
Some important takeaways that I took from TDD is that:

- Test functions should have descriptive names
Names such as: 

```python
def test_should_return_array_reversed_when_given_array():
    test_array = [1,2,3]
    expected_array=reverseArray(test_array)
    assert expected_array == [3,2,1]
```

- Test file names should be the same name as a module's name 
If a module's name is snakes_cafe.py, 
the test file's name should be test_snakes_cafe.py

- AAA (Arrange, Act and Assert)
Arrange: organize the data needed to execute the test code

Act: execute the code thats being tested

Assert: assert the expected return value from test function == what you expected it to be.

## __name__ == "__main__"

- What is it?

```python

if __name__ == "__main__":

```

is also known as a 'main' gate. It is kind of like a boilerplate code that will help a program only invoke code that it intends to. And keeps us from running imported code.

- Why do we need it?

It is best practice to use a main gate when executing code from a file and getting the code that we expected, to run.

### Things I want to know more about

- Are there ever any instances when the 'main' gate has a different name other than main? 

- What exactly is the __name__ variable? 

- How extensive can tests be? 

Ways I can implement TDD to my previous code projects

> References
>
>[In Tests We Trust — TDD with Python](https://code.likeagirl.io/in-tests-we-trust-tdd-with-python-af69f47e6932)
>
>[What does the if __name__ == “__main__”: do?](https://www.geeksforgeeks.org/what-does-the-if-__name__-__main__-do/)