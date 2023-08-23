# Asynchronous and Synchronous JavaScript


### # Synchronous JavaScript : 
As the name suggests synchronous means to be in a sequence, i.e. every statement of the code gets executed one by one. So, basically a statement has to wait for the earlier statement to get executed.
Let us understand this with the help of an example.

Example:
```js
    console.log("Hi"); // First
  
    console.log("Mayukh") ;// Second
      
    console.log("How are you"); // Third
```

In the above code snippet, the first line of the code Hi will be logged first then the second line Mayukh will be logged and then after its completion, the third line would be logged How are you.
So as we can see the codes work in a sequence. Every line of code waits for its previous one to get executed first and then it gets executed.



### # Asynchronous JavaScript :
 Asynchronous code allows the program to be executed immediately where the synchronous code will block further execution of the remaining code until it finishes the current one. This may not look like a big problem but when you see it in a bigger picture you realize that it may lead to delaying the User Interface.

Let us see the example how Asynchronous JavaScript runs.

Example:
```js
    console.log("Hi"); // First
  
    setTimeout(() => {
        console.log("Let us see what happens"); // Third
    }, 2000);
      
    console.log("How are you"); // second
```

So, what the code does is first it logs in Hi then rather than executing the setTimeout function it logs in End and then it runs the setTimeout function.

At first, as usual, the Hi statement got logged in. As we use browsers to run JavaScript, there are the web APIs that handle these things for users. So, what JavaScript does is, it passes the setTimeout function in such web API and then we keep on running our code as usual. So it does not block the rest of the code from executing and after all the code its execution, it gets pushed to the call stack and then finally gets executed. This is what happens in asynchronous JavaScript.

---

**Asynchronous programming** is a technique that enables your program to start a potentially long-running task and still be able to be responsive to other events while that task runs, rather than having to wait until that task has finished. Once that task has finished, your program is presented with the result.

Many functions provided by browsers, especially the most interesting ones, can potentially take a long time, and therefore, are asynchronous. For example:

- Making HTTP requests using fetch()
- Accessing a user's camera or microphone using getUserMedia()
- Asking a user to select files using showOpenFilePicker()

So even though you may not have to implement your own asynchronous functions very often, you are very likely to need to use them correctly.



### # Callback :
An event handler is a particular type of callback. A callback is just a function that's passed into another function, with the expectation that the callback will be called at the appropriate time. As we just saw, callbacks used to be the main way asynchronous functions were implemented in JavaScript.

#### What are Callbacks?

A callback is a function that is passed as an argument to another function, and is called after the main function has finished its execution. The main function is called with a callback function as its argument, and when the main function is finished, it calls the callback function to provide a result. Callbacks allow you to handle the results of an asynchronous operation in a non-blocking manner, which means that the program can continue to run while the operation is being executed.

#### Why use Callbacks?

Callbacks are used to handle the results of asynchronous operations in a non-blocking manner. Asynchronous operations are operations that take a significant amount of time to complete, such as network requests, file I/O, and database queries. If these operations were executed synchronously, the program would freeze and wait for the operation to complete before continuing. This can lead to a poor user experience, as the program would appear unresponsive.

Callbacks allow you to continue executing code while the operation is being executed in the background. Once the operation has completed, the callback function is called with the result of the operation. This way, you can ensure that the program remains responsive and the user experience is not impacted.

**> Concepts :**

**Asynchronous programming :** Callbacks are used to handle the results of asynchronous operations, which means that the operation does not block the execution of the rest of the program. Instead, the program continues to run and the callback function is executed when the operation is complete.

**Non-blocking :** Callbacks allow for non-blocking programming, which means that the program does not stop and wait for an operation to complete before continuing to execute. This is important for improving the performance and responsiveness of applications.

**Higher-order functions :** A higher-order function is a function that takes one or more functions as arguments, or returns a function as a result. The mainFunction in the examples above is a higher-order function because it takes a callback function as an argument.

**Anonymous functions :** Anonymous functions are functions that are not named and are often used as callbacks. The function passed to setTimeout in the first code example is an anonymous function.

**Closure :** A closure is a function that has access to variables in its outer scope, even after the outer function has returned. This allows the callback function to access variables and information from the main function, even after the main function has completed its execution.

understanding these concepts is essential for effectively using callbacks in JavaScript programming

**Real-Life Examples :**

- Loading images on a website: When you load a website, images can take a while to load, especially if they’re large. If images were loaded synchronously, the website would freeze and wait for each image to load before continuing. With callbacks, you can load the images asynchronously, which means that the website continues to load while the images are being loaded in the background.

- Handling form submissions: When a user submits a form, it takes time to process the data and send it to the server. If the form submission was executed synchronously, the user would have to wait for the data to be processed and sent before the form can be submitted. With callbacks, you can handle the form submission asynchronously, which means that the user can continue to interact with the form while the data is being processed and sent in the background

```js
function mainFunction(callback) {
  console.log("Performing operation...");
  // Use setTimeout to simulate an asynchronous operation
  setTimeout(function() {
    callback("Operation complete");
  }, 1000);
}
 
// Define the callback function
function callbackFunction(result) {
  console.log("Result: " + result);
}
 
// Call the main function with the callback function
mainFunction(callbackFunction);
//This code is contributed by Veerendra Singh Rajpoot

// Output
// Performing operation...
// Result: Operation complete
```


###  Promises in JS?

To manage asynchronous actions in JavaScript, promises are used. It is an assurance that something will be done. The promise is used to keep track of whether the asynchronous event has been executed or not and determines what happens after the event has occurred.

 

A Promise has four states: 

- fulfilled: Action related to the promise succeeded
- rejected: Action related to the promise failed
- pending: Promise is still pending i.e. not fulfilled or rejected yet
- settled: Promise has fulfilled or rejected

Syntax:
```js
let promise = new Promise(function(resolve, reject){
    // do something
});

// A promise can be created using Promise constructor.
```

**Parameters :**

- Promise constructor takes only one argument which is a callback function (and that callback function is also referred as an anonymous function too).
- Callback function takes two arguments, resolve and reject
- Perform operations inside the callback function and if everything went well then call resolve.
- If desired operations do not go well then call reject.


```js
var promise = new Promise(function(resolve, reject) {
const x = "hello";
const y = "hello"
if(x === y) {
    resolve();
} else {
    reject();
}
});
      
promise.
    then(function () {
        console.log('Success');
    }).
    catch(function () {
        console.log('Some error has occurred');
    });
```


Promise Consumers: Promises can be consumed by registering functions using .then and .catch methods.

**1.Promise then() Method :** It is invoked when a promise is either resolved or rejected. It may also be defined as a carrier that takes data from promise and further executes it successfully.

**Parameters:** It takes two functions as parameters.

- The first function is executed if the promise is resolved and a result is received.
- The second function is executed if the promise is rejected and an error is received. (It is optional and there is a better way to handle error using .catch() method

Example : 
```js
let promise = new Promise(function (resolve, reject) {
    resolve('Hello my world');
})
 
promise
    .then(function (successMessage) {
        //success handler function is invoked
        console.log(successMessage);
    }, function (errorMessage) {
        console.log(errorMessage);
    });
```

**2. Promise catch() Method :** It is invoked when a promise is either rejected or some error has occurred in execution. It is used as an Error Handler whenever at any step there is a chance of getting an error.

**Parameters:** It takes one function as a parameter.

- Function to handle errors or promise rejections.(.catch() method internally calls .then(null, errorHandler), i.e. .catch() is just a shorthand for .then(null, errorHandler) )

```js 

let promise = new Promise(function (resolve, reject) {
    reject('Promise Rejected')
})
 
promise
    .then(function (successMessage) {
        console.log(successMessage);
    })
    .catch(function (errorMessage) {
        //error handler function is invoked
        console.log(errorMessage);
    });
```


**Benefits of Promises :**

- Improves Code Readability
- Better handling of asynchronous operations
- Better flow of control definition in asynchronous logic
- Better Error Handling

**Promise vs Callback in JavaScript**

| 	| Callback | Promise |
|-- | ---------| -------|
| Syntax |	The syntax is difficult to understand.|	The syntax is user-friendly and easy to read because of then and catch.|
| Error handling |	Error handling may be hard to manage.|	Error handling is easier to manage using catch block.|
| Callback hell |	It may create callback hell.|	It resolves callback hell.|

---

### # Async Await :

Async/Await is used to work with promises in asynchronous functions. It is basically syntactic sugar for promises. It is just a wrapper to restyle code and make promises easier to read and use. It makes asynchronous code look more like synchronous/procedural code, which is easier to understand.

await can only be used in async functions. It is used for calling an async function and waits for it to resolve or reject. await blocks the execution of the code within the async function in which it is located. 



#### What is Async Function ?
Async simply allows us to write promises-based code as if it was synchronous and it checks that we are not breaking the execution thread. It operates asynchronously via the event loop. Async functions will always return a value. It makes sure that a promise is returned and if it is not returned then JavaScript automatically wraps it in a promise which is resolved with its value.

#### What is Await Function ?
Await function is used to wait for the promise. It could be used within the async block only. It makes the code wait until the promise returns a result. It only makes the async block wait.

This example shows the basic use of the await keyword in JavaScript.
```js
const getData = async () => {
    let y = await "Hello World";
    console.log(y);
}
 
console.log(1);
getData();
console.log(2);

// Output
// 1
// 2
// Hello World
```

**Error Handling in Async/Await :** For a successfully resolved promise, we use try and for rejected promise, we use catch. To run a code after the promise has been handled using try or catch, we can .finally() method. The code inside .finally() method runs once regardless of the state of the promise.

Example :
```js 
const helperPromise = function () {
    const promise = new Promise(function (resolve, reject) {
      const x = "hello";
      const y = "hello";
      if (x === y) {
        resolve("Strings are same");
      } else {
        reject("Strings are not same");
      }
    });
 
    return promise;
  };
 
  async function demoPromise() {
    try {
      let message = await helperPromise();
      console.log(message);
    } catch (error) {
      console.log("Error: " + error);
    }
  }
 
  demoPromise();
```
  
**Difference Between Promise and Async/Await :**

|Sr.no | Promise | Async/Await |
| ---- | --------| ------------|
| 1.  |	Promise is an object representing intermediate state of operation which is guaranteed to complete its execution at some point in future. |	Async/Await is a syntactic sugar for promises, a wrapper making the code execute more synchronously.|
| 2. |	Promise has 3 states – resolved, rejected and pending. |	It does not have any states. It returns a promise either resolved or rejected.|
| 3. |	If the function “fxn1” is to executed after the promise, then promise.then(fxn1) continues execution of the current function after adding the fxn1 call to the callback chain. |	If the function “fxn1” is to executed after await, then await X() suspends execution of the current function and then fxn1 is executed.|                                
| 4. |	 Error handling is done using .then() and .catch() methods. |	Error handling is done using .try() and .catch() methods.|
| 5. |	Promise chains can become difficult to understand sometimes. |	Using Async/Await makes it easier to read and understand the flow of the program as compared to promise chains.     |