# Variables and Data Types:





## Variables :
Variables in JavaScript are declared using one of three keywords: let, const, or var.

**1. let :** 
`let` allows you to declare block-level variables. The declared variable is available from the block it is enclosed in.(**Remember it : `let` can be re-assigned, but can't be re-declare in it's scope.**)

**2. const :**
`const` allows you to declare variables whose values are never intended to change. The variable is available from the block it is declared in. (**Remember this : `const` can't be re-assigned or re-declare in it's scope.**)

**3. var :**
In JavaScript, `var` is used to create variables, but it has less strict scoping rules than let and const, which can sometimes lead to unexpected behaviors and make the code harder to understand and maintain.(**Remember this : `var` can be re-assigned or re-declare always. that's why in  modern javascript we should not use it.**)



## Data types : 
There are two types of data type in javascript. 

 ### **1. Primitive data types:**
  The predefined data types provided by JavaScript language are known as primitive data types. Primitive data types are also known as in-built data types.

JavaScript offers seven primitive types:

- **String :** g: The string data type in javascript represents a sequence of characters that are surrounded by single or double quotes.used to store text.
```js
// here we can use signle qoute, double qoute as well as template literals.
let name = "Bharat"; // double qoute
let message = 'Namaste, world!'; // signle qoute
let address = `wherever you live` //template literals
```

- **Number :** Number data type in javascript can be used to hold decimal values as well as values without decimals.
```js
let age = 25;
let pi = 3.14;
```

- **BigInt :** Used for arbitrarily large integers.This data type can represent numbers greater than 2^53^-1 which helps to perform operations on large numbers. The number is specified by writing ‘n’ at the end of the value
```js
const bigIntValue = 1234567890123456789012345678901234567890n;
```

- **Boolean :**  The boolean data type can accept only two values i.e. true and false. — usually used for conditional logic.
```js
let isStudent = true;
let hasCar = false;
```

- **Symbol :** Used for creating unique identifiers that won't collide. This data type is used to create objects which will always be unique. these objects can be created using Symbol constructor.
```js
const uniqueSymbol = Symbol("description");
```

- **Undefined :** indicating that a variable has not been assigned a value. The meaning of undefined is ‘value is not assigned’.
```js
let uninitializedVar;
```

- **Null :** indicating a deliberate non-value.
This data type can hold only one possible value that is null.
```js
let noValue = null;
```

All primitive types, except null, can be tested by the typeof operator. typeof null returns "object", so one has to use === null to test for null.

| Type | typeof return value |
| -----| --------------------|	
| Null 	| "object"	|
| Undefined	| "undefined"	|
| Boolean	| "boolean"	|
| Number	| "number"	|
| BigInt	| "bigint"	|
| String	| "string"	|
| Symbol	| " symbol" |


Everything else is known as a non-primitive and an Object type. Common object types include:


 ### **2. Non-primitive data types :** 
 The data types that are derived from primitive data types of the JavaScript language are known as non-primitive data types. It is also known as derived data types or reference data types.

- **Array :** Represents an ordered list of values. With the help of an array, we can store more than one element under a single name.

```js
let colors = ["red", "green", "blue"];
let numbers = [1, 2, 3, 4, 5];
```

- **Object :** Represents a collection of key-value pairs.An object in Javascript is an entity having properties and methods. `Everything is an object in javascript.`
```js
let person = {
  firstName: "Jane",
  lastName: "Doe",
  age: 30
};
```

- **Function :** Represents a block of reusable code.
```js
function add(a, b) {
  return a + b;
}
```

- **Date :** Represents a specific moment in time.
```js
const currentDate = new Date();
```

- **RegExp :** Represents regular expressions for pattern matching.
```js
const pattern = /[a-zA-Z]+/;
```
- **Error**


#### Difference between Primitive vs Non-Primitive :

| Primitive |  Non-Primitive |
|    ------     |  -------  |  
| Primitive Data types are predefined. | Non-Primitive data types are created by the programmer |
| Primitive Data types will have certain values. |	Non-Primitive data types can be NULL.|
| Size depends on the type of data structure.|	Size is not fixed|

## Some importent things about variables :

- In Javascript when we assign any primitive variable to another. it will make a copy of data but when we assign any non-primitive or reference data to another. It will not make a copy of data rather it will reference to that data. and then if we make changes in second variable. it would also change the first variable because it has referece to that variable in memory . that's why we called non-primitive data to reference data type as well. 

- JavaScript is a dynamically typed language, so variables can change their data types during runtime. For example, a variable initially holding a number can be assigned a string value later.