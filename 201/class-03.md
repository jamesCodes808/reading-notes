# HTML Lists, Control Flow with JS, and the CSS Box Model

## Class 3

### HTML 
- When should you use an unordered list in your HTML document?
>You should use unordered lists in an HTML document when you are listing a group of items that have no numerical order. Some examples of good unordered list item groups are links, navigation group, or a
>

- How do you change the bullet style of unordered list items?
>To change the bullet style of unordered list items you have to use the CSS `list-style-type` property on the `<ul>`
>

- When should you use an ordered list vs an unordered list in your HTML document?
>You should use an ordered list when there is no numerical order in the list items. When there needs to be a numbered order in the items you are listing such as steps for instructions, numbered directions or a list of hierarchal items.
>

- Describe two ways you can change the numbers on list items provided by an ordered list?
>the `<ol>` element accepts certain attributes. Some of these attributes include:
`reversed`, `start`, and `type`. To change the numbers on the list items you could use:

```
<ol type="a"> sets numbering type to lowercase letters
<ol type="1"> sets numbering type to numbers (default)
<ol type="I"> sets numbering type to uppercase Roman numerals
```


### CSS
- Describe the CSS properties of margin and padding as characters in a story. What is their role in a story titled: “The Box Model”?
>In the story of "The Box Model," There was a main character named element who wore a border armor because he needed to be protected. Margin and Padding were two friends of element who had very different roles. Margin was able to manipulate the amount of space outside of element's border armor, while Padding was able to manipulate the amount of space inside of element's border armor, closer to the element's content.
>
>Margin was loud and liked to keep things separate, often creating space between element from others of his kind to prevent them from crowding each other. Padding, on the other hand, was more introverted and enjoyed staying close to the element and its pet content, making sure that they were cushioned and protected.
>
>Together, Margin and Padding were integral to element. Without Margin and Padding, the element would be cramped against others and be uninviting, but with their help, they would create a  Box Model that was beautiful, cohesive and organized.
>
- List and describe the four parts of an HTML elements box as referred to by the box model.
>In order of outermost part: margin, border, padding, content
>

### JS

- What data types can you store inside of an Array?
>Arrays are able to hold strings, numbers, objects, and other arrays.
>

- Is the people array a valid JavaScript array? If so, how can I access the values stored? If not, why?

```javascript
 const people = [['pete', 32, 'librarian', null], ['Smith', 40, 'accountant', 'fishing:hiking:rock_climbing'], ['bill', null, 'artist', null]];
```

>Yes this is a valid javascript array. In order to access the values stored inside we would have to use the angle brackets with an index number such as:
`people[0]` which would retrieve `["pete",32,"librarian",null]` from the array. To acces the items inside of that index we would use: 
`people[0][0]` which would give us 'pete'.
>

- List five shorthand operators for assignment in javascript and describe what they do.

```javascript
= //assignment operator, assigns data to a variable
+= //addition assignment, shorthand for x = x + y
-= //subtraction assignment, shorthand for x = x - y
*= //multiplication assignment, shorthand for x = x * y
/= //division assignment, shorthand for x = x / y
```


- Read the code below and evaluate the last expression and explain what the result would be and why.

```javascript
 let a = 10;
 let b = 'dog';
 let c = false;

 // evaluate this
 (a + c) + b;
```
>
>

- Describe a real world example of when a conditional statement should be used in a JavaScript program.
>One real work example I can think of that would make good use of a conditional statements is any type of login page. We can use conditional statements to create an if statement that lets a user log in IF the password entered is correct, else, they do not get access.
>

- Give an example of when a Loop is useful in JavaScript.
>A loop would be useful if  you want to repeat code a certain amount of times, or if you just want to repeat code in general. One example would be to get through an array. We can create an array and a for loop. We would use the `i` in the first expression to index through an array, looking something like this

```javascript
let arrayOfNumbers = [0,1,2,3,4,5,6]

for(let i=0; i < arrayOfNumbers.length; i++){
    console.log(arrayOfNumbers[i])
}

```


>References
>
>[<ul>: The Unordered List element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ul)
>
>[<ol>: The Ordered List element](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ol)
>
>[The box model](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/The_box_model)
>
>[Arrays](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/First_steps/Arrays)
>
>[Expressions and operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators)
>
>[Making decisions in your code — conditionals](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/conditionals)
>
>[Looping code](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Looping_code)

## Things I want to know more about
- Using the position property with the box model correctly
- Array methods
- Using loops in a more advance, real-world way