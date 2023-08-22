# Function 
function is a block of code that is written for do same task again n again. here we have long description as follows.

- A function is a set of statements that take inputs, do some specific computation, and produce output. The idea is to put some commonly or repeatedly done tasks together and make a function so that instead of writing the same code again and again for different inputs, we can call that function. 
- The `function` keyword is used to define JavaScript Function Definitions.

To create a function in JavaScript, we have to first use the keyword function, separated by the name of the function and parameters within parenthesis. The part of the function inside the curly braces {} is the body of the function.

In javascript, functions can be used in the same way as variables for assignments, or calculations.

Function Definition: Before, using a user-defined function in JavaScript we have to create one. We can use the above syntax to create a function in JavaScript. A function definition is sometimes also termed a function declaration or function statement. Below are the rules for creating a function in JavaScript:

- Every function should begin with the keyword function followed by,
- A user-defined function name that should be unique,
- A list of parameters enclosed within parentheses and separated by commas,
- A list of statements composing the body of the function enclosed within curly braces {}.



There are three ways of writing a function in JavaScript:

**Function Declaration :**  
 It declares a function with a function keyword. The function declaration must have a function name.

 ```js
 function functionName( parameters ) {
    // Statements
}
 ```

 **Function Expression :**  
  It is similar to a function declaration without the function name. Function expressions can be stored in a variable assignment. 
  ```js
  let variableName = functionName( parameter ) {
    // Statements
}; 
  ```

**Arrow Function :**  
   It is one of the most used and efficient methods to create a function in JavaScript because of its comparatively easy implementation. It is a simplified as well as a more compact version of a regular or normal function expression or syntax. 
   
   By implementing the Arrow functions it becomes easier to write function expressions and it also allows a short syntax for writing function expressions and there is no need of the function keyword, the return keyword and the curly brackets.
```js
let function_name = (argument1, argument2 ,..) => {
        // Statements
} 
```


**Function Constructor :**
```js
var FunctionName = new Function("parameter", "return parameter");
var variableName = FunctionName(values); 
```

**Function Parameters :** Till now, we have heard a lot about function parameters but haven’t discussed them in detail. Parameters are additional information passed to a function. For example, in the below example, the task of the function calcAddition is to calculate the addition of two numbers. These two numbers on which we want to perform the addition operation are passed to this function as parameters. The parameters are passed to the function within parentheses after the function name and separated by commas. A function in JavaScript can have any number of parameters and also at the same time, a function in JavaScript can not have a single parameter.

```js
function multiply(a, b) {
    b = typeof b !== "undefined" ? b : 1;
    return a * b;
}
 
console.log(multiply(69)); // 69
```


**Calling Functions :**  
 After defining a function, the next step is to call them to make use of the function. We can call a function by using the function name separated by the value of parameters enclosed between the parenthesis and a semicolon at the end. The below syntax shows how to call functions in JavaScript:

Syntax:
```js
functionName( Value1, Value2, ..);
```

**Return Statement :**  
 There are some situations when we want to return some values from a function after performing some operations. In such cases, we can make use of the return statement in JavaScript. This is an optional statement and most of the time the last statement in a JavaScript function.

Syntax: The most basic syntax for using the return statement is:
```js
return value;
```

The return statement begins with the keyword `return` separated by the value which we want to return from it. We can use an expression also instead of directly returning the value.

Example : 
```js
function calcAddition(number1, number2) {
    return number1 + number2;
}
console.log(calcAddition(6,9));
```

### # Other Definitions :

**Function Hoisting :**  
 It is the mechanism of moving declarations to the top of the current scope. Function declarations are hoisted to the top of the enclosing function and by Function Hoisting we can use the function before its declaration. Functions defined using an expression are not hoisted.

 **Self-Invoking Functions :**  
  A self-invoking functions runs automatically when you create it and self-invoking functions has no name. If the expression is followed by () then Function expressions will execute automatically and you can’t invoke a function declaration.sometimes we call it IIFE (Immediately invoked function expression)

  ```js 
  (function () {
            document.getElementById("name").innerHTML
                = "this is the best way to learn";
        })();
  ```

**Functions are Objects :**  
 It can describe functions as objects and have both properties and methods.

- When define function as property of an object then it is known as method to the object.
- When design a function to create new objects then it is known as object constructor.