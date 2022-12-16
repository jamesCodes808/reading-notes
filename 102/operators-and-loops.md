# Operators and Looping your code

## Class 8 - Operators and Loops

### Expressions are joined by operators

Expressions are units of code used to resolve a value just like in algebra.
`1 + 1 = 2`

In coding, expressions such use *operators* such as the `=` sign to assign values to variables:
`x = 100`. 
In this example, the variable `x` is equal to `100`.

In basic expressions, the order of precedence rule **(PEMDAS)** applies to the operators when evaluating:
```
P arentheses
E xponents
M inus
D ivision
A ddition
S ubtraction
```

### Operators
Javascript has many different types of operators. Some of the most used are:
```javascript
//Assignment Operators
x = y   
x += y //equal to x = x + y
x -= y //equal to x = x - y

//Comparison Operators
==      //Equals
!=    //Not Equal
===  //Strict Equal
>   //Greater than
<=  //Less than or equal 

//Arithmetic Operators
%   //Remainder (modulo) 12%5 returns 2
++  //Increment by 1  (5++ returns 6)
--  //Decrement by 1  (5-- returns 4)
**  //Exponentation (2 ** 3 returns 8)

//Logical Operators
&&  //logical AND (expr1 && expr2, both have to be TRUE to return TRUE else FALSE)

||  //logical OR (expr1 || expr2, one expression has to be TRUE to return     TRUE else FALSE)

!   //logical NOT (!expr, returns FALSE if expr is TRUE, else TRUE)
```

### Loops and Iterations
Loops are an easy way to repeat a block of code based on a conditional or iterable statement. Here are a couple basic loops

#### For loops
`for` loops repeat until the condition specified evaluates to false. Basic syntax:
```javascript
for(initialExpression; conditionalExpression; incrementExpression){
    execute this code while conditionalExpression is true
}

//example, this will console log 5 times
for(let i = 0; i < 5; i++){
    console.log(i)
}
```

#### While Loops
`while` loops execute as long as the condition is true. Basic Syntax:
```javascript
while(condition){
    execute this code while condition is true
}

//example, this is an infinite loop and will log 'error' forever
while(true){
    console.log('error')
}
```

There are many ways to combine operators and loops and many use cases for loops in creating web pages, applications and even games.

> ### References:
>
>- [Expressions and Operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators)
>
>- [Loops](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Loops_and_iteration)
>

## Things I want to know more about
- nesting loops
