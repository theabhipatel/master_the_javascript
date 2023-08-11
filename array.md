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

9. lastIndexOf()
The lastIndexOf() method of Array instances returns the last index at which a given element can be found in the array, or -1 if it is not present. The array is searched from backwards, 
```javascript
const animals = ['Parrot', 'Tiger', 'Penguin', 'Parrot'];

console.log(animals.lastIndexOf('Parrot'));
// output -> 3

console.log(animals.lastIndexOf('Tiger'));
// output -> 1

```

10. includes()
The includes() method of Array Determines whether an array contains a certain element or not, returning true or false. it is works only in premetive data type.  
```javascript
const array1 = [1, 2, 3];

console.log(array1.includes(2));
// output -> true

console.log(array1.includes(4));
// output -> false
```

11. find()
The find() method of Array instances returns the first element in the provided array that satisfies the provided testing function. If no values satisfy the testing function, undefined is returned.

```javascript
const array1 = [5, 12, 8, 130, 44];

const found = array1.find((element) => element > 10);

console.log(found);
// output -> 12

```

12. findIndex()
The findIndex() method of Array instances returns the index of the first element in an array that satisfies the provided testing function. If no elements satisfy the testing function, -1 is returned.
```javascript
const array1 = [5, 12, 8, 130, 44];

const isLargeNumber = (element) => element > 13;

console.log(array1.findIndex(isLargeNumber));
// output -> 3

```

13. forEach()
The forEach() method is an iterative method. It calls a provided callbackFn function once for each element in an array in ascending-index order.  forEach() always returns undefined and that's why it is not chainable. it modifies the original array.
```javascript
const array1 = [1,2,3];

array1.forEach((element, index, array) => console.log(element +1));
// output -> 2
// output -> 3
// output -> 4
```

14. map()
The map() method is an iterative method. It calls a provided callbackFn function once for each element in an array and constructs a new array from the results.
```javascript
const array1 = [1, 4, 9, 16];

// Pass a function to map
const map1 = array1.map((x) => x * 2);

console.log(map1);
// output -> Array [2, 8, 18, 32]
```

15. filter()
The filter() method is an iterative method. It calls a provided callbackFn function once for each element in an array, and constructs a new array of all the values for which callbackFn returns a truthy value. Array elements which do not pass the callbackFn test are not included in the new array.
```javascript
const words = ['spray', 'limit', 'elite', 'exuberant', 'destruction', 'present'];

const result = words.filter((word) => word.length > 6);

console.log(result);
// Expected output: Array ["exuberant", "destruction", "present"]

```

16. reduce()
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
// Expected output: 10

```

17. reduceRight()
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
// Expected output: Array [4, 5, 2, 3, 0, 1]
```

18. sort()
Sorts the elements of an array in place and returns the sorted array.
```javascript

```
19. reverse()
Reverses the order of the elements in an array in place.
```javascript

```
20. every()
Checks if all elements in an array pass a provided testing function.
```javascript

```
21. some()
Checks if at least one element in an array passes a provided testing function.
```javascript

```
22. join()
Joins all elements of an array into a string.
```javascript

```
23. toString()
Returns a string representation of an array.
```javascript

```
24. isArray()
Checks if a given value is an array.
```javascript

```
25. fill()
Changes all elements in an array to a specified value.
```javascript

```
26. copyWithin()
Copies a sequence of array elements within the array to a specified position.
```javascript

```
27. flat()
Creates a new array with all sub-array elements concatenated into it recursively.
```javascript

```
28. flatMap()
Maps each element using a mapping function, then flattens the result into a new array.
```javascript

```