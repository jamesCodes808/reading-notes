# Passing Functions as Props

## Lists and Keys

- What does .map() return?

A new array that has been mutated.

- If I want to loop through an array and display each value in JSX, how do I do that in React?

We can use the JS map() function to loop through the array and then out put the items from the array in JSX using the curly braces, {}.

```javascript

const numbers = [1, 2, 3, 4, 5];
const listItems = numbers.map((number) =>
  <li>{number}</li>
);

```

- Each list item needs a unique ____.

Each list item needs a unique key. (A “key” is a special string attribute you need to include when creating lists of elements.)

- What is the purpose of a key?

Keys help React identify which items have changed, are added, or are removed. Keys should be given to the elements inside the array to give the elements a stable identity:

```javascript 

const numbers = [1, 2, 3, 4, 5];
const listItems = numbers.map((number) =>
  <li key={number.toString()}>
    {number}
  </li>
);

```

The best way to pick a key is to use a string that uniquely identifies a list item among its siblings. Most often you would use IDs from your data as keys or use the item index:

```javascript

const todoItems = todos.map((todo) =>
  <li key={todo.id}>
    {todo.text}
  </li>
);


const todoItems = todos.map((todo, index) =>
  // Only do this if items have no stable IDs
  <li key={index}>
    {todo.text}
  </li>
);

```

## The Spread Operator

- What is the spread operator?

In JS the spread operator (...) is spread syntax for expanding an iterable object into the list of arguments. It can spread an array into seperate arguments.

- List 4 things that the spread operator can do.

Copying an array, Concatenating or combining arrays, Using an array as arguments, Adding to state in React

- Give an example of using the spread operator to combine two arrays.

```javascript

const myArray = [`🤪`,`🐻`,`🎌`]
const yourArray = [`🙂`,`🤗`,`🤩`]
const ourArray = [...myArray,...yourArray]
console.log(...ourArray) // 🤪 🐻 🎌 🙂 🤗 🤩

```

- Give an example of using the spread operator to add a new item to an array.

```javascript
const fewFruit = ['🍏','🍊','🍌']
const fewMoreFruit = ['🍉', '🍍', ...fewFruit]
console.log(fewMoreFruit) //  Array(5) [ "🍉", "🍍", "🍏", "🍊", "🍌" ]

```

- Give an example of using the spread operator to combine two objects into one.
 
 ```javascript

const objectOne = {hello: "🤪"}
const objectTwo = {world: "🐻"}
const objectThree = {...objectOne, ...objectTwo, laugh: "😂"}
console.log(objectThree) // Object { hello: "🤪", world: "🐻", laugh: "😂" }
const objectFour = {...objectOne, ...objectTwo, laugh: () => {console.log("😂".repeat(5))}}
objectFour.laugh() // 😂😂😂😂😂

 ```

 ## How to Pass Functions Between Components


- In the video, what is the first step that the developer does to pass functions between components?

The first thing that the developer does is creates a JSX attribute with a name and assigns it to {this.functionName} to reference the method that exists on the component.

- In your own words, what does the increment function do?

It takes in a person, loops through the state's 'people' array using the map function, finds matching name on an object, increments the count in the matching object, creates a new array with the updated count, then uses setState to the new array with the updated count. 

```javascript
increment =(name)=> {
    let ppl = this.state.people.map((p)=> {
        if(p.name === name){
            p.count++;
        }
        return p;
    });
    this.setState({people: ppl});
}

```

- How can you pass a method from a parent component into a child component?

You can pass a method down from a parent component into a child component by creating a JSX element attribute and assigning it to the object prototype method like, 

```javascript
<Child 
name={person.name}
key={person.name}
count={person.count}
functionFromParent={this.increment}
/>

```

- How does the child component invoke a method that was passed to it from a parent component?

By calling the method through props inside of its own prototype method. This will pass the change back up, then back down.

```javascript

functionName = () => {
    this.props.functionFromParent(this.props.name)
}

```

>References
>
>[Lists and Keys](https://reactjs.org/docs/lists-and-keys.html)
>
>[How to Use the Spread Operator (…) in JavaScript](https://medium.com/coding-at-dawn/how-to-use-the-spread-operator-in-javascript-b9e4a8b06fab)
>
>[React - How to Pass Functions between Components - Episode 22](https://www.youtube.com/watch?v=c05OL7XbwXU)

## Things I want to know more about

- Using the spread operator in React to change state.

- Want to get deeper into using and learning about passing methods around components