# Putting it All Together

## Thinking in React 

- What is the single responsibility principle and how does it apply to components?

It is the principle that a component should ideally only do one thing, as it grows it should be decomposed into smaller subcomponents

- What does it mean to build a ‘static’ version of your application?

It means to build a version of your application that takes the data and renders it but has no interactivity. 

- Once you have a static application, what do you need to add?

Building a static application includes building the components that reuse other components and passes data using props and not using state in this static version. You will need to add a render() method and the data model as a prop.

- What are the three questions you can ask to determine if something is state?

1. Is it passed in from a parent via props? If so, it probably isn’t state.
2. Does it remain unchanged over time? If so, it probably isn’t state.
3. Can you compute it based on any other state or props in your component? If so, it isn’t state.

- How can you identify where state needs to live?

Identify every component that renders something based on that state.
Find a common owner component (a single component above all the components that need the state in the hierarchy).
Either the common owner or another component higher up in the hierarchy should own the state.
If you can’t find a component where it makes sense to own the state, create a new component solely for holding the state and add it somewhere in the hierarchy above the common owner component.

## High Order Functions 


- What is a “higher-order function”?

It is a function that operates on other functions by either taking them as arguments or by returning them. 

- Explore the greaterThan function as defined in the reading. In your own words, what is line 2 of this function doing?

In this line of code, the second line 'return m => m > n' is returning a function that also takes in a parameter and returns a boolean depending on if that parameter is greater than or less than the first function's passed in parameter

```javascript

function greaterThan(n) {
  return m => m > n;
}

```

- Explain how either map or reduce operates, with regards to higher-order functions.

With regards to higher-order functions, map operates by transforming an array by applying a function to all of its elements and building a new array with the returned values. It is a function that takes in a callback function to perform an operation on each element in the array. 

>References
>
>[Thinking in React](https://reactjs.org/docs/thinking-in-react.html)
>
>[Higher-Order Functions](https://eloquentjavascript.net/05_higher_order.html#h_xxCc98lOBK)

## Things I want to know more about

- More about higher order functions and abstraction of returning a function with a function.