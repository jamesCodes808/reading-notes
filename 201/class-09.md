# Forms And JS Events

## HTML Forms

- Why are forms so important in web development?

Forms are important in web development because, for the front-end, it provides the web page a way to interact and get data from the user.

- When designing a form, what are some key things to keep in mind when it comes to user experience?

Some key things to keep in mind when designing a form is the key information you need from the user, the simplicity of the form, and its focus.

- List 5 form elements and explain their importance.

```html
<!-- This container tag will define the form -->
<form action="/form-submission-page" method="post"> 
<!-- The attributes action and method should always be set in a form  -->

    <!-- the label tag creates a label for its corresponding data input tag (with matching id's)-->
    <label for="name">Name:</label> 
 
    <input type="text" id="name" name="user_name" />
    <!-- The input tag will be the point of data entry for your form-->

    <!-- the fieldset tag is a convenient element used to group together widgets/inputs that share the same purpose, -->
    <fieldset>
        <legend>Favorite Color</legend>
        <!-- The legend is like a label for the fieldset -->
        
        <label for="color_red">Red</label>
        <input type="radio" name="color" id="color_red" value="red">
        
        <label for="color_blue">Blue</label>
        <input type="radio" name="color" id="color_blue" value="blue">
    </fieldset>


    <button type="submit">Submit message</button>
    <!-- The button element will submit the data once the form is filled out -->
</form>
```

## JS Events

- How would you describe events to a non-technical friend?

The way I would describe events to a non-technical friend would be really simple and high level. I would explain to them, that when they click their mouse, scroll their wheel, or even move their mouse into a certain area of a webpage, that is an event in programming.

- When using the addEventListener() method, what 2 arguments will you need to provide?

You will need to provide the name of the event and a function to handle the event.

```javascript

document.body.addEventListener('click', fireClickFunction)

```

- Describe the event object. Why is the target within the event object useful?

The target property of the event object is useful because it is a reference to the element that the event is occurring on.

- What is the difference between event bubbling and event capturing?

Event bubbling and capturing are outdated and have been combined but.

The difference between event bubbling and event capturing is:

With event bubbling, when we assign the same event handlers to an element, and its parents, the event fires on the child element first then bubbles up to its parents.

With event capturing, the reverse happens, the event fires on the parents first then goes down to its child.


>References
>
>[Web Forms - Working with user data](https://developer.mozilla.org/en-US/docs/Learn/Forms)
>
>[Your first form](https://developer.mozilla.org/en-US/docs/Learn/Forms/Your_first_form)
>
>[How to structure a webform](https://developer.mozilla.org/en-US/docs/Learn/Forms/How_to_structure_a_web_form)
>
>[Introduction to events](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Events)

### Things I want to know more about
- When would we use event bubbling and capturing?
- What kind of events can we capture with event listeners?