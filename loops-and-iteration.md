# Loops and iteration
Loops offer a quick and easy way to do something repeatedly.


**Overview Loops and iteration :** 

- There are many different kinds of loops, but they all essentially do the same thing: they repeat an action some number of times. (Note that it's possible that number could be zero!)

- The various loop mechanisms offer different ways to determine the start and end points of the loop. There are various situations that are more easily served by one type of loop over the others.

The statements for loops provided in JavaScript are:

- for statement
- while statement
- do...while statement
- labeled statement
- break statement
- continue statement
- for...in statement
- for...of statement


### for statement :
A for loop repeats until a specified condition evaluates to false. The JavaScript for loop is similar to the Java and C for loop.

A for statement looks as follows:

```js
for (initialization; condition; afterthought){
    statement
}
```

**When a for loop executes, the following occurs :**

1. The initializing expression initialization, if any, is executed. This expression usually initializes one or more loop counters, but the syntax allows an expression of any degree of complexity. This expression can also declare variables.

2. The condition expression is evaluated. If the value of condition is true, the loop statements execute. Otherwise, the for loop terminates. (If the condition expression is omitted entirely, the condition is assumed to be true.)

3. The statement executes. To execute multiple statements, use a block statement ({ }) to group those statements.
4. If present, the update expression afterthought is executed.
5. Control returns to Step 2.

**Example :**
```js
for (let i = 1; i <= 5; i++) {
  console.log("Count: " + i);
}
// output :
// Count: 1
// Count: 2
// Count: 3
// Count: 4
// Count: 5
```

### while statement
A while statement executes its statements as long as a specified condition evaluates to true. A while statement looks as follows:

```js
while (condition){
    statement
}
```

- If the condition becomes false, statement within the loop stops executing and control passes to the statement following the loop.

- The condition test occurs before statement in the loop is executed. If the condition returns true, statement is executed and the condition is tested again. If the condition returns false, execution stops, and control is passed to the statement following while.

- if the condition returns initially `false` then it will never be executed.

- Avoid infinite loops. Make sure the condition in a loop eventually becomes false—otherwise, the loop will never terminate.

**Example :**
The following while loop iterates as long as n is less than 3.
```js
let n = 0;
let x = 0;
while (n < 3) {
  n++;
  x += n;
}
```

### do...while statement
The do...while statement repeats until a specified condition evaluates to false.

A do...while statement looks as follows:

```js
do{
  statement
}
while (condition);
```

- statement is always executed once before the condition is checked. (To execute multiple statements, use a block statement ({ }) to group those statements.)

- If condition is true, the statement executes again. At the end of every execution, the condition is checked. When the condition is false, execution stops, and control passes to the statement following do...while.

**Example : **
In the following example, the do loop iterates at least once and reiterates until i is no longer less than 5.

```js
let i = 0;
do {
  i += 1;
  console.log(i);
} while (i < 5);
```

### labeled statement :
A label provides a statement with an identifier that lets you refer to it elsewhere in your program. For example, you can use a label to identify a loop, and then use the break or continue statements to indicate whether a program should interrupt the loop or continue its execution.

The syntax of the labeled statement looks like the following :

```js 
label:
  statement
```


- The value of label may be any JavaScript identifier that is not a reserved word. The statement that you identify with a label may be any statement. For examples of using labeled statements, see the examples of break and continue below.


### break statement : 
Use the break statement to terminate a loop, switch, or in conjunction with a labeled statement.

- When you use break without a label, it terminates the innermost enclosing while, do-while, for, or switch immediately and transfers control to the following statement.
- When you use break with a label, it terminates the specified labeled statement.

The syntax of the break statement looks like this : 
```js
break;
break label;
```
1. The first form of the syntax terminates the innermost enclosing loop or switch.
2. The second form of the syntax terminates the specified enclosing labeled statement.

**Example :**

The following example iterates through the elements in an array until it finds the index of an element whose value is theValue :
```js
for (let i = 0; i < a.length; i++) {
  if (a[i] === theValue) {
    break;
  }
}
```
Breaking to a label :

```js
let x = 0;
let z = 0;
labelCancelLoops: while (true) {
  console.log("Outer loops:", x);
  x += 1;
  z = 1;
  while (true) {
    console.log("Inner loops:", z);
    z += 1;
    if (z === 10 && x === 10) {
      break labelCancelLoops;
    } else if (z === 10) {
      break;
    }
  }
}
```

### continue statement : 
The continue statement can be used to restart a while, do-while, for, or label statement.

- When you use continue without a label, it terminates the current iteration of the innermost enclosing while, do-while, or for statement and continues execution of the loop with the next iteration. In contrast to the break statement, continue does not terminate the execution of the loop entirely. In a while loop, it jumps back to the condition. In a for loop, it jumps to the increment-expression.
- When you use continue with a label, it applies to the looping statement identified with that label.

The syntax of the continue statement looks like the following :
```js
continue;
continue label;
```

**Example :**

Example 1 :

The following example shows a while loop with a continue statement that executes when the value of i is 3. Thus, n takes on the values 1, 3, 7, and 12.

If you comment out the continue;, the loop would run till the end and you would see 1,3,6,10,15.

```js
let i = 0;
let n = 0;
while (i < 5) {
  i++;
  if (i === 3) {
    continue;
  }
  n += i;
  console.log(n);
}
// Logs:
// 1 3 7 12
```

Example 2 : 

A statement labeled checkiandj contains a statement labeled checkj. If continue is encountered, the program terminates the current iteration of checkj and begins the next iteration. Each time continue is encountered, checkj reiterates until its condition returns false. When false is returned, the remainder of the checkiandj statement is completed, and checkiandj reiterates until its condition returns false. When false is returned, the program continues at the statement following checkiandj.

If continue had a label of checkiandj, the program would continue at the top of the checkiandj statement.

```js 
let i = 0;
let j = 10;
checkiandj: while (i < 4) {
  console.log(i);
  i += 1;
  checkj: while (j > 4) {
    console.log(j);
    j -= 1;
    if (j % 2 === 0) {
      continue checkj;
    }
    console.log(j, "is odd.");
  }
  console.log("i =", i);
  console.log("j =", j);
}
```

### for...in statement : 
The for...in statement iterates a specified variable over all the enumerable properties of an object. For each distinct property, JavaScript executes the specified statements. 

A for...in statement looks as follows
```js
for (variable in object){
    statement
}
```
**Example :**

The following function takes as its argument an object and the object's name. It then iterates over all the object's properties and returns a string that lists the property names and their values.

```js
function dumpProps(obj, objName) {
  let result = "";
  for (const i in obj) {
    result += `${objName}.${i} = ${obj[i]}<br>`;
  }
  result += "<hr>";
  return result;
}
```


### for...of statement : 
The for...of statement creates a loop Iterating over iterable objects (including Array, Map, Set, arguments object and so on), invoking a custom iteration hook with statements to be executed for the value of each distinct property.

```js
for (variable of object){
statement
}
```

The following example shows the difference between a for...of loop and a for...in loop. While for...in iterates over property names, for...of iterates over property values:

```js
const arr = [3, 5, 7];
arr.foo = "hello";

for (const i in arr) {
  console.log(i);
}
// "0" "1" "2" "foo"

for (const i of arr) {
  console.log(i);
}
// Logs: 3 5 7
```

- The for...of and for...in statements can also be used with destructuring. For example, you can simultaneously loop over the keys and values of an object using Object.entries().

```js
const obj = { foo: 1, bar: 2 };

for (const [key, val] of Object.entries(obj)) {
  console.log(key, val);
}
// "foo" 1
// "bar" 2
```