# Control Flow and functions in Javascript

## Class 7 - Programming with Javascript

### Conditionals and loops
When we talk about programming with Javascript and adding logic to our code we first need to talk about the importance of the *control flow*. The usual control flow for code when ran is line to line, top to bottom, unless we run into things that change the control flow like conditionals and loops.

An example of a conditional is a block of code that executes based on a condition being **true** or **false**:
```javascript
let userSaysYes = confirm("Would you like access?");
let userAccess;

if (userSaysYes) {
    userAccess = true;
} else {
 userAccess = false;
}

```
> In this block of code, the user is prompted with a popup confirming if they want access or not. IF they confirm, it will assign `true` to the variable `userSaysYes` and run the first block of code and give access to the user. If they do not confirm, they will not have access

Conditional statements go hand in hand with loops. We can ensure the user gets access by creating a loop around the conditional statement.
```javascript

while (userAccess == false){
    userSaysYes = confirm("Are you sure you don't want access?")
    if(userSaysYes){
        userAccess = true;
    } else {
        userAccess = false;
    }
} 

```
> In this loop, we are continuously asking the user if they want access if they keep on selecting no from our confirm popup. The loop will run while `userAccess = false`

### Functions
If we have want to run this conditional statement that gives users access over and over again for **EVERY** new user that comes gets prompted, we can condense it and run it `while (userAccess == false)` with a function and call it in the loop.
```javascript

let userSaysYes = confirm("Would you like access?");
let userAccess = false;

function userConfirmFunction(usersConfirmation) {
    usersConfirmation = confirm("Are you sure you don't want access?")
    if(usersConfirmation){
        userAccess = true;
    } else {
        userAccess = false;
    }
    return usersConfirmation;
    return userAccess;
}

while (userAccess == false){
   
  userConfirmFunction(userSaysYes);
}



```
In this example, we have condensed all of the `if...else` code into a function and defined it. Then we call(run) that function inside of the while loop. So the confirmation prompt will still continuously pop up if the user says no until they say yes, granting them access


> ### References:
>
>- [MDN Control Flow](https://developer.mozilla.org/en-US/docs/Glossary/Control_flow)
>
>- [Functions](https://www.w3schools.com/js/js_functions.asp)
>
>- [Operators](https://www.w3schools.com/js/js_operators.asp)

## Things I want to know more about
- Using functions to manipulate the HTML webpage
- Using function to manipulate status of data