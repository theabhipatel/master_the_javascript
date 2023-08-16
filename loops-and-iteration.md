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
