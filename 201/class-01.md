# How The Web Works

## Class 1 - HTTP, HTML, CSS and JS

### Getting Started

- Compose a short poem describing how HTTP sends data between computers.

>HTTP, you're so good to me<br>
>When i request something<br>
>You send it through my TCP/IP<br>
>Your language is so confusing<br>
>And you work just like a sage<br>
>doing magic in the background<br>
>to give me a nice webpage<br>

- Describe how HTML, CSS, and JS files are “parsed” in the browser.

>The order that the browser parses a webpage is with the HTML file first. As the browser is parsing the HTML file, it will read the metadata in the `<head>` portion of the HTML file and recognize any `<link>` and/or `<script>` elements. 
>
>With this data the browser creates a DOM (Document Object Model) tree from the HTML, CSSOM (CSS Object Model) from the CSS and compiles and executes the JavaScript code.
>
>All of this is combined to instruct the browser how to display the webpage, what the contents are and how it should behave to the user.

- How can you find images to add to a Website?

>There are a couple of different ways to find images to add to a website. 
>
>The most prominent place for any type of image or information is through:<br>
>    https://google.com
>
>Some places that I go to get images that are royalty free are: <br>
>    https://unsplash.com <br>
>    https://blush.design <br>
>    https://storyset.com <br>



- How do you create a String vs a Number in JavaScript?
```javascript
// Creating a string
let age = "50";

//Creating a number
let age = 50;
```
>In this example, the diffrences between creating a string vs creating a number is the parentheses around the data we are assigning to the variable. 
>
>In a String, we use "parentheses" around the 50, making it a string that will display "50"
>
>In a number, we do NOT use parentheses around the `50` making it a number that we can perform mathematical operations on.


- What is a Variable and why are they important in JavaScript?

>When we create variables we are creating and naming containers for data. 
>
>We can store whatever kind of data we need to in these containers and we can manipulate them depending on the type of container it is making it dynamic. 
>
>This is why variables are important.  variables are important to javascript because it allows our programs to be dynamic with data. 


### Introduction to HTML

- What is an HTML attribute?
>There are many things that HTML attributes do, most are unseen unless it is the `style` inline css attribute. In general, HTML attributes have information for the HTML element that they live in. For example:
```HTML
<a href="https://google.com">Google</a>
```
>The href is the attribute, containing information for where the <a> HTML element refers to.

- Describe the Anatomy of an HTMl element.
What is the Difference between `<article>` and `<section>` element tags?

>An HTML element is made up of a start tag, content, and an end tag. The start tag usually looks something like `<article>` or `<section>`, and the end tag is the same as the start tag but with a forward slash before the element name, like `</article>` or `</section>`. The content is the information that appears between the start and end tags.
>
>The `<article>` element is used to represent a self-contained piece of content, such as a blog post or newspaper article. It is meant to stand alone and make sense on its own, even if it is removed from the rest of the page. 
>
>On the other hand, the `<section>` element is used to group together related content on a page, such as chapters of a book or different sections of an article. It is used to divide the page into different sections, but the content within a `<section>` element may not necessarily make sense on its own.
>
For example, if you had a webpage about a recipe and you wanted to include the ingredients and instructions, you might use an `<article>` element for the whole recipe and then use `<section>` elements to divide the recipe into the ingredients and instructions. It would look something like this:
```html
<article>
  <h1>Chocolate Chip Cookies</h1>
  <section>
    <h2>Ingredients</h2>
    <ul>
      <li>1 cup butter</li>
      <li>1 cup sugar</li>
      <li>1 cup brown sugar</li>
      ...
    </ul>
  </section>
  <section>
    <h2>Instructions</h2>
    <ol>
      <li>Preheat your oven to 350°F (180°C).</li>
      <li>Cream together the butter, sugar, and brown sugar.</li>
      <li>Add the eggs and vanilla and mix well.</li>
      ...
    </ol>
  </section>
</article>
```

- What Elements does a “typical” website include?
>A typical website will include several elements such as a header, navigation menu, main content area, and a footer.
>
>The header is usually located at the top of the page and may include a logo or title for the website.
>
>The navigation menu allows users to easily move around the website by providing links to the different pages on the site.
>
>The main content area is where the main information on the webpage is displayed. This could include text, images, and other media.
>
>The footer is usually located at the bottom of the page and may include additional links, copyright information, and other important details.
>
>

- How does metadata influence Search Engine Optimization?
>Metadata is information about a webpage that is not visible to users, but is used by search engines to understand the content of the page. This can include the title of the page, a description of the page's content, and relevant keywords.
>
>When a search engine crawls a webpage, it looks at the metadata to understand what the page is about and how it should be indexed. If the metadata is well-written and includes relevant keywords, it can help the page rank higher in search results for those keywords.


- How is the `<meta>` HTML tag used when specifying metadata?
>The `<meta>` tag is placed in the `<head>` section of an HTML document and can be used to specify various types of metadata, such as the page's description, keywords, author, and other information. For example, you can use the `<meta>` tag to specify a description of the page's content like this:
```html
<meta charset="utf-8" name="description" content="This page is about chocolate chip cookies and includes a recipe and instructions for making them.">

```


### Miscellaneous

#### How to start to design a Website

- What is the first step to designing a Website?
>According to the Mozilla Developer Network, the first step in designing a website is to identify the purpose and goals of the website. This involves understanding the target audience, the type of content that will be presented on the website, and the desired actions that visitors should take when they visit the website. By clearly defining the purpose and goals of the website, you can create a roadmap for the design and development process and ensure that the final product meets the needs of the target audience. This step is important because it helps to establish the direction and focus of the project, and it can save time and resources in the long run by avoiding the need to make major changes later on in the process.

- What is the most important question to answer when designing a Website?
>According to the Mozilla Developer Network, the most important question to answer when designing a website is "What is the purpose of the website?" Identifying the purpose and goals of the website is the first step in the design process and helps to establish the direction and focus of the project. 

#### Semantics

- Why should you use an `<h1>` element over a `<span>` element to display a top level heading?
>According to the Mozilla Developer Network, it is generally recommended to use an `<h1>` element to display a top level heading on a webpage rather than a `<span>` element. This is because the `<h1>` element has semantic meaning and conveys to the browser and search engines that the content contained within it is a top level heading. This can have an impact on the way the content is displayed and how it is interpreted by assistive technologies such as screen readers.

- What are the benefits of using semantic tags in our HTML?
>The benefits of using semantic tags in our HTML is that it gives the HTML elements meaning and purpose in the structure of the webpage. Such as `<header>`, `<section>` and `<footer>`.

#### What is JavaScript?

- Describe 2 things that require JavaScript in the Browser?
>According to the Mozilla Developer Network, JavaScript is a programming language that is commonly used in web development to add interactivity and dynamic behavior to websites. There are many things that require JavaScript in the browser, but some examples include:
>
>Client-side form validation: JavaScript can be used to validate form input on the client-side before the form is submitted. This can help to improve the user experience by providing immediate feedback if there are any errors in the form and can also help to reduce the workload on the server.
>
>Dynamic web pages: JavaScript can be used to create dynamic web pages that can change and update content without needing to refresh the page. For example, you can use JavaScript to display the current time, update a shopping cart, or retrieve data from a server.

- How can you add JavaScript to an HTML document?
>According to the Mozilla Developer Network, there are three ways to add JavaScript to an HTML document:
>
>Inline script: You can add JavaScript directly to an HTML element by using the script attribute. For example:
```javascript
<button onclick="alert('Hello World!')">Click me</button>
```
>
>Internal Script: You can add a script to the `<head>` or `<body>` of an HTML document by using the `<script>` element. For example:
```javascript
<script>
  alert('Hello World!');
</script>
```
>
>External script: You can add a script to an HTML document by linking to an external script file using the `<script>` element and the src attribute. For example:
```javascript
<script src="/path/to/script.js"></script>
```


>References
>
>[Getting started with the web](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web)
>
>[How the web works](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/How_the_Web_works)
>
>[Javascript Basics](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/JavaScript_basics)
>
>[Getting Started with HTML](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/Getting_started)
>
>[Metadata in HTML](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/The_head_metadata_in_HTML)
>
>[How to start to design a website](https://developer.mozilla.org/en-US/docs/Learn/Common_questions/Thinking_before_coding)
>
>[Semantics](https://developer.mozilla.org/en-US/docs/Glossary/Semantics)
>
>[What is JavaScript?](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/First_steps/What_is_JavaScript)

## Things I want to know more about
- Including other libraries into the HTML document
- How to use metadata in a webpage
- Uncommon attributes