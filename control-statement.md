# Conditional or Control statements 

A conditional statement is a set of commands that executes if a specified condition is true. JavaScript supports two conditional statements: if...else and switch.

### if...else statement
Use the if statement to execute a statement if a logical condition is true. Use the optional else clause to execute a statement if the condition is false.
An if statement looks like this:
```js
if (condition) {
  statement1;
} else {
  statement2;
}
```

If condition evaluates to true, statement_1 is executed. Otherwise, statement_2 is executed. statement_1 and statement_2 can be any statement, including further nested if statements.

You can also compound the statements using else if to have multiple conditions tested in sequence, as follows:

```js
if (condition1) {
  statement1;
} else if (condition2) {
  statement2;
} else if (conditionN) {
  statementN;
} else {
  statementLast;
}
```

### Falsy values
The following values evaluate to false (also known as Falsy values):

false
undefined
null
0
NaN
the empty string ("")
All other values—including all objects—evaluate to true when passed to a conditional statement.

### Switch Statement
A switch statement allows a program to evaluate an expression and attempt to match the expression's value to a case label. If a match is found, the program executes the associated statement.

A switch statement looks like this:

```js
switch (expression) {
  case label1:
    statements1;
    break;
  case label2:
    statements2;
    break;
  // …
  default:
    statementsDefault;
} 
```

JavaScript evaluates the above switch statement as follows:

- The program first looks for a case clause with a label matching the value of expression and then transfers control to that clause, executing the associated statements.
- If no matching label is found, the program looks for the optional default clause:
 - - If a default clause is found, the program transfers control to that clause, executing the associated statements.
 - - If no default clause is found, the program resumes execution at the statement following the end of switch.
 - - By convention, the default clause is written as the last clause, but it does not need to be so.


#### break statements :
The optional break statement associated with each case clause ensures that the program breaks out of switch once the matched statement is executed, and then continues execution at the statement following switch. If break is omitted, the program continues execution inside the switch statement (and will evaluate the next case, and so on).

### Exception handling statements : 
You can throw exceptions using the throw statement and handle them using the try...catch statements.

- - - throw statement
- - - try...catch statement

#### throw statement :
Use the throw statement to throw an exception. A throw statement specifies the value to be thrown.

You may throw any expression, not just expressions of a specific type. The following code throws several exceptions of varying types

```js
throw "Error2"; // String type
throw 42; // Number type
throw true; // Boolean type
throw {
  toString() {
    return "I'm an object!";
  },
};
```

#### try...catch statement : 
The try...catch statement marks a block of statements to try, and specifies one or more responses should an exception be thrown. If an exception is thrown, the try...catch statement catches it.

- The try...catch statement consists of a try block, which contains one or more statements, and a catch block, containing statements that specify what to do if an exception is thrown in the try block.

- In other words, you want the try block to succeed—but if it does not, you want control to pass to the catch block. If any statement within the try block (or in a function called from within the try block) throws an exception, control immediately shifts to the catch block. If no exception is thrown in the try block, the catch block is skipped. The finally block executes after the try and catch blocks execute but before the statements following the try...catch statement.

**Example :**

The following example uses a try...catch statement. The example calls a function that retrieves a month name from an array based on the value passed to the function. If the value does not correspond to a month number (1 – 12), an exception is thrown with the value 'InvalidMonthNo' and the statements in the catch block set the monthName variable to 'unknown'.

```js
function getMonthName(mo) {
  mo--; // Adjust month number for array index (so that 0 = Jan, 11 = Dec)
  const months = [
    "Jan", "Feb", "Mar", "Apr", "May", "Jun",
    "Jul", "Aug", "Sep", "Oct", "Nov", "Dec",
  ];
  if (months[mo]) {
    return months[mo];
  } else {
    throw new Error("InvalidMonthNo"); // throw keyword is used here
  }
}

try {
  // statements to try
  monthName = getMonthName(myMonth); // function could throw exception
} catch (e) {
  monthName = "unknown";
  logMyErrors(e); // pass exception object to error handler (i.e. your own function)
}
```

#### The finally block :
The finally block contains statements to be executed after the try and catch blocks execute. Additionally, the finally block executes before the code that follows the try…catch…finally statement.

It is also important to note that the finally block will execute whether or not an exception is thrown. If an exception is thrown, however, the statements in the finally block execute even if no catch block handles the exception that was thrown.
```js
openMyFile();
try {
  writeMyFile(theData); // This may throw an error
} catch (e) {
  handleError(e); // If an error occurred, handle it
} finally {
  closeMyFile(); // Always close the resource
}
```

If the finally block returns a value, this value becomes the return value of the entire try…catch…finally production, regardless of any return statements in the try and catch blocks.

```js
function f() {
  try {
    console.log(0);
    throw "bogus";
  } catch (e) {
    console.log(1);
    // This return statement is suspended
    // until finally block has completed
    return true;
    console.log(2); // not reachable
  } finally {
    console.log(3);
    return false; // overwrites the previous "return"
    console.log(4); // not reachable
  }
  // "return false" is executed now
  console.log(5); // not reachable
}
console.log(f()); // 0, 1, 3, false
```

Overwriting of return values by the finally block also applies to exceptions thrown or re-thrown inside of the catch block
```js
function f() {
  try {
    throw "bogus";
  } catch (e) {
    console.log('caught inner "bogus"');
    // This throw statement is suspended until
    // finally block has completed
    throw e;
  } finally {
    return false; // overwrites the previous "throw"
  }
  // "return false" is executed now
}

try {
  console.log(f());
} catch (e) {
  // this is never reached!
  // while f() executes, the `finally` block returns false,
  // which overwrites the `throw` inside the above `catch`
  console.log('caught outer "bogus"');
}

// Logs: ->
// caught inner "bogus"
// false
```


**Nesting try...catch statements :**

You can nest one or more try...catch statements.

If an inner try block does not have a corresponding catch block:

- it must contain a finally block, and
- the enclosing try...catch statement's catch block is checked for a match.