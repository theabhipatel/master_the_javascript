# ES 6 : ECMAScript 2015

ECMAScript 2015 was the second major revision to JavaScript.

ECMAScript 2015 is also known as ES6 and ECMAScript 6.

This chapter describes the most important features of ES6.

## New Features in ES6
- The let keyword
- The const keyword
- Arrow Functions
- The ... Operator
- For/of
- Map Objects
- Set Objects
- Classes
- Promises
- Symbol
- Default Parameters
- Function Rest Parameter
- String.includes()
- String.startsWith()
- String.endsWith()
- Array.from()
- Array keys()
- Array find()
- Array findIndex()
- New Math Methods
- New Number Properties
- New Number Methods
- New Global Methods
- Object entries
- JavaScript Modules


### # Let :
Let statement declares blocked scoped local variables, unlike the var keyword, which when used declares a variable globally or locally to an entire function regardless of the block scope.  

- Variables defined with let cannot be Redeclared.
- Variables defined with let must be Declared before use.
- Variables defined with let have Block Scope.
```js
let x = "John Doe";
let y ; 
y = x; // this is write syntax

```

### # Const :
 const declaration creates a read-only reference to a variable defined. The variable identifier cannot be reassigned.
- The const keyword allows you to declare a constant (a JavaScript variable with a constant value).

- Constants are similar to let variables, except that the value cannot be changed.



### Block Scope :
Before ES6 (2015), JavaScript had Global Scope and Function Scope.
ES6 introduced two important new JavaScript keywords: let and const.
These two keywords provide Block Scope in JavaScript.
Variables declared inside a { } block cannot be accessed from outside the block:


**What is Good?**
- `let` and `const` have block scope.
- `let` and `const` can not be redeclared.
- `let` and `const` must be declared before use.
- `let` and `const` does not bind to this.
- `let` and `const` are not hoisted.

**What is Not Good?**
- `var` does not have to be declared.
- `var` is hoisted.
- `var` binds to this.

**Difference Between var, let and const**
| keyword | Scope |	Redeclare |	Reassign |	Hoisted	 | Binds this |
| -- | -- | -- | -- | -- | -- |
| var |	No |	Yes |	Yes |	Yes |	Yes|
| let |	Yes |	No |	Yes |	No |	No |
| const |	Yes |	No | No |	No |	No |


### # Arrow Functions :
Arrow function uses the => syntax as its shorthand. It’s an alternative to the traditional arrow function.

- Arrow functions allows a short syntax for writing function expressions.
- You don't need the function keyword, the return keyword, and the curly brackets.
-  Arrow functions do not have their own this. They are not well suited for defining object methods.
- Arrow functions are not hoisted. They must be defined before they are used.
- Using const is safer than using var, because a function expression is always a constant value.
- You can only omit the return keyword and the curly brackets if the function is a single statement. 

let’s check an example for comparing both traditional vs arrow functions.

```js
    // Without using Arrow Function
    let square = function (x) {
        return (x * x);
    };
    console.log(square(9));
 
    // Using Arrow Function
    square = (x) => { return x * x; }
 
    console.log(square(9));
```

### # Spread (...) Operator :
 Spread allows an iterable such as array or strings to be expanded in places where zero or more arguments, there are also options to use object expression to be expanded in places where zero or more key-value pairs are expected.

 - The ... operator expands an iterable (like an array) into more elements:
 ```js
 const q1 = ["Jan", "Feb", "Mar"];
const q2 = ["Apr", "May", "Jun"];
const q3 = ["Jul", "Aug", "Sep"];
const q4 = ["Oct", "Nov", "May"];

const year = [...q1, ...q2, ...q3, ...q4];
 ```

 ### # Rest Operator : 
 The rest parameter allows a function to accept an indefinite number of arguments as an array. 
 ```js
 // REST concept
    function fun(a, ...b) {
        return a * b.length
    }

 // one more example 
function sum(...args) {
  let sum = 0;
  for (let arg of args) sum += arg;
  return sum;
}

let x = sum(4, 9, 16, 25, 29, 100, 66, 77);
 ```

### # The For Of Loop :
The JavaScript for/of statement loops through the values of an iterable objects.

for/of lets you loop over data structures that are iterable such as Arrays, Strings, Maps, NodeLists, and more.

The for/of loop has the following syntax:
```js
for (variable of iterable) {
  // code block to be executed
}
```

### # Map Objects :
The Map object holds key-value pair and holds into account the original insertion order of the keys.
- A Map holds key-value pairs where the keys can be any datatype.
- A Map remembers the original insertion order of the keys.
- A Map has a property that represents the size of the map.

| Method |	Description |
| ------ | --------------|
 | new Map() | 	Creates a new Map object |
| set() | Sets the value for a key in a Map |
| get() | Gets the value for a key in a Map |
| clear() | Removes all the elements from a Map |
| delete() | Removes a Map element specified by a key |
| has() | Returns true if a key exists in a Map |
| forEach() | Invokes a callback for each key/value pair in a Map |
| entries() | Returns an iterator object with the [key, value] pairs in a Map |
| keys() | Returns an iterator object with the keys in a Map |
| values() | Returns an iterator object of the values in a Map |

| Property |	Description |
| -------- |  -------------  |
| size |	Returns the number of Map elements |

**How to Create a Map**  

You can create a JavaScript Map by:
- Passing an Array to new Map()
- Create a Map and use Map.set()


### # Set Objects :
Set object stores unique values (just like set in math) of any type. It contains a collection of values and its possible to iterate through the elements of a set in the order at the time of insertion. 
- A JavaScript Set is a collection of unique values. 
- Each value can only occur once in a Set.
- A Set can hold any value of any data type.

| Method |	Description | 
| -- | -- |
| new Set() |	Creates a new Set |
| add() |	Adds a new element to the Set |
| delete() |	Removes an element from a Set |
| has() |	Returns true if a value exists |
| clear() |	Removes all elements from a Set |
| forEach() |	Invokes a callback for each element |
| values() |	Returns an Iterator with all the values in a Set |
| keys() |	Same as values() |
| entries() |	Returns an Iterator with the [value,value]  |pairs from a Set


| Property	| Description |
| -- | -- |
| size	| Returns the number elements in a Set |

**How to Create a Set :**  
You can create a JavaScript Set by:
- Passing an Array to new Set()
- Create a new Set and use add() to add values
- Create a new Set and use add() to add variables


### # weakSet and weakMap:
 The weakmap object is a collection (key, value) pairs, and in this case of weakmap the keys are weakly referenced, the keys in weakmap are of the object type. 

weakset objects let us store weakly held objects in the collection. Like weakmap, it is also a collection of objects, the difference comes in the part that weakest is the only collection of objects and weakset is weak, which means that reference to an object is being held weakly and therefore if there is no reference to an object stored in a weakset exist then those objects can be garbage collected by the garbage collector.

```js
 let s = new Set()
 
    s.add({ course: "Complete placement guide" });
    console.log(s);
 
    const course = { course: "python fundamentals" };
 
    // weakmap
    var gfg = new WeakMap();
    gfg.set(s, course);
 
 
    // waekset
    var coder = new WeakSet();
    coder.add(course);
 
    console.log(gfg, coder);
```

### # ES6/ES2015 classes:
 This feature really made javascript the language it is now. As you may know, classes are a template for creating an object. ES6 classes brought the power of inheritance, super calls, an instance of a class, and the constructor (which is initialized while creating a class).
 - JavaScript Classes are templates for JavaScript Objects.
- Use the keyword class to create a class.
- A JavaScript class is not an object. It is a template for JavaScript objects.

Class Declaration:
```js
  // Here class is declared
    class Rectangle {
 
        constructor(a, b) {
            this.a = a;
            this.b = b;
        }
    }
    let rect = new Rectangle(10, 20);
    console.log(rect.a, rect.b)
```
  
  ### # Promises:
You guess it right, this was the version of ECMAScript that brought promises to the world of Javascript and the rest is history, Promises are a library for asynchronous programming which is widely used in Javascript. Promises are also 1st class representations of a value that may be made available in the future, now what this means is with an example.

Example: Let’s suppose we request an item that is out of order in a shopping site so what we can do is maybe select the option of remind me when available if it’s given on the website and leave that site and maybe later some days after we may get a remainder, that what promises are it promises that we will get the thing that we have a request in some time.  

- A Promise is a JavaScript object that links "Producing Code" and "Consuming Code".
- "Producing Code" can take some time and "Consuming Code" must wait for the result.

```js
const myPromise = new Promise(function(myResolve, myReject) {
// "Producing Code" (May take some time)

  myResolve(); // when successful
  myReject();  // when error
});

// "Consuming Code" (Must wait for a fulfilled Promise).
myPromise.then(
  function(value) { /* code if successful */ },
  function(error) { /* code if some error */ }
);
```

### # Symbol Type :
A JavaScript Symbol is a primitive datatype just like Number, String, or Boolean.

- It represents a unique "hidden" identifier that no other code can accidentally access.
- For instance, if different coders want to add a person.id property to a person object belonging to a third-party code, they could mix each others values.
- Using Symbol() to create a unique identifiers, solves this problem:

```js
const person = {
  firstName: "John",
  lastName: "Doe",
  age: 50,
  eyeColor: "blue"
};

let id = Symbol('id');
person[id] = 140353;
// Now person[id] = 140353
// but person.id is still undefined
```

- Symbols are always unique.
- If you create two symbols with the same description they will have different values:

> Symbol("id") == Symbol("id"); // false


### # Default Parameter Values :
ES6 allows function parameters to have default values.
```js
function myFunction(x, y = 10) {
  // y is 10 if not passed or undefined
  return x + y;
}
myFunction(5); // will return 15
```


### # String.includes() : 
The includes() method returns true if a string contains a specified value, otherwise false:

```js
let text = "Hello world, welcome to the universe.";
text.includes("world")    // Returns true
```

### # String.startsWith() :
The startsWith() method returns true if a string begins with a specified value, otherwise false:

Example
```js
let text = "Hello world, welcome to the universe.";

text.startsWith("Hello")   // Returns true
```

### # String.endsWith() :
The endsWith() method returns true if a string ends with a specified value, otherwise false:

Example
```js
var text = "John Doe";
text.endsWith("Doe")    // Returns true
```

### # Array.from() : 
The Array.from() method returns an Array object from any object with a length property or any iterable object.

Example
```js
// Create an Array from a String:
Array.from("ABCDEFG")   // Returns [A,B,C,D,E,F,G]
```

### # Array keys() :
The keys() method returns an Array Iterator object with the keys of an array.

Example
Create an Array Iterator object, containing the keys of the array:
```js
const fruits = ["Banana", "Orange", "Apple", "Mango"];
const keys = fruits.keys();

let text = "";
for (let x of keys) {
  text += x + "<br>";
}
```

### # Array find() :
The find() method returns the value of the first array element that passes a test function.

the function takes 3 arguments:
- The item value
- The item index
- The array itself

This example finds (returns the value of ) the first element that is larger than 18:

Example

```js
const numbers = [4, 9, 16, 25, 29];
let first = numbers.find(myFunction);

function myFunction(value, index, array) {
  return value > 18;
} 
```

### # Array findIndex() :
The findIndex() method returns the index of the first array element that passes a test function.

This example finds the index of the first element that is larger than 18:

Example
```js
const numbers = [4, 9, 16, 25, 29];
let first = numbers.findIndex(myFunction);

function myFunction(value, index, array) {
  return value > 18;
}
```
---

### # New Math Methods :- 
ES6 added the following methods to the Math object:

- Math.trunc()
- Math.sign()
- Math.cbrt()
- Math.log2()
- Math.log10()

#### The Math.trunc() Method :
Math.trunc(x) returns the integer part of x:

Example
```js
Math.trunc(4.9);    // returns 4
Math.trunc(4.7);    // returns 4
Math.trunc(4.4);    // returns 4
Math.trunc(4.2);    // returns 4
Math.trunc(-4.2);    // returns -4
```

#### The Math.sign() Method :
Math.sign(x) returns if x is negative, null or positive:

Example
```js
Math.sign(-4);    // returns -1
Math.sign(0);    // returns 0
Math.sign(4);    // returns 1
```

#### The Math.cbrt() Method :
Math.cbrt(x) returns the cube root of x:

Example
```js
Math.cbrt(8);    // returns 2
Math.cbrt(64);    // returns 4
Math.cbrt(125);    // returns 5
```

#### The Math.log2() Method :
Math.log2(x) returns the base 2 logarithm of x:

Example
```js
Math.log2(2);    // returns 1
```

#### The Math.log10() Method :
Math.log10(x) returns the base 10 logarithm of x:

Example
```js
Math.log10(10);    // returns 1
```

--- 

### # New Number Properties :
ES6 added the following properties to the Number object:

- EPSILON
- MIN_SAFE_INTEGER
- MAX_SAFE_INTEGER

```js
// EPSILON Example
let x = Number.EPSILON;
// MIN_SAFE_INTEGER Example
let x = Number.MIN_SAFE_INTEGER;
// MAX_SAFE_INTEGER Example
let x = Number.MAX_SAFE_INTEGER;
```


### # New Number Methods :
ES6 added 2 new methods to the Number object:

- Number.isInteger()
- Number.isSafeInteger()

**The Number.isInteger() Method** :  
The Number.isInteger() method returns true if the argument is an integer.

Example
```js
Number.isInteger(10);        // returns true
Number.isInteger(10.5);      // returns false
```

**The Number.isSafeInteger() Method :**  
A safe integer is an integer that can be exactly represented as a double precision number.


JS Debugging
JS Style Guide
JS Best Practices
JS Mistakes
JS Performance
JS Reserved Words

JS Versions
JS Versions
JS 2009 (ES5)
JS 2015 (ES6)
JS 2016
JS 2017
JS 2018
JS 2019
JS 2020
JS 2021/2022
JS IE / Edge
JS History

JS Objects
Object Definitions
Object Properties
Object Methods
Object Display
Object Accessors
Object Constructors
Object Prototypes
Object Iterables
Object Sets
Object Maps
Object Reference

JS Functions
Function Definitions
Function Parameters
Function Invocation
Function Call
Function Apply
Function Bind
Function Closures

JS Classes
Class Intro
Class Inheritance
Class Static

JS Async
JS Callbacks
JS Asynchronous
JS Promises
JS Async/Await

JS HTML DOM
DOM Intro
DOM Methods
DOM Document
DOM Elements
DOM HTML
DOM Forms
DOM CSS
DOM Animations
DOM Events
DOM Event Listener
DOM Navigation
DOM Nodes
DOM Collections
DOM Node Lists

JS Browser BOM
JS Window
JS Screen
JS Location
JS History
JS Navigator
JS Popup Alert
JS Timing
JS Cookies

JS Web APIs
Web API Intro
Web Forms API
Web History API
Web Storage API
Web Worker API
Web Fetch API
Web Geolocation API

JS AJAX
AJAX Intro
AJAX XMLHttp
AJAX Request
AJAX Response
AJAX XML File
AJAX PHP
AJAX ASP
AJAX Database
AJAX Applications
AJAX Examples

JS JSON
JSON Intro
JSON Syntax
JSON vs XML
JSON Data Types
JSON Parse
JSON Stringify
JSON Objects
JSON Arrays
JSON Server
JSON PHP
JSON HTML
JSON JSONP

JS vs jQuery
jQuery Selectors
jQuery HTML
jQuery CSS
jQuery DOM

JS Graphics
JS Graphics
JS Canvas
JS Plotly
JS Chart.js
JS Google Chart
JS D3.js

JS Examples
JS Examples
JS HTML DOM
JS HTML Input
JS HTML Objects
JS HTML Events
JS Browser
JS Editor
JS Exercises
JS Quiz
JS Bootcamp
JS Certificate

JS References
JavaScript Objects
HTML DOM Objects



Javascript ES6
ECMAScript 2015 was the second major revision to JavaScript.

ECMAScript 2015 is also known as ES6 and ECMAScript 6.

This chapter describes the most important features of ES6.

New Features in ES6
The let keyword
The const keyword
Arrow Functions
The ... Operator
For/of
Map Objects
Set Objects
Classes
Promises
Symbol
Default Parameters
Function Rest Parameter
String.includes()
String.startsWith()
String.endsWith()
Array.from()
Array keys()
Array find()
Array findIndex()
New Math Methods
New Number Properties
New Number Methods
New Global Methods
Object entries
JavaScript Modules
Browser Support for ES6 (2015)
Safari 10 and Edge 14 were the first browsers to fully support ES6:

Chrome 58	Edge 14	Firefox 54	Safari 10	Opera 55
Jan 2017	Aug 2016	Mar 2017	Jul 2016	Aug 2018
JavaScript let
The let keyword allows you to declare a variable with block scope.

Example
var x = 10;
// Here x is 10
{
  let x = 2;
  // Here x is 2
}
// Here x is 10
Read more about let in the chapter: JavaScript Let.

JavaScript const
The const keyword allows you to declare a constant (a JavaScript variable with a constant value).

Constants are similar to let variables, except that the value cannot be changed.

Example
var x = 10;
// Here x is 10
{
  const x = 2;
  // Here x is 2
}
// Here x is 10
Read more about const in the chapter: JavaScript Const.

Arrow Functions
Arrow functions allows a short syntax for writing function expressions.

You don't need the function keyword, the return keyword, and the curly brackets.

Example
// ES5
var x = function(x, y) {
   return x * y;
}

// ES6
const x = (x, y) => x * y;
Arrow functions do not have their own this. They are not well suited for defining object methods.

Arrow functions are not hoisted. They must be defined before they are used.

Using const is safer than using var, because a function expression is always a constant value.

You can only omit the return keyword and the curly brackets if the function is a single statement. Because of this, it might be a good habit to always keep them:

Example
const x = (x, y) => { return x * y };
Learn more about Arrow Functions in the chapter: JavaScript Arrow Function.

The Spread (...) Operator
The ... operator expands an iterable (like an array) into more elements:

Example
const q1 = ["Jan", "Feb", "Mar"];
const q2 = ["Apr", "May", "Jun"];
const q3 = ["Jul", "Aug", "Sep"];
const q4 = ["Oct", "Nov", "May"];

const year = [...q1, ...q2, ...q3, ...q4];
The ... operator can be used to expand an iterable into more arguments for function calls:

Example
const numbers = [23,55,21,87,56];
let maxValue = Math.max(...numbers);
The For/Of Loop
The JavaScript for/of statement loops through the values of an iterable objects.

for/of lets you loop over data structures that are iterable such as Arrays, Strings, Maps, NodeLists, and more.

The for/of loop has the following syntax:

for (variable of iterable) {
  // code block to be executed
}
variable - For every iteration the value of the next property is assigned to the variable. Variable can be declared with const, let, or var.

iterable - An object that has iterable properties.

Looping over an Array
Example
const cars = ["BMW", "Volvo", "Mini"];
let text = "";

for (let x of cars) {
  text += x + " ";
}
Looping over a String
Example
let language = "JavaScript";
let text = "";

for (let x of language) {
    text += x + " ";
}
Learn more in the chapter: JavaScript Loop For/In/Of.

JavaScript Maps
Being able to use an Object as a key is an important Map feature.

Example
const fruits = new Map([
["apples", 500],
["bananas", 300],
["oranges", 200]
]);
Learn more about Map objects, and the difference between a Map and an Array, in the the chapter: JavaScript Maps.

JavaScript Sets
Example
// Create a Set
const letters = new Set();

// Add some values to the Set
letters.add("a");
letters.add("b");
letters.add("c");
Learn more about Set objects in the the chapter: JavaScript Sets.

JavaScript Classes
JavaScript Classes are templates for JavaScript Objects.

Use the keyword class to create a class.

Always add a method named constructor():

Syntax
class ClassName {
  constructor() { ... }
}
Example
class Car {
  constructor(name, year) {
    this.name = name;
    this.year = year;
  }
}
The example above creates a class named "Car".

The class has two initial properties: "name" and "year".

A JavaScript class is not an object.

It is a template for JavaScript objects.

Using a Class
When you have a class, you can use the class to create objects:

Example
const myCar1 = new Car("Ford", 2014);
const myCar2 = new Car("Audi", 2019);

Learn more about classes in the the chapter: JavaScript Classes.

JavaScript Promises
A Promise is a JavaScript object that links "Producing Code" and "Consuming Code".

"Producing Code" can take some time and "Consuming Code" must wait for the result.

Promise Syntax
const myPromise = new Promise(function(myResolve, myReject) {
// "Producing Code" (May take some time)

  myResolve(); // when successful
  myReject();  // when error
});

// "Consuming Code" (Must wait for a fulfilled Promise).
myPromise.then(
  function(value) { /* code if successful */ },
  function(error) { /* code if some error */ }
);
Example Using a Promise
const myPromise = new Promise(function(myResolve, myReject) {
  setTimeout(function() { myResolve("I love You !!"); }, 3000);
});

myPromise.then(function(value) {
  document.getElementById("demo").innerHTML = value;
});

Learn more about Promises in the the chapter: JavaScript Promises.

The Symbol Type
A JavaScript Symbol is a primitive datatype just like Number, String, or Boolean.

It represents a unique "hidden" identifier that no other code can accidentally access.

For instance, if different coders want to add a person.id property to a person object belonging to a third-party code, they could mix each others values.

Using Symbol() to create a unique identifiers, solves this problem:

Example
const person = {
  firstName: "John",
  lastName: "Doe",
  age: 50,
  eyeColor: "blue"
};

let id = Symbol('id');
person[id] = 140353;
// Now person[id] = 140353
// but person.id is still undefined
Note
Symbols are always unique.

If you create two symbols with the same description they will have different values:

Symbol("id") == Symbol("id"); // false
Default Parameter Values
ES6 allows function parameters to have default values.

Example
function myFunction(x, y = 10) {
  // y is 10 if not passed or undefined
  return x + y;
}
myFunction(5); // will return 15
Function Rest Parameter
The rest parameter (...) allows a function to treat an indefinite number of arguments as an array:

Example
function sum(...args) {
  let sum = 0;
  for (let arg of args) sum += arg;
  return sum;
}

let x = sum(4, 9, 16, 25, 29, 100, 66, 77);
String.includes()
The includes() method returns true if a string contains a specified value, otherwise false:

Example
let text = "Hello world, welcome to the universe.";
text.includes("world")    // Returns true
String.startsWith()
The startsWith() method returns true if a string begins with a specified value, otherwise false:

Example
let text = "Hello world, welcome to the universe.";

text.startsWith("Hello")   // Returns true
String.endsWith()
The endsWith() method returns true if a string ends with a specified value, otherwise false:

Example
var text = "John Doe";
text.endsWith("Doe")    // Returns true
Array.from()
The Array.from() method returns an Array object from any object with a length property or any iterable object.

Example
Create an Array from a String:

Array.from("ABCDEFG")   // Returns [A,B,C,D,E,F,G]
Array keys()
The keys() method returns an Array Iterator object with the keys of an array.

Example
Create an Array Iterator object, containing the keys of the array:

const fruits = ["Banana", "Orange", "Apple", "Mango"];
const keys = fruits.keys();

let text = "";
for (let x of keys) {
  text += x + "<br>";
}
Array find()
The find() method returns the value of the first array element that passes a test function.

This example finds (returns the value of ) the first element that is larger than 18:

Example
const numbers = [4, 9, 16, 25, 29];
let first = numbers.find(myFunction);

function myFunction(value, index, array) {
  return value > 18;
}
Note that the function takes 3 arguments:

The item value
The item index
The array itself
Array findIndex()
The findIndex() method returns the index of the first array element that passes a test function.

This example finds the index of the first element that is larger than 18:

Example
const numbers = [4, 9, 16, 25, 29];
let first = numbers.findIndex(myFunction);

function myFunction(value, index, array) {
  return value > 18;
}
Note that the function takes 3 arguments:

The item value
The item index
The array itself
New Math Methods
ES6 added the following methods to the Math object:

Math.trunc()
Math.sign()
Math.cbrt()
Math.log2()
Math.log10()
The Math.trunc() Method
Math.trunc(x) returns the integer part of x:

Example
Math.trunc(4.9);    // returns 4
Math.trunc(4.7);    // returns 4
Math.trunc(4.4);    // returns 4
Math.trunc(4.2);    // returns 4
Math.trunc(-4.2);    // returns -4
The Math.sign() Method
Math.sign(x) returns if x is negative, null or positive:

Example
Math.sign(-4);    // returns -1
Math.sign(0);    // returns 0
Math.sign(4);    // returns 1
The Math.cbrt() Method
Math.cbrt(x) returns the cube root of x:

Example
Math.cbrt(8);    // returns 2
Math.cbrt(64);    // returns 4
Math.cbrt(125);    // returns 5
The Math.log2() Method
Math.log2(x) returns the base 2 logarithm of x:

Example
Math.log2(2);    // returns 1
The Math.log10() Method
Math.log10(x) returns the base 10 logarithm of x:

Example
Math.log10(10);    // returns 1
New Number Properties
ES6 added the following properties to the Number object:

EPSILON
MIN_SAFE_INTEGER
MAX_SAFE_INTEGER
EPSILON Example
let x = Number.EPSILON;
MIN_SAFE_INTEGER Example
let x = Number.MIN_SAFE_INTEGER;
MAX_SAFE_INTEGER Example
let x = Number.MAX_SAFE_INTEGER;
New Number Methods
ES6 added 2 new methods to the Number object:

Number.isInteger()
Number.isSafeInteger()
The Number.isInteger() Method
The Number.isInteger() method returns true if the argument is an integer.

Example
Number.isInteger(10);        // returns true
Number.isInteger(10.5);      // returns false
The Number.isSafeInteger() Method
A safe integer is an integer that can be exactly represented as a double precision number.

The Number.isSafeInteger() method returns true if the argument is a safe integer.

Example
Number.isSafeInteger(10);    // returns true
Number.isSafeInteger(12345678901234567890);  // returns false
- Safe integers are all integers from -(2^53 - 1) to +(253 - 1).
- This is safe: 9007199254740991. This is not safe: 9007199254740992.

The Number.isSafeInteger() method returns true if the argument is a safe integer.

Example
```js
Number.isSafeInteger(10);    // returns true
Number.isSafeInteger(12345678901234567890);  // returns false
```

--- 

### # New Global Methods : 
ES6 added 2 new global number methods:

- isFinite()
- isNaN()

**The isFinite() Method :**
The global isFinite() method returns false if the argument is Infinity or NaN.

Otherwise it returns true:

Example
```js
isFinite(10/0);       // returns false
isFinite(10/1);       // returns true
```

**The isNaN() Method :**
The global isNaN() method returns true if the argument is NaN. Otherwise it returns false:

Example
```js
isNaN("Hello");       // returns true
```
--- 

### # Object entries() :
Create an Array Iterator, and then iterate over the key/value pairs:

The entries() method does not change the original array.

Example
```js
const fruits = ["Banana", "Orange", "Apple", "Mango"];
const f = fruits.entries();

for (let x of f) {
  document.getElementById("demo").innerHTML += x;
}
The entries() method returns an Array Iterator object with key/value pairs:

[0, "Banana"]
[1, "Orange"]
[2, "Apple"]
[3, "Mango"]
```


### # Modules :
JavaScript modules allow you to break up your code into separate files.

- This makes it easier to maintain a code-base.
- Modules are imported from external files with the import statement.
- Modules also rely on type="module" in the <script> tag.


Modules are imported in two differen ways:

```js
// Import from named exports
// Import named exports from the file person.js:

import { name, age } from "./person.js";

// Import from default exports
// Import a default export from the file message.js:

import message from "./message.js";


```
 