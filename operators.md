# Operators in JS 
JavaScript **operators** operate the operands, these are symbols that are used to manipulate a certain value or operand. Operators are used to performing specific mathematical and logical computations on operands. In other words, we can say that an operator operates the operands. In JavaScript, operators are used to compare values, perform arithmetic operations, etc.

- Operators in JavaScript are symbols that perform operations on operands (values or variables). They allow you to manipulate, compare, and combine values in your code. 

- These operators are fundamental for writing expressions and manipulating data in JavaScript. They allow you to create more complex behavior and calculations within your code.

**JavaScript Operators :** There are various operators supported by JavaScript.

1. JS Arithmetic Operators
2. JS Assignment Operators
3. JS Comparison Operators
4. JS Logical Operators
5. JS String Operators
6. JS Ternary Operators
7. JS Bitwise Operators
8. JS typeof Operator


### # 1. Arithmetic Operators :
 These are the operators that operate upon the numerical values and return a numerical value.

| Operator |	Description |
| -------- | ---------------|
| + |	Addition |
| -  |	Subtraction |
| *  |	Multiplication |
| **  |	Exponentiation  (ES2016) |
| /  |	Division |
| %  |	Modulus  (Division Remainder) |
| ++  |	Increment |
| --  |	Decrement |
| +a | Unary |
| -a | Negation |

**1. Addition (+) :**  
Addition ‘+’ operator performs addition on two operands. This ‘+’ operator can also be used to concatenate (add) strings.
```js
Y = 5 + 5 gives Y = 10
Y = "Hello" + "for" + "World" 
// gives Y = "HelloforWorld"
Y = "Hello" + 4 + "World" 
// gives Y = "Hello4World"
```


**2. Subtraction (-) :**  
Subtraction ‘-‘ operator performs subtraction on two operands.
```js
Y = 5 - 3 gives Y = 2 
```

**3. Multiplication (*) :**  
Multiplication ‘*’ operator performs multiplication on two operands.
```js
Y = 5 * 5 gives Y = 25
```

**4. Division (/) :**  
Division ‘/’ operator performs division on two operands (divide the numerator by the denominator).
```js
Y = 5 / 5 gives Y = 1
``` 

**5. Modulus (%) :**  
Modulus ‘%’ operator gives a remainder of an integer division. 
```js
// A % B means remainder (A/B)
Y = 5 % 4  // gives Y = 1
```


**6. Exponentiation (**) :**  
Exponentiation ‘**’ operator give the power of the first operator raised to the second operator.
```js
Y = 5 ** 3 gives Y = 125
```

**7. Increment(++) :**  
Increment ‘+ +’ operator increases an integer value by one. 
```js
let A = 10 and Y = A + + then A = 11, Y=10
if A = 10 and Y = + + A then A = 11, Y=11
```


**8. Decrement (- -) :**  
Decrement ‘- -‘ operator decreases an integer value by one.
```js
let A = 10 and Y = A - - then A = 9, Y=10
if A = 10 and Y = - - A then A = 9, Y=9
```

**9. Unary (+) :**  
Unary ‘+’ is the fastest and preferred way of converting something into a number
+a means a is a  number
```js
let a = "45";
console.log(+a); // 45
console.log(typeof +a); // number
```

**10. Negation (-) :**  
Negation ‘-‘ operator gives the negation of an operand.
-a means a is a negative number

Example: In this example we will use all assignment operators.

```js
// Addition Operator
let a = 1 + 2
console.log(a); // 3

  
// Subtraction Operator
let b = 10 - 7
console.log(b); // 3

  
// Multiplication Operator
let c = 3 * 3
console.log(c); // 9

  
// Division Operator
let d = 1.0 / 2.0
console.log(d); // 0.5

  
// Modulas Operator
let e = 9 % 5
console.log(e) // 4

  
// Exponentian Operator
let f = 2 ** 5
console.log(f) // 32

  
// Increment Operator
let g = 2;
g1 = g++;
console.log(g) // 3

  
// Decrement Operator
let h = 2;
h1 = h--;
console.log(h) // 1

  
// Unary plus Operator
let i = '3';
i1 = +i;
console.log(i1) // 3

  
// Negation Operator
let j = 3;
j1 = -j;
console.log(j1) // -3
```

 --- ----------------------

###  # 2. Assignment Operators: 
The assignment operation evaluates the assigned value. Chaining the assignment operator is possible in order to assign a single value to multiple variables

| Operator |	Example	| Same As  |
|--------- | --------- | -------- |
| =  |	x = y |	x = y |
| += |	x += y |	x = x + y |
| -= |	x -= y |	x = x - y |
| *= |	x *= y |	x = x * y |
| /= |	x /= y |	x = x / y |
| %= |	x %= y |	x = x % y |
| **= |	x **= y |	x = x ** y |

1. **Assignment (=) :**  
This operator assigns the right operand value to the left operand.
 ```js 
 If A = 10 and Y = A then Y = 10
 ```

2. **Addition Assignment (+=) :**  
 Sums up left and right operand values and then assigns the result to the left operand.;
 ```js
Y += 1 gives Y = Y + 1 
 ```

3. **Subtraction Assignment (- =) :**  
 It subtracts the right side value from the left side value and then assigns the result to the left operand. 
 ```js
Y -= 1 gives Y = Y - 1 
 ```

4. **Multiplication Assignment (*=):**  
 It multiplies a variable by the value of the right operand and assigns the result to the variable.
 ```js
Y *= A is equivalent to Y = Y * A
 ```

5. **Division Assignment (/ =) :**  
 It divides a variable by the value of the right operand and assigns the result to the variable.
 ```js
Y /= A is equivalent to Y = Y / A
 ```

6. **Modules/Remainder Assignment (% =) :**   
It divides a variable by the value of the right operand and assigns the remainder to the variable.
```js
Y %= A is equivalent to Y = Y % A
```

7. **Exponentiation Assignment (** =) :**   
This raises the value of a variable to the power of the right operand.
```js
Y **= A is equivalent to Y=Y ** A
```

8. **Left Shift Assignment (<< =) :**  
 It moves the specified amount of bits to the left and assigns the result to the variable.
 ```js
Y <<= A is equivalent to Y=Y << A
 ```

9. **Right Shift Assignment (>> =) :**  
 It moves the specified amount of bits to the right and assigns the result to the variable.
```js
Y >>= A is equivalent to Y = Y >> A
``` 

10. **Bitwise AND Assignment (& =) :**  
 It does a bitwise AND operation on the operand, and assigns the result to the variable.
```js
Y &= b is equivalent to Y = Y & A
```

11. **Bitwise OR Assignment (| =) :**  
 It does a bitwise OR operation on the operand, and assigns the result to the variable.
```js
Y |= A is equivalent to Y= Y | b
```

12. **Bitwise XOR Assignment (^ =) :**  
 It does a bitwise XOR operation on the operand, and assigns the result to the variable.
```js
 Y ^= A is equivalent to Y= Y ^ A
```

Example: In this example, we will use all assignment operators.

```js 
    // Assignment Operator
    let a = 2;
    console.log(a); // 2
      
    // Addition Assignment Operator
    const b= 3;
    console.log(a = b + 1); // 4
       
    // Subtraction Assignment Operator
    let yoo=4;
    console.log(foo=yoo-1); // 3
      
    // Multiplication Assignment 
    console.log(yoo=yoo*2);  // 8
 
    // Division Assignment Operator
    const moo=2;
    console.log(yoo=yoo/moo); // 4    
       
    // Modulas Assignment Operator
    console.log(yoo%=2); // 0
      
    // Exponentian Assignment Operator
    console.log(yoo**moo); // 0
      
    // Left Shift Assignment
    console.log(yoo<<=2); // 0
      
    // Right Shift Assignment
    console.log(yoo>>=2); // 0
       
    // Bitwise AND Assignment
    console.log(yoo&=2); // 0
       
    // Bitwise OR Assignment
    console.log(yoo|=2); // 2
      
    // Bitwise XOR Assignment
    console.log(yoo^=2); // 0
```
---
<!-- ------------------------------------------ -->

### # 3. Comparison Operators :
 Comparison operators are mainly used to perform the logical operations that determine the equality or difference between the values.

| Operator | 	Description |
| - | - |
| == |	equal to |
| === |	equal value and equal type |
| != |	not equal |
| !== |	not equal value or not equal type |
| > |	greater than |
| < |	less than |
| >= |	greater than or equal to |
| <= |	less than or equal to |
| ? |	ternary operator |

1. **Equality (==) :**  
 Compares the equality of two operands. If equal then the condition is true otherwise false.
 ```js
 Y = 5 and X = 6
Y = = X is false.

 ```

2. **Strict equality (===):**  
 Compares the equality of two operands with type. If both value and type are equal then the condition is true otherwise false.
 ```js
 Y = 5 and X = '5'
Y = = = X is false.
 ```

3. **Inequality (!=) :**  
  Compares inequality of two operands. True if operands are not equal. 
  ```js
    let X = 10 then X ! = 11 is true. 
  ```

4. **Strict inequality(!==) :**  
 Compares the inequality of two operands with type. If both value and type are equal then the condition is true otherwise false.
 ```js
let X = 10 then X ! == '10' is true. 
 ```

5. **Greater than (>) :**  
  This operator checks whether the left side value is greater than the right side value. If yes then it returns true otherwise it returns false. 
  ```js
    let X = 10 then X > 11 is false. 
  ```

6. **Less than (<) :**  
 This operator checks whether the left side value is less than the right side value. If yes then it returns true otherwise it returns false. 
 ```js
    let X = 10 then X < 11 is true. 
 ```

7. **Greater than or Equal to (> =) :**  
 This operator checks whether the left side operand is greater than or equal to the right side operand. If yes then it returns true otherwise it returns false. 
 ```js
    let X = 10 then X > = 11 is false. 
 ```

8. **Less than or Equal to (<= ) :**  
 This operator checks whether the left side operand value is less than or equal to the right side operand value. If yes then it returns true otherwise it returns false.
 ```js
    let X = 10 then X < = 10 is true. 
 ``` 

Example: In this example, we will use all comparison operators.

```js
// Assigning values
    let val1 = 5;
    let val2 = 5;
    // Equality Operator
    console.log(val1 == val2); //   true
  
    // Strict equality Operator
    console.log(val1 === val2); // true
  
    // Inequality Operator
    console.log(val1 != val2); // false
  
    // Strict Inequality Operator
    console.log(val1 !== val2); // false
  
    // Greater than Operator
    console.log(val1 > val2); // false
  
    // Greater than or equal Operator
    console.log(val1 >= val2); // true
  
    // Less than Operator
    console.log(val1 < val2); // false
  
    // Less than or equal Operator
    console.log(val1 <= val2); // true

```

----------------------------------
<!-- ---------------------------------- -->

## # 4. Logical Operators :
 These operators are used to determine the logic between variables or values.
 
| Operator |	Description |
| --- | ---- |
| && |	logical and |
| \|\| |	logical or |
| !	 | logical not |

1. **Logical AND (&&) :**  
 It checks whether two operands are non-zero (0, false, undefined, null, or “” are considered as zero), if yes then return the last operand when evaluating from left to right. 
 ```js 
 Y = 5 and X = 6
Y && X is 6.
 ```


2. **Logical OR (||) :**  
 It checks whether two operands are non-zero (0, false, undefined, null, or “” is considered as zero), if yes then return the first operand when evaluating from left to right. 
 ```js
 Y = 5 and X = 0
Y || X is 5.
 ```


3. **Logical NOT (!) :**  
 It reverses the boolean result of the operand (or condition). 
 ```js 
 Y = 5 and X = 0
!(Y || X) is false.
 ```


Example: In this example, we will use all logical operators.

```js
 // Assigning values
    let val1 = 5;
    let val2 = 5;
      
    // Logical !(NOT) Operator
    console.log(!val2); // false

  
    // Logical &&(AND) Operator
    console.log( val1 && val2 ); // 5

      
    // Lgical ||(OR) Operator
    console.log( val1 || val2 ); // 5

```

### # 5. String Operator : 


**Concatenation (+) :**  
The + can also be used to add (concatenate) strings 
```js
let text1 = "John";
let text2 = "Doe";
let text3 = text1 + " " + text2;
```
The += assignment operator can also be used to add (concatenate) strings 
```js 
let text1 = "What a very ";
text1 += "nice day";
// output : "What a very nice day"
```

### # 5.  Bitwise Operator: 
The bitwise operator in JavaScript is used to convert the number to a 32-bit binary number and perform the bitwise operation. The number is converted back to the 64-bit number after the result. 
| Operator | Discription |
| --- | --- |
| & Bitwise AND |
| \|  | Bitwise OR |
| ^ | Bitwise XOR |
| ~ | Bitwise NOT |
| << | Left shift |
| >> | Right shift |
| >>> | Unsigned right shift |


### # 6. Ternary Operator :
 The ternary operator has three operands. It is the simplified operator of if/else.

**Ternary Operator(?) :** It is like the short form of the if-else condition. 
```js
Y =  ? A : B
If the condition is true then Y = A otherwise Y = B
```


Example: In this example, we will use the ternary operator.
```js
    // Assigning values
    let PMarks = 40
      
    // Ternary Operator
    let result = (PMarks > 39)?
        "Pass":"Fail";
   
    console.log(result); // Pass
```

---
<!-- ------------------------------------ -->


### # 7. JavaScript typeof Operator : 
It returns the data type of its operand in the form of a string. The operand can be any object, function, or variable.

| Operator |	Description |
|- |- |
| typeof |	Returns the type of a variable |
| instanceof |	Returns true if an object is an instance of an object type |

**typeof :** It returns the operand type, The possible types that exist in javascript are undefined, Object, boolean, number, string, symbol, and function.

typeof variable;

Example: In this example, we will use typeof operator.
```js
 let a = 17;
    let b = "GeeksforGeeks";
    let c = "";
    let d = null;
      
    console.log("Type of a = " + (typeof a)); //  Type of a = number
    console.log("Type of b = " + (typeof b)); // Type of b = string
    console.log("Type of c = " + (typeof c)); // Type of c = string
    console.log("Type of d = " + (typeof d)); // Type of d = object
    console.log("Type of e = " + (typeof e)); // Type of e = undefined
```




