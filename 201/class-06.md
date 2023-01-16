# Problem Domain, Objects and the DOM

## Class 6

### JS: Object Basics
- How would you describe an object to a non-technical friend you grew up with?
One way to think of an object in a non-technical sense is like the brain of a robot. In that brain, you have a collection of actions it can perform (called methods) and that brain can also hold data or value pairs (also known as variables or properties). With this brain object, you can give the robot commands and it will understand what the commands mean based on what you defined them as. An example would be:

```javascript
const roboBrain = {
    name: "RoboBoy v.1",
    introduceSelf: function() {
        alert(`hello, I am ${this.name}, how are you today?`);
    },
    giveSum: function(a,b) {
        return [(a+b), `the sum of the numbers ${a} and ${b} are ${(a+b)}`]
    }
}

roboBrain.introduceSelf();
roboBrain.giveSum(10,59);

```

- What are some advantages to creating object literals?
Some advantages of using object literals is that an object can hold just about any type of data, or data structure such as strings, numbers, functions, arrays and even other objects. And calling the methods or variables in the object is as simple as using the dot or bracket notation such as `object.callFunction()` or `object.firstVariable`.

- How do objects differ from arrays?
Arrays are used more for a list of data in a single variable while objects can be used more for an entire thing with different properties and functions(methods) inside of it.

- Give an example for when you would need to use bracket notation to access an object’s property instead of dot notation.
If an object property name is held in a variable, then you can't use dot notation to access the value, but you can access the value using bracket notation. Such as if you are using a function argument. 

```javascript
const roboBrain = {
    name: ['robo','boy'],
    version: 1
}

function getRoboProperty(propertyName){
    console.log(roboBrain[propertyName])
}

getRoboProperty("name");
//['robo','boy']

getRoboProperty('version');
// 1

```

- Evaluate the code below. What does the term this refer to and what is the advantage to using this?

```javascript

const dog = {
  name: 'Spot',
  age: 2,
  color: 'white with black spots',
  humanAge: function (){
    console.log(`${this.name} is ${this.age*7} in human years`);
  }
}

```

The term `this` refers to the current object that the code is being written inside of. In the above example, `this` refers to the `const dog` object and its `name` variable. The advantage to using the keyword `this` is it provides us an easy way to create multiple object literals, instead of writing `dog.name` we can just use `this.name` and it will refer to whatever object we're creating.

### HTML, JS: The DOM
- What is the DOM?
The DOM stands for Document Object Model. It represents the entire webpage and its structure in way that programs can understand and manipulate it. Each HTML element, class, id and content of the webpage is represented in the DOM as nodes and objects so programming languages can interact and manipulate them.

- Briefly describe the relationship between the DOM and JavaScript.
Javascript has access to the DOM through its elements being seen as objects and nodes. Without the DOM, javascript would not have any way to access a webpage's elements and manipulate them. 


>References
>
>[Javascript Object Basics](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Basics)
>
>[Introduction to the DOM](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model/Introduction)

### Things I want to learn more about
- DOM manipulation through javascript
- Using functions to create object literals