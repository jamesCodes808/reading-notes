# Basics of HTML, CSS and JS

## Class 2 - HTML, CSS & JS

### HTML
- Why is it important to use semantic elements in our HTML?
>It is important to use semantic elements in our HTML because it gives our elements a logical name that can be understood by other developers. Giving an element a name of `<header>` instead of `<div>` lets other devs know that this is a header section where a nav, a brand and maybe a title would go. A `<div>` is not semantic and does not convey the same information as a `<header>` would in the structure of the HTML

- How many levels of headings are there in HTML?
>There are 6 levels of headings in HTML. `<h1>, <h2>, <h3>, <h4>, <h5>, <h6>`

- What are some uses for the `<sup>` and `<sub>` elements?
>The `<sub>` stands for subscript and the `<sup>` stands for superscript. Some uses for the `<sub>` and `<sup>` elements are in marking up dates, chemical formulas and mathematical equations. 
>Example of what it would look like: 
```html
<p>Today is the 10<sup>th</sup> of January 2023.
```

- When using the `<abbr>` element, what attribute must be added to provide the full expansion of the term?
>When you are using the `<abbr>` element, the `title` attribute must be added with the full word that is being abbreviated. Such as:
```html
<p> My address is on 1234 madeup <abbr title="Court">Ct.</abbr>.
```


### Learn CSS
- What are ways we can apply CSS to our HTML?
>We can apply CSS to our HTML using inline styling, inline stylesheets or external stylesheets. 

- Why should we avoid using inline styles?
>We should avoid using inline styles whenever possible because it is the least efficient way to implement CSS and for the sake of maintaining a website. When we have to go back and edit the CSS, with inline styling, we would have to go into each element and edit them. Best practice is to separate the HTML, CSS, and JS files when possible.
- Review the block of code below and answer the following questions:
```css
   h2 {
     color: black;
     padding: 5px;
   }
```
- What is representing the selector?
>the `h2` selector.
- Which components are the CSS declarations?
>the `color` and `padding`
- Which components are considered properties?
>the `black` and the `5px`

### Learn JS
- What data type is a sequence of text enclosed in single quote marks?
>A string

- List 4 types of JavaScript operators.
>Additon `+`, Subtraction `-`, Multiplication `*`, Modulo `%`

- Describe a real world Problem you could solve with a Function.
>You can solve redundant and repetetive code by storing it in a function and calling it whenever it needs to execute.

### Making Decisions in Your Code - Conditionals

- An if statement checks a __ and if it evaluates to ___, then the code block will execute.
>condition, true
- What is the use of an else if?
>to provide more choices if the first if statement is 
- List 3 different types of comparison operators.
>`===` strict equals, `<` less than, `>` greater than
- What is the difference between the logical operator && and ||?
>`&&` is true if both expressions are true, `||` is true if one of the expressions are true

>References
>
>[HTML text fundamentals](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/HTML_text_fundamentals)
>
>[Html Advanced text formatting](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/Advanced_text_formatting)
>
>[How CSS is structured](https://developer.mozilla.org/en-US/docs/Learn/CSS/First_steps/How_CSS_is_structured)
>
>[JavaScript basics](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/JavaScript_basics)
>
>[Making decisions in your code — conditionals](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/conditionals)

## Things I want to know more about