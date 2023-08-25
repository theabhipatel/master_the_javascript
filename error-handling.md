# Error Handling 

### # Error :
An error is an action that is inaccurate or incorrect. There are three types of errors in programming which are discussed below:

- Syntax error
- Logical error
- Runtime error

**Syntax error :**  
 According to computer science, a syntax error is an error in the syntax of a sequence of characters or tokens that is intended to be written in a particular programming language or it is also a compile-time error if the syntax is not correct then it will give an error message. 

**Logical error :**  
 It is the most difficult error to be traced as it is the error on the logical part of the coding or logical error is a bug in a program that causes it to operate incorrectly and terminate abnormally (or crash). 

**Runtime Error :**  
 A runtime error is an error that occurs during the running of the program, also known as the exception. In the example that is given below the syntax is correct, but at runtime, it is trying to call a method that does not exist. 


 ### # Error handling :

 When executing JavaScript code, errors will most definitely occur. These errors can occur due to a fault from the programmer’s side or the input is wrong or even if there is a problem with the logic of the program. But all errors can be solved and to do so we use five statements that will now be explained.

- The try statement lets you test a block of code to check for errors.
- The catch statement lets you handle the error if any are present.
- The throw statement lets you make your own errors.
- The finally statement lets you execute code after try and catch.  
- The finally block runs regardless of the result of the try-catch block.


**Try and Catch Block :**  
 The try statement allows you to check whether a specific block of code contains an error or not. The catch statement allows you to display the error if any are found in the try block.

```js
try {
     Try Block to check for errors.
}
catch(err) {
      Catch Block to display errors.
}
```

JavaScript uses the try catch and finally to handle the exception and it also uses the throw operator to handle the exception. try have the main code to run and in the catch block if any error is thrown by try block will be caught and the catch block will execute. Finally block will always occur even if an error is thrown


**Javascript Throws Block The throw Statement :**   
When any error occurs, JavaScript will stop and generate an error message. The throw statement lets you create your own custom error. Technically you can throw your custom exception (throw an error). The exception can be a JavaScript Number, String, Boolean, or Object. By using throw together with try and catch, you can easily control the program flow and generate custom error messages. 

Example: In this example, we will see how a throw statement is used to throw an error in javascript.

```js
try {
    throw new Error('Yeah... Sorry');
}
catch (e) {
    console.log(e);
}
```

**The finally Block :**  
 The finally Statement runs unconditionally after the execution of the try/catch block. Its syntax is

```js
try {
     Try Block to check for errors.
}
catch(err) {
      Catch Block to display errors.
} 
finally {
      Finally Block executes regardless of the try / catch result.
}
```

Example: In this example, we will learn about the final statement of Javascript.
```js
try {
    console.log('try');
} catch (e) {
    console.log('catch');
} finally {
    console.log('finally');
}

// output :
// try
// finally
```
