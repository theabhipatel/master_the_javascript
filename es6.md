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