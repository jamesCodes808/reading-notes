# Object-Oriented Programming, HTML Tables

## Class 7

### Domain Modeling

- Explain why we need domain modeling.

Good domain modeling helps us communicate the specific problem amongst stakeholders and allows us to be able to model and build scalable code that can be explained technically and in layman's terms.

### HTML: Tables

- Why should tables not be used for page layouts?

Tables layouts reduce accessibility for visually impaired users, the structure of a table is very complex markup wise and can make code harder to debug and tables widths and sizes are dependent on the content inside making them hard to style.

- List and describe 3 different semantic HTML elements used in an HTML `<table>`.

Creating a table includes the following `HTML` elements:

```html
<table>
    <tr>
        <td></td>
    </tr>
</table>

```

### JS: Intro to Constructors

- What is a constructor and what are some advantages to using it?

A constructor is basically just a function being called using the `new` keyword to create a new object, bind `this` to the new object, so `this` can be used in te constructor, run code in the constructor and return a new object. The advantage to using constructors is a faster a shorter way to create many objects with similar properties, and using the keyword `this` instead of creating a new object inside of the constructor function.

- How does the term this differ when used in an object literal versus when used in a constructor?

In a constructor, the `this` keyword binds itself to a property that is being declared, in an object literal, we are referring to something that is currently in the object.

### JS: Object Prototypes

- Explain prototypes and inheritance via an analogy from your previous work experience. NOTE: This is a very common front end developer interview question

Inheritance is when we use the `Object.create(anotherObject)` method for an object using another object. We can change the properties that we need to change using the created object and it will inherit properties we didn't declare from `anotherObject`. The same goes for prototypes, we can create different object methods using `Object.prototype.functionName` and it will be shared with all `Object` that is created. 

An analogy of this from my previous job is when a new person onboards into our team, they are given the default priviliges, and inherit default restrictions, once they are fully onboarded into the system and into a specific team, they will also gain the shared priviliges(just like methods) once their account is fully created/onboarded.

>References
>
>[Domain Modeling](https://github.com/codefellows/domain_modeling#domain-modeling)
>
>[HTML Table Basics](https://developer.mozilla.org/en-US/docs/Learn/HTML/Tables/Basics)
>
>[Javascript Object Basics](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Objects/Basics#introducing_constructors)
>
>[A Beginner's Guide to Javascript's Prototype](https://ui.dev/beginners-guide-to-javascript-prototype)

### Things I want to know more about
- I definitely want to know more about prototypes and inheritance
- javascript classes and arrow functions