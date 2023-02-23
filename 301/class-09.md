# Functional Programming

## Functional Programming Concepts


- What is functional programming?

Functional programming is a programming paradigm — a style of building the structure and elements of computer programs — that treats computation as the evaluation of mathematical functions and avoids changing-state and mutable data

- What is a pure function and how do we know if something is a pure function?

It returns the same result if given the same arguments (it is also referred as deterministic) and it does not cause any observable side effects

- What are the benefits of a pure function?

Some of the benefits of a pure function is basically its functionality. It does not rely on outside global objects and the function will produce the same results no matter what arguments are passed into it. Also, when debugging we can look at the outer values for the issues while the function can remain untouched so it is easier to test and debug.

- What is immutability?

Immutability means that somethings state or value cannot be changed after it's created. If you want to change it you just have to create a new value off of the immutable object.

- What is Referential transparency?

It is the combination of a pure function and immutable data. Its basically when a function produces the same results for the same input.

## Modules and require()

- What is a module?

It is code that is split up into different logical 'parts'. Modules have a certain functionality in our application with certain code that logically makes sense for just that module to do. 

- What does the word ‘require’ do?

If we want to use the functionality of a seperate module in a different script file we use a require(). require tells the script that we are need a certain module to run its functionality in a different script. Imagine we have a count.js file with counting functionality. To include it in our app.js it would look like this: 

```javascript
// App.js
let counter = require('./count');

console.log(counter([1,2,3,4]))

// Count.js
let counter = (arr) => `there are ${arr.length} in this array`

module.exports = counter; 

```

- How do we bring another module into the file the we are working in?

To bring in another module into a file we're working in we have to create an expression using require()

```javascript

let moduleFunction = require('./ExternalModule')

```

- What do we have to do to make a module available?

To make the module availble we have to export it from that module

```javascript

module.exports = ThisFunctionalModule;

```

## Things I want to know more about

- Using modules, and how they differ from our current imports in React.

>References
>
>[Functional Programming Concepts](https://medium.com/the-renaissance-developer/concepts-of-functional-programming-in-javascript-6bc84220d2aa)
>
>[Node JS Tutorial For Beginners #6 - Modules and require()](https://www.youtube.com/watch?v=xHLd36QoS4k)
>