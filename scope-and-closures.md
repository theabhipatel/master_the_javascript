# Scope and Closures

### # Closures :
A closure is a feature of JavaScript that allows inner functions to access the outer scope of a function. Closure helps in binding a function to its outer boundary and is created automatically whenever a function is created. A block is also treated as a scope since ES6. Since JavaScript is event-driven so closures are useful as it helps to maintain the state between events.

**Lexical Scoping :**  
 A function scope’s ability to access variables from the parent scope is known as lexical scope. We refer to the parent function’s lexical binding of the child function as “lexically binding.”

 Let’s see and understand closure through an example. 

 Example : This example shows the basic use of closure.

 ```js
 function foo() {
    let b = 1;
    function inner() {
        return b;
    }
    return inner;
}
let get_func_inner = foo();
 
console.log(get_func_inner());
console.log(get_func_inner());
console.log(get_func_inner());
// output :
// 1
// 1
// 1
 ```

**Output :** We can access the variable b which is defined in the function foo() through function inner() as the later preserves the scope chain of the enclosing function at the time of execution of the enclosing function i.e. the inner function knows the value of b through its scope chain. 
This is closure in action that is inner function can have access to the outer function variables as well as all the global variables.


Definition of Closure: 

    *In programming languages, closures (also lexical closures or function closures) are techniques for implementing lexically scoped name binding in languages with first-class functions. Operationally, a closure is a record storing a function[a] together with an environment:[1] a mapping associating each free variable of the function (variables that are used locally, but defined in an enclosing scope) with the value or reference to which the name was bound when the closure was created.*[b] 
    -Wikipedia

or 

    *In other words, closure is created when a child function keep the environment of the parent scope even after the parent function has already executed* 


- Closure is the concept of function + lexical environment in which function it was created. so every function declared within another function then it has access to the scope chain of the outer function and the variables created within the scope of the outer function will not get destroyed.

Now let’s look at another example. 

Example 2: This example shows the basic use of closure.
```js
function foo(outer_arg) {
 
    function inner(inner_arg) {
        return outer_arg + inner_arg;
    }
    return inner;
}
let get_func_inner = foo(5);
 
console.log(get_func_inner(4));
console.log(get_func_inner(3));

// out put :
//9
// 8
```

Output: In the above example we used a parameter function rather than a default one. Not even when we are done with the execution of foo(5) we can access the outer_arg variable from the inner function. And on the execution of the inner function produce the summation of outer_arg and inner_arg as desired. 


Now let’s see an example of closure within a loop. 
In this example, we would store an anonymous function at every index of an array. 

Example 3: This example shows the basic use of closure.
```js
// Outer function
function outer() {
    let arr = [];
    let i;
    for (i = 0; i < 4; i++) {
        // storing anonymous function
        arr[i] = function () { return i; }
    }
 
    // returning the array.
    return arr;
}
 
let get_arr = outer();
 
console.log(get_arr[0]());
console.log(get_arr[1]());
console.log(get_arr[2]());
console.log(get_arr[3]());

// output :
// 4
// 4
// 4
// 4
```

Output: Did you guess the right answer? In the above code, we have created four closures that point to the variable i which is the local variable to the function outer. Closure doesn’t remember the value of the variable it only points to the variable or stores the reference of the variable and hence, returns the current value. In the above code when we try to update the value it gets reflected all because the closure stores the reference. 


Let’s see the correct way to write the above code so as to get different values of i at different indexes. 

Example 4: This example shows the basic use of closure

```js
// Outer function
function outer() {
    function create_Closure(val) {
        return function () {
            return val;
        }
    }
    let arr = [];
    let i;
    for (i = 0; i < 4; i++) {
        arr[i] = create_Closure(i);
    }
    return arr;
}
let get_arr = outer();
console.log(get_arr[0]());
console.log(get_arr[1]());
console.log(get_arr[2]());
console.log(get_arr[3]());

// output :
// 0
// 1
// 2
// 3
```

Output: In the above code we are updating the argument of the function create_Closure with every call. Hence, we get different values of i at different indexes.


### # scope :

In JavaScript, there are two types of variable scopes:

**1. Global Scope :**  
 Variables declared Globally (outside of any function) have Global Scope and Global variables can be accessed from anywhere in a program. Similar to function scope variables declared with var, let and const are quite similar when declared outside a block.Scope outside the outermost function attached to the window.
**2. Local Scope :**  
 Variables declared inside a function become local to the function. Local variables are created when a function starts and deleted when the function is executed. Local variables have Function Scope which means that they can only be accessed from within the function. Inside the function being executed. 


- After ES2015, we started using let instead of var for declaring variables, and also now the if block is also counted as a block scope, 

Below examples illustrate the JavaScript Variable Scope:

Example 1: We have a global variable defined in the first line in the global scope. Then we have a local variable defined inside the function fun(). 

```js
 let globalLet = "This is a global variable";
 
    function fun() {
      let localLet = "This is a local variable";
 
      console.log(globalLet); // This is a global variable
      console.log(localLet);   // This is a local variable
    }
    fun();
```
   
Output: When we execute the function fun(), the output shows that both global, as well as local variables, are accessible inside the function as we are able to console.log them. This shows that inside the function we have access to both global variables (declared outside the function) and local variables (declared inside the function). 