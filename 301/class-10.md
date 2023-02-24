# In memory storage

## Understanding the Javascript Call Stack


- What is a ‘call’?

A 'call' is essentially the invocation of a function execution.

- How many ‘calls’ can happen at once?

'Calls' can happen one at a time, from top to bottom, making it synchronous.

- What does LIFO mean?

Last in First out. 

This means that the last function that gets pushed into the stack is the first to be popped out, when the function returns.

- Draw an example of a call stack and the functions that would need to be invoked to generate that call stack.

```javascript 
const function1 = () => {
    console.log('im f1')
}

const function2 = () -> {
    function1();
    console.log('im f2')
}

```

- What causes a Stack Overflow?

A stack overflow occurs when there is a recursive function (a function that calls itself) without an exit point. The browser (hosting environment) has a maximum stack call that it can accomodate before throwing a stack error.

## Javascript error messages


- What is a ‘reference error’?

This is as simple as when you try to use a variable that is not yet declared you get this type os errors. 

- What is a ‘syntax error’?

This occurs when you have something that cannot be parsed in terms of syntax, like when you try to parse an invalid object using JSON.parse.

- What is a ‘range error’?

This error happens when we try to manipulate an object with some kind of length and give it an invalid length.

- What is a ‘type error’?

This type of errors shows up when the types (number, string and so on) you are trying to use or access are incompatible, like accessing a property in an undefined type of variable.

- What is a breakpoint?

It is a point in your code that you can set where you can see what happened in the code before that point.

- What does the word ‘debugger’ do in your code?

It can be used to set a break point in your code in the line that you put the keyword 'debugger'

## Things I want to know more about

- Using debugger more efficiently

- Understanding the call stack more and how to rememdy stack overflow errors

>References
>
>[The JavaScript Call Stack - What It Is and Why It's Necessary](https://www.freecodecamp.org/news/understanding-the-javascript-call-stack-861e41ae61d4)
>
>[JavaScript error messages && debugging](https://codeburst.io/javascript-error-messages-debugging-d23f84f0ae7c)
>
>