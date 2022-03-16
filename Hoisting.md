## Let's understanding Hoisting in JS
##### Hoisting is a technique in JS, where we can access the function and variable before initializing or declaring it without any error (unlike other programming language).
[Main benefit of hoisting is that it lets you use a function before you declare it in your code](https://developer.mozilla.org/en-US/docs/Glossary/Hoisting)

Ex:1
```
getName();          //func hoisted
console.log(x);     //variable hoisted

var x = 5;          //variable declared and initialized

function getName(){                     //func getName declared
    console.log("CoolJavaScript");
}

//output:
//CoolJavaScript
//undefined
```
- From the above example, we invoke a function and print variable `x` before declaration/initialization. 
- As hoisting work different for function and variable, so function `getName` runs and returns.
- In variable case, JS only hoists declarations, not initializations. This means that initialization doesn't happen until the associated line of code is executed.
- Finally `Hoisting` is there on the top of execution contexts (i.e. creation and execution phases) in JavaScript. 
