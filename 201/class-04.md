# HTML Links, JS Functions, and Intro to CSS Layout

## Class 4

### HTML: Hyperlinks
- To create a basic link, we wrap text or other content inside what element?
To create a link we wrap the text or other content that link to a website in an anchor tag. The anchor tag looks like this `<a>` and we use an `href` attribute. For Example:

```html
<a href="https://google.com">Clicking this will go to Google.com</a>
```

- The href attribute contains what information?
The `href` attribute contains the address of the website we are directing the user to through an anchor tag. It stands for `hyper text reference`.

- What are some ways we can ensure links on our pages are accessible to all readers?
One of the ways we can ensure that links are accessible to all readers is by using the attribute `title`. Another way is to wrap the `anchor` tags around meaningful content or text, such as "home", "FAQ", "Contact" or "Click me to go here".

### CSS: Layout, Positioning
- What is meant by “normal flow”?
"Normal Flow" means the default way that elements are laid out or positioned on a webpage when none of their properties are changed with styling.

- What are a few differences between block-level and inline elements?
`block-level` and `inline` are the default display properties of elements. The difference between `block-level` and `inline` elements are that `block-level` elements take up the entire `inline` space while `inline` elements are elements that display "inline" with other elements. One example is that `block-level` elements begin on a new line, or take up an entire line while `inline` elements do not and just fit in with the document flow. 

- ___ positioning is the default for every html element.
`Static`

- Name a few advantages to using absolute positioning on an element.
Some advantages of using `absolute` positioning on an elements are:<br>
Removing it from the normal document flow.<br>
You can create isolated UI features that don't interfere with the layout of other elements.<br>
Pop-up information boxes, control menus, rollover panels, drag and drop UI can be created.<br>

- What is a key difference between fixed positioning and absolute positioning?
Some of the key differences between `fixed` and `absolute` positioning are absolute positioning fixes an element in place relative to its nearest positioned ancestor (the initial containing block if there isn't one), fixed positioning usually fixes an element in place relative to the visible portion of the viewport, unless one of the element's ancestors is a fixed containing block because its transform property has a value other than none.)

### JS: Functions
- Describe the difference between a function declaration and a function invocation.
Function declaration is used when you are declaring a function name and what that function will do.

```javascript
function myFunction(){
    console.log('i'm a function')
}
```

Function invocation is used when you are trying to invoke or call a function to execute.

```javascript
myFunction();
```

- What is the difference between a parameter and an argument?
From what I understand they are used interchangeably, but parameters are mostly used during the declaration of a function, to state what variables will be needed for the function to execute and arguments are mostly used when we describe what actual variables we are passing into a function.

### Misc: Pair Programming
- Pick 2 benefits to pair programming and reflect on how these benefits could help you on your coding journey.
In my experience, I benefit from pair programming because it helps me learn from others while learning about myself, when I share knowledge. Being able to bounce ideas around with a fellow programmer definitely helps in that process. Another benefit from pair programming that I benefit from is the use of language and environment. I am able to expand my technical vocabulary and actually articulate what my code is doing to fellow programmers who would understand the terminology.

>References
>
>[Creating hyperlinks](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/Creating_hyperlinks)
>
>[Positioning](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Positioning)
>
>[Normal Flow](https://developer.mozilla.org/en-US/docs/Learn/CSS/CSS_layout/Normal_Flow)
>
>[Functions — reusable blocks of code](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Functions)
>
>[6 Reasons for Pair Programming](https://www.codefellows.org/blog/6-reasons-for-pair-programming/)


### Things I want to know more about
- Using functions and loops together
- More about CSS positioning
- Best practices when pair programming