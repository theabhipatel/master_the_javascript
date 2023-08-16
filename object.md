# Object
This will give you information about Object and all the working methods there are present in objects.


## Definition : 
 An object in JavaScript is a collection of related data and functions grouped together under a single name. It allows you to store and organize information in the form of key-value pairs, where each key is a string and each value can be a variety of data types, including other objects or functions. 

 - **in simplest way we can say** - in Javascript Object is a data type. with the help of object we store data in key-value pair. Where key is always string and value can be any data type like string, boolean, number, object, array etc.
 - Object is a **non-premetive** and  **reference** data type, like array.
 - **reference** data type means when we assign any object to another object, it would not make the copy of the previous object rather it will reference the memory location. that's why if we make some changes in second object, the first object will also be modified. 
 - In the **Javascript everything  is an object at the end.** it means all the things which are there in javascript convert into the object. 

## Methods : 
#### 1. Object.assign() :
The Object.assign() static method copies all enumerable own properties from one or more source objects to a target object. It returns the modified target object.

```js
const target = { a: 1, b: 2 };
const source = { b: 4, c: 5 };

const returnedTarget = Object.assign(target, source);

console.log(target);
// Expected output: Object { a: 1, b: 4, c: 5 }

console.log(returnedTarget === target);
// Expected output: true

// or we can assign it to the blank object 
const copyToBlank = Object.assign({},  target, source)
console.log(copyToBlank)
// Expected output: Object { a: 1, b: 4, c: 5 }

```


#### 2. Object.create() :
The Object.create() static method creates a new object, using an existing object as the prototype of the newly created object. it inherites all the values that have in that existing object.
```js
const person = {
  isHuman: false,
  printIntroduction: function () {
    console.log(`My name is ${this.name}. Am I human? ${this.isHuman}`);
  },
};

const me = Object.create(person);

me.name = 'Matthew'; // "name" is a property set on "me", but not on "person"
me.isHuman = true; // Inherited properties can be overwritten

me.printIntroduction();
// Expected output: "My name is Matthew. Am I human? true"
```

#### 3. Object.keys() :
The Object.keys() static method returns an array of a given object's own enumerable string-keyed property names.
```js
const object1 = {
  a: 'somestring',
  b: 42,
  c: false,
};

console.log(Object.keys(object1));
// Expected output: Array ["a", "b", "c"]
```

#### 4. Object.values() :
The Object.values() static method returns an array of a given object's own enumerable string-keyed property values.
```js
const object1 = {
  a: 'somestring',
  b: 42,
  c: false,
};

console.log(Object.values(object1));
// Expected output: Array ["somestring", 42, false]
```


#### 5. Object.entries() :
The Object.entries() static method returns an array of a given object's own enumerable string-keyed property key-value pairs.

```js
const object1 = {
  a: 'somestring',
  b: 42,
};

console.log(Object.entries(object1))
// Exprected output : Array [["a", "somestring"],["b", 42]]

for (const value of Object.entries(object1)) {
  console.log(value);
}

// Expected output:
// Array ["a", "somestring"]
// Array ["b", 42]

// or we can do like this ->
for (const [key, value] of Object.entries(object1)) {
  console.log(`${key}: ${value}`);
}
// Expected output:
// "a: somestring"
// "b: 42"
```

#### 6. Object.fromEntries() :
The Object.fromEntries() static method transforms a list of key-value pairs into an object.
```js
const entries = new Map([
  ['foo', 'bar'],
  ['baz', 42],
]);

const obj = Object.fromEntries(entries);

console.log(obj);
// Expected output: Object { foo: "bar", baz: 42 }

```

#### 7. Object.freeze() :
The Object.freeze() static method freezes an object. Freezing an object prevents extensions and makes existing properties non-writable and non-configurable. A frozen object can no longer be changed: new properties cannot be added, existing properties cannot be removed, their enumerability, configurability, writability, or value cannot be changed, and the object's prototype cannot be re-assigned. freeze() returns the same object that was passed in.

Freezing an object is the highest integrity level that JavaScript provides.
```js
const obj = {
  prop: 42,
};

Object.freeze(obj);

obj.prop = 33;
// Throws an error in strict mode

console.log(obj.prop);
// Expected output: 42
```

#### 8. Object.isFrozen() :
The Object.isFrozen() static method determines if an object is frozen. and returns true of false.
```js
const object1 = {
  property1: 42,
};

console.log(Object.isFrozen(object1));
// Expected output: false

Object.freeze(object1);

console.log(Object.isFrozen(object1));
// Expected output: true

```


---
## Now for Pro Player ->

#### 9. Object.defineProperties() :
The Object.defineProperties() static method defines new or modifies existing properties directly on an object, returning the object.
```js
const object1 = {};

Object.defineProperties(object1, {
  property1: {
    value: 42,
    writable: true,
  },
  property2: {},
});

console.log(object1.property1);
// Expected output: 42
```

#### 10. Object.defineProperty() :
The Object.defineProperty() static method defines a new property directly on an object, or modifies an existing property on an object, and returns the object.
```js
const object1 = {};

Object.defineProperty(object1, 'property1', {
  value: 42,
  writable: false,
});

object1.property1 = 77;
// Throws an error in strict mode

console.log(object1.property1);
// Expected output: 42
```

#### 11. Object.getOwnPropertyNames() :
The Object.getOwnPropertyNames() static method returns an array of all properties (including non-enumerable properties except for those which use Symbol) found directly in a given object.
```js
const object1 = {
  a: 1,
  b: 2,
  c: 3,
};

console.log(Object.getOwnPropertyNames(object1));
// Expected output: Array ["a", "b", "c"]

```

#### 12. Object.getOwnPropertySymbols() :
The Object.getOwnPropertySymbols() static method returns an array of all symbol properties found directly upon a given object.
```js
const object1 = {};
const a = Symbol('a');
const b = Symbol.for('b');

object1[a] = 'localSymbol';
object1[b] = 'globalSymbol';

const objectSymbols = Object.getOwnPropertySymbols(object1);

console.log(objectSymbols);
// Expected output: Array [Symbol(a), Symbol(b)]

console.log(objectSymbols.length);
// Expected output: 2
```

#### 13. Object.hasOwn() :
The Object.hasOwn() static method returns true if the specified object has the indicated property as its own property. If the property is inherited, or does not exist, the method returns false.

Note: Object.hasOwn() is intended as a replacement for Object.prototype.hasOwnProperty().
```js
const object1 = {
  prop: 'exists',
};

console.log(Object.hasOwn(object1, 'prop'));
// Expected output: true

console.log(Object.hasOwn(object1, 'toString'));
// Expected output: false

console.log(Object.hasOwn(object1, 'undeclaredPropertyValue'));
// Expected output: false
```

#### 14. Object.prototype.hasOwnProperty() :
The hasOwnProperty() method of Object instances returns a boolean indicating whether this object has the specified property as its own property (as opposed to inheriting it).

Note: Object.hasOwn() is recommended over hasOwnProperty(), in browsers where it is supported.
```js
const object1 = {};
object1.property1 = 42;

console.log(object1.hasOwnProperty('property1'));
// Expected output: true

console.log(object1.hasOwnProperty('toString'));
// Expected output: false

console.log(object1.hasOwnProperty('hasOwnProperty'));
// Expected output: false
```

#### 15. Object.is() :
The Object.is() static method determines whether two values are the same value.
```js
console.log(Object.is('1', 1));
// Expected output: false

console.log(Object.is(NaN, NaN));
// Expected output: true

console.log(Object.is(-0, 0));
// Expected output: false

const obj = {};
console.log(Object.is(obj, {}));
// Expected output: false


const obj1 = {a:'a'};
const obj2 = {a:'a'};
console.log(Object.is(obj1, obj2));
// Expected output: false
```




#### 16. Object.seal() :
The Object.seal() static method seals an object. Sealing an object prevents extensions and makes existing properties non-configurable. A sealed object has a fixed set of properties: new properties cannot be added, existing properties cannot be removed, their enumerability and configurability cannot be changed, and its prototype cannot be re-assigned. Values of existing properties can still be changed as long as they are writable. seal() returns the same object that was passed in.
```js
const object1 = {
  property1: 42,
};

Object.seal(object1);
object1.property1 = 33;
console.log(object1.property1);
// Expected output: 33

delete object1.property1; // Cannot delete when sealed
console.log(object1.property1);
// Expected output: 33

```

#### 17. Object.prototype.toString() :
The toString() method of Object instances returns a string representing this object. This method is meant to be overridden by derived objects for custom type conversion logic.
```js
function Dog(name) {
  this.name = name;
}

const dog1 = new Dog('Gabby');

Dog.prototype.toString = function dogToString() {
  return `${this.name}`;
};

console.log(dog1.toString());
// Expected output: "Gabby"
```

#### 18. Object.prototype.toLocaleString() :
The toLocaleString() method of Object instances returns a string representing this object. This method is meant to be overridden by derived objects for locale-specific purposes.
```js
const date1 = new Date(Date.UTC(2012, 11, 20, 3, 0, 0));

console.log(date1.toLocaleString('ar-EG'));
// Expected output: "٢٠‏/١٢‏/٢٠١٢ ٤:٠٠:٠٠ ص"

const number1 = 123456.789;

console.log(number1.toLocaleString('de-DE'));
// Expected output: "123.456,789"
```

#### 19. Object.prototype.valueOf() :
The valueOf() method of Object instances converts the this value to an object. This method is meant to be overridden by derived objects for custom type conversion logic.
```js
function MyNumberType(n) {
  this.number = n;
}

MyNumberType.prototype.valueOf = function () {
  return this.number;
};

const object1 = new MyNumberType(4);

console.log(object1 + 3);
// Expected output: 7
```


### Other methods : 
- Object.prototype.propertyIsEnumerable()
- Object.isExtensible()
- Object.preventExtensions()
- Object.isSealed()
- Object.getOwnPropertyDescriptor()
- Object.getOwnPropertyDescriptors()
- Object.getPrototypeOf()
- Object.prototype.isPrototypeOf()
- Object.setPrototypeOf()





