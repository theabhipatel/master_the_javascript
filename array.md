# Array in JavaScript
all methods of array all here with explaination as well as example.


## Methods in Array 

 #### 1. push() :

Appends new elements to the end of an array, and returns the new length of the array.
```javascript 

const arr = [1, 2, 3, 4, 5];
const newReturn =  arr.push(6, 7);
console.log(newReturn) // output -> 7 (as the length of new array is 7)
console.log(arr); // output -> [1, 2, 3, 4, 5, 6, 7];

```

 #### 2. unshift() :
AInserts new elements at the start of an array, and returns the new length of the array.
```javascript 

const arr = [1, 2, 3, 4, 5];
const newReturn =  arr.unshift(6, 7);
console.log(newReturn) // output -> 7 (as the length of new array is 7)
console.log(arr); // output -> [6, 7, 1, 2, 3, 4, 5];

```

 #### 3. pop() : 
Removes the last element from an array and returns it. If the array is empty, undefined is returned and the array is not modified.
```javascript 

const arr = [1, 2, 3, 4, 5];
const newReturn =  arr.pop();
console.log(newReturn) // output -> a (as the last element is 5)
console.log(arr); // output -> [ 1, 2, 3, 4 ]

```

 #### 4. shift() :
Removes the first element from an array and returns it. If the array is empty, undefined is returned and the array is not modified.
```javascript 

const arr = [1, 2, 3, 4, 5];
const newReturn =  arr.shift();
console.log(newReturn) // output -> 1 (as the first element is 1)
console.log(arr); // output -> [  2, 3, 4, 5 ]

```


#### 5. concat() :
The concat() method of Array instances is used to merge two or more arrays. This method does not change the existing arrays, but instead returns a new array.
```javascript
const array1 = ['a', 'b', 'c'];
const array2 = ['d', 'e', 'f'];
const array3 = ['1', '2', '3'];
const array4 = array1.concat(array2, array3);

console.log(array4);
// output -> ["a", "b", "c", "d", "e", "f", "1", "2", "3"]
```

#### 6. slice() : 
The slice() method of Array instances returns a shallow copy of a portion of an array into a new array object selected from start to end (end not included) where start and end represent the index of items in that array. The original array will not be modified.

```javascript 
console.log(animals.slice(2));
// output ->  Array ["camel", "duck", "elephant"]

console.log(animals.slice(2, 4));
// output ->  Array ["camel", "duck"]

console.log(animals.slice(-2));
// output ->  Array ["duck", "elephant"]

console.log(animals.slice(1, -1));
// output -> ["bison", "camel", "duck"]

console.log(animals.slice());
// array will not be modified in this case
// output -> Array ["ant", "bison", "camel", "duck", "elephant"]

```

#### 7. splice() :
The splice() method of Array instances changes the contents of an array by removing or replacing existing elements or adding new elements, and return removed elements in form of array [].
```javascript
splice(start, deleteCount, item0, item1, /* …, */ itemN)

const months = ['Jan', 'March', 'April', 'June'];
months.splice(1, 0, 'Feb'); // Inserts at index 1

console.log(months);
// output -> Array ["Jan", "Feb", "March", "April", "June"]

const whatReturns = months.splice(4, 1, 'May');
// Replaces 1 element at index 4
console.log(months);
// output -> Array ["Jan", "Feb", "March", "April", "May"]
console.log(whatReturns) 
// output -> ["June"]
```

#### 8. indexOf() :
The indexOf() method of Array instances returns the first index at which a given element can be found in the array, or -1 if it is not present.
```javascript
const beasts = ['ant', 'bison', 'camel', 'duck', 'bison'];

console.log(beasts.indexOf('bison'));
// output -> 1

// Start from index 2
console.log(beasts.indexOf('bison', 2));
// output -> 4

console.log(beasts.indexOf('giraffe'));
// output -> -1

```

#### 9. lastIndexOf() :
The lastIndexOf() method of Array instances returns the last index at which a given element can be found in the array, or -1 if it is not present. The array is searched from backwards, 
```javascript
const animals = ['Parrot', 'Tiger', 'Penguin', 'Parrot'];

console.log(animals.lastIndexOf('Parrot'));
// output -> 3

console.log(animals.lastIndexOf('Tiger'));
// output -> 1

```

#### 10. includes() :
The includes() method of Array Determines whether an array contains a certain element or not, returning true or false. it is works only in premetive data type.  
```javascript
const array1 = [1, 2, 3];

console.log(array1.includes(2));
// output -> true

console.log(array1.includes(4));
// output -> false
```

#### 11. find() :
The find() method of Array instances returns the first element in the provided array that satisfies the provided testing function. If no values satisfy the testing function, undefined is returned.

```javascript
const array1 = [5, 12, 8, 130, 44];

const found = array1.find((element) => element > 10);

console.log(found);
// output -> 12

```

#### 12. findIndex() :
The findIndex() method of Array instances returns the index of the first element in an array that satisfies the provided testing function. If no elements satisfy the testing function, -1 is returned.
```javascript
const array1 = [5, 12, 8, 130, 44];

const isLargeNumber = (element) => element > 13;

console.log(array1.findIndex(isLargeNumber));
// output -> 3

```

#### 13. forEach() :
The forEach() method is an iterative method. It calls a provided callbackFn function once for each element in an array in ascending-index order.  forEach() always returns undefined and that's why it is not chainable. it modifies the original array.
```javascript
const array1 = [1,2,3];

array1.forEach((element, index, array) => console.log(element +1));
// output -> 2
// output -> 3
// output -> 4
```

#### 14. map() :
The map() method is an iterative method. It calls a provided callbackFn function once for each element in an array and constructs a new array from the results.
```javascript
const array1 = [1, 4, 9, 16];

// Pass a function to map
const map1 = array1.map((x) => x * 2);

console.log(map1);
// output -> Array [2, 8, 18, 32]
```

#### 15. filter() :
The filter() method is an iterative method. It calls a provided callbackFn function once for each element in an array, and constructs a new array of all the values for which callbackFn returns a truthy value. Array elements which do not pass the callbackFn test are not included in the new array.
```javascript
const words = ['spray', 'limit', 'elite', 'exuberant', 'destruction', 'present'];

const result = words.filter((word) => word.length > 6);

console.log(result);
// output -> Array ["exuberant", "destruction", "present"]

```

#### 16. reduce() :
The reduce() method is an iterative method. It runs a "reducer" callback function over all elements in the array, in ascending-index order, and accumulates them into a single value. Every time, the return value of callbackFn is passed into callbackFn again on next invocation as accumulator. The final value of accumulator becomes the return value of reduce().

The first time that the callback is run there is no "return value of the previous calculation". If supplied, an initial value may be used in its place. Otherwise the array element at index 0 is used as the initial value and iteration starts from the next element (index 1 instead of index 0).
```javascript
const array1 = [1, 2, 3, 4];

// 0 + 1 + 2 + 3 + 4
const initialValue = 0;
const sumWithInitial = array1.reduce((accumulator, currentValue) =>{
return accumulator + currentValue
} , initialValue);

console.log(sumWithInitial);
// output -> 10

```

#### 17. reduceRight() :
The reduceRight() method is an iterative method. It runs a "reducer" callback function over all elements in the array, in descending-index order, and accumulates them into a single value. Similar to reduce(), but starts from the last element and works towards the first. or we can say right to left.
```javascript
// below example for flat 2d array
const array1 = [
  [0, 1],
  [2, 3],
  [4, 5],
];

const result = array1.reduceRight((accumulator, currentValue) => accumulator.concat(currentValue));

console.log(result);
// output -> Array [4, 5, 2, 3, 0, 1]
```

#### 18. sort() :
The sort() method of Array instances sorts the elements of an array  and returns the reference to the same array, now sorted. The default sort order is ascending, built upon converting the elements into strings, then comparing their sequences of UTF-16 code units values.

The time and space complexity of the sort cannot be guaranteed as it depends on the implementation.
```js
const months = ['March', 'Jan', 'Feb', 'Dec'];
months.sort();
console.log(months);
// output -> Array ["Dec", "Feb", "Jan", "March"]

const array1 = [1, 30, 4, 21, 100000];
array1.sort();
console.log(array1);
// output -> Array [1, 100000, 21, 30, 4]
```
**Compare Function (Optional) :**

A function that defines the sort order. The return value should be a number whose sign indicates the relative order of the two elements: negative if a is less than b, positive if a is greater than b, and zero if they are equal. NaN is treated as 0. The function is called with the following arguments: 

`a` The first element for comparison. Will never be undefined.

`b`` The second element for comparison. Will never be undefined.

If compareFn is not supplied, all non-undefined array elements are sorted by converting them to strings and comparing strings in UTF-16 code units order. For example, "banana" comes before "cherry". In a numeric sort, 9 comes before 80, but because numbers are converted to strings, "80" comes before "9" in the Unicode order. All undefined elements are sorted to the end of the array.

```js
const stringArray = ["Blue", "Humpback", "Beluga"];
const numberArray = [40, 1, 5, 200];
const numericStringArray = ["80", "9", "700"];
const mixedNumericArray = ["80", "9", "700", 40, 1, 5, 200];

function compareNumbers(a, b) {
  return a - b;
}

stringArray.sort(); // ['Beluga', 'Blue', 'Humpback']

numberArray.sort(); // [1, 200, 40, 5]
numberArray.sort(compareNumbers); // [1, 5, 40, 200]

```

#### 19. reverse() :
The reverse() method of Array instances reverses an array and returns the reference to the same array, the first array element now becoming the last, and the last array element becoming the first. In other words, elements order in the array will be turned towards the direction opposite to that previously stated.
```js
const array1 = ['one', 'two', 'three'];
console.log('array1:', array1);
// Expected output: "array1:" Array ["one", "two", "three"]

const reversed = array1.reverse();
console.log('reversed:', reversed);
// Expected output: "reversed:" Array ["three", "two", "one"]

```
#### 20. every() :
The every() method of Array instances tests whether all elements in the array pass the test implemented by the provided function. It returns a Boolean value.
```js
const isBelowThreshold = (currentValue) => currentValue < 40;

const array1 = [1, 30, 39, 29, 10, 13];

console.log(array1.every(isBelowThreshold));
// Expected output: true
```
#### 21. some() :
The some() method of Array instances tests whether at least one element in the array passes the test implemented by the provided function. It returns true if, in the array, it finds an element for which the provided function returns true; otherwise it returns false. It doesn't modify the array.
```javascript
const array = [1, 2, 3, 4, 5];

// Checks whether an element is even
const even = (element) => element % 2 === 0;

console.log(array.some(even));
// Expected output: true

```

#### 22. join() :
The join() method of Array instances creates and returns a new string by concatenating all of the elements in this array, separated by commas or a specified separator string. If the array has only one item, then that item will be returned without using the separator.
```javascript
const elements = ['Fire', 'Air', 'Water'];

console.log(elements.join());
// Expected output: "Fire,Air,Water"

console.log(elements.join(''));
// Expected output: "FireAirWater"

console.log(elements.join('-'));
// Expected output: "Fire-Air-Water"
```
#### 23. toString() :
The toString() method of Array instances returns a string representing the specified array and its elements.

The Array object overrides the toString method of Object. The toString method of arrays calls join() internally, which joins the array and returns one string containing each array element separated by commas. If the join method is unavailable or is not a function, Object.prototype.toString is used instead, returning [object Array].

```javascript
const array1 = [1, 2, 'a', '1a'];

console.log(array1.toString());
// Expected output: "1,2,a,1a"
```

#### 24. isArray() :
The Array.isArray() static method determines whether the passed value is an Array. and returns true or false.

```javascript
console.log(Array.isArray([1, 3, 5]));
// Expected output: true

console.log(Array.isArray('[]'));
// Expected output: false

console.log(Array.isArray(new Array(5)));
// Expected output: true

console.log(Array.isArray(new Int16Array([15, 33])));
// Expected output: false

```
#### 25. fill() :
The fill() method of Array instances changes all elements within a range of indices in an array to a static value. It returns the modified array.
```javascript
fill(value, start, end)

const array1 = [1, 2, 3, 4];

// Fill with 0 from position 2 until position 4
console.log(array1.fill(0, 2, 4));
// Expected output: Array [1, 2, 0, 0]

// Fill with 5 from position 1
console.log(array1.fill(5, 1));
// Expected output: Array [1, 5, 5, 5]

console.log(array1.fill(6));
// Expected output: Array [6, 6, 6, 6]

```

#### 26. copyWithin() :
The copyWithin() method of Array instances shallow copies part of this array to another location in the same array and returns this array without modifying its length.

```javascript
copyWithin(target, start, end)

const array1 = ['a', 'b', 'c', 'd', 'e'];

// Copy to index 0 the element at index 3
console.log(array1.copyWithin(0, 3, 4));
// Expected output: Array ["d", "b", "c", "d", "e"]

// Copy to index 1 all elements from index 3 to the end
console.log(array1.copyWithin(1, 3));
// Expected output: Array ["d", "d", "e", "d", "e"]


```
#### 27. flat() :
he flat() method of Array instances creates a new array with all sub-array elements concatenated into it recursively up to the specified depth.
```javascript
const arr1 = [0, 1, 2, [3, 4]];

console.log(arr1.flat());
// Expected output: Array [0, 1, 2, 3, 4]

const arr2 = [0, 1, 2, [[[3, 4]]]];

console.log(arr2.flat(2));
// Expected output: Array [0, 1, 2, Array [3, 4]]
```

#### 28. flatMap() :

he flatMap() method of Array instances returns a new array formed by applying a given callback function to each element of the array, and then flattening the result by one level. It is identical to a map() followed by a flat() of depth 1 (arr.map(...args).flat()), but slightly more efficient than calling those two methods separately.

```javascript
const arr1 = [1, 2, 1];

const result = arr1.flatMap((num) => (num === 2 ? [2, 2] : 1));

console.log(result);
// Expected output: Array [1, 2, 2, 1]
```

#### 29. Array.at() :
The at() method of Array instances takes an integer value and returns the item at that index, allowing for positive and negative integers. Negative integers count back from the last item in the array.
```js
const array1 = [5, 12, 8, 130, 44];

let index = 2;

console.log(`Using an index of ${index} the item returned is ${array1.at(index)}`);
// Expected output: "Using an index of 2 the item returned is 8"

index = -2;

console.log(`Using an index of ${index} item returned is ${array1.at(index)}`);
// Expected output: "Using an index of -2 item returned is 130"
```
#### 30. Array.entries() :
The entries() method of Array instances returns a new array iterator object that contains the key/value pairs for each index in the array.
```js
const array1 = ['a', 'b', 'c'];

const iterator1 = array1.entries();

console.log(iterator1.next().value);
// Expected output: Array [0, "a"]

console.log(iterator1.next().value);
// Expected output: Array [1, "b"]

```
#### 31. Array.findLast() :
The findLast() method of Array instances iterates the array in reverse order and returns the value of the first element that satisfies the provided testing function. If no elements satisfy the testing function, undefined is returned.
```js
const array1 = [5, 12, 50, 130, 44];

const found = array1.findLast((element) => element > 45);

console.log(found);
// Expected output: 130

```
#### 32. Array.findLastIndex() :
The findLastIndex() method of Array instances iterates the array in reverse order and returns the index of the first element that satisfies the provided testing function. If no elements satisfy the testing function, -1 is returned.
```js
const array1 = [5, 12, 50, 130, 44];

const isLargeNumber = (element) => element > 45;

console.log(array1.findLastIndex(isLargeNumber));
// Expected output: 3
// Index of element with value: 130
```
#### 33. Array.from() :
The Array.from() static method creates a new, shallow-copied Array instance from an iterable or array-like object.
```js
console.log(Array.from('foo'));
// Expected output: Array ["f", "o", "o"]

console.log(Array.from([1, 2, 3], (x) => x + x));
// Expected output: Array [2, 4, 6]
```

#### 34. Array.of() :
The Array.of() static method creates a new Array instance from a variable number of arguments, regardless of number or type of the arguments.
```js

console.log(Array.of('foo', 2, 'bar', true));
// Expected output: Array ["foo", 2, "bar", true]

console.log(Array.of());
// Expected output: Array []

```

#### 35. Array.keys() :
The keys() method of Array instances returns a new array iterator object that contains the keys for each index in the array.
```js
const array1 = ['a', 'b', 'c'];
const iterator = array1.keys();

for (const key of iterator) {
  console.log(key);
}

// Expected output: 0
// Expected output: 1
// Expected output: 2
```


#### 36. Array.values() :
The values() method of Array instances returns a new array iterator object that iterates the value of each item in the array.
```js
const array1 = ['a', 'b', 'c'];
const iterator = array1.values();


for (const value of iterator) {
  console.log(value);
}

// Expected output: "a"
// Expected output: "b"
// Expected output: "c"

```

#### 36. Array.with() :
The with() method changes the value of a given index in the array, returning a new array with the element at the given index replaced with the given value. The original array is not modified. This allows you to chain array methods while doing manipulations.
```js
// arrayObject.with(index, value)
const arr = [1, 2, 3, 4, 5];
console.log(arr.with(2, 6)); // [1, 2, 6, 4, 5]
console.log(arr); // [1, 2, 3, 4, 5]
```


### New methods :
- Array.prototype.toLocaleString()
- Array.prototype.toReversed()
- Array.prototype.toSorted()
- Array.prototype.toSpliced()