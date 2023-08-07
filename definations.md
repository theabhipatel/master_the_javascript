# Definations
These are the some defination of javaScript which is freqently asked in interviews.


### Q. What is temporal dead zone
temporal dead zone is the time since when this let and const variable was hoisted and till it is intialized some value. thee time between that is known as the temporal dead zone. - whenever we declair variable using var it will attach to the global object during memory creation phase but let and const not attached to the global object these are attached in temporal dead zone.

### Q. what is block in js
block is nothing but the curely bracet  
ex.- {}
- block is wrapping multiple statement of code,

### Q. What is closure
function along whit its lexical scope  that's know as a closure. or we can say function along with its lexical scope bundle togather form a closure. and the simplest manner - function with it's scope called closure. 
#### uses of closure : 
 - module design pattern
 - currying 
 - function like once
 - memoize
 - maintaining state in async world
 - iterators

 #### Disadvantages of closure :
 - when clouser is created many time, then its leads to heavy memory consumption and also memory can leak and browser freezes.

 ### Q. Function statement
 when we write a normal function its called function statement and aslo known as function declaration.

 ### Q. Anonymous function 
 when we create function without its name called anonymous function. it does not have its own identity and if we create  normally an anonymous function it will result out to be a syntax error, because a function statement should always have a name.

 ### Q. What is the use of an Anonymous function 
 anonymous function are used in a place where function are used as values it mean we can use it to assign it to any variables or pass into arguments of any function.

 ### Q. Function expression
 when we create an anonymous function and assigned it to the variable its called function expression.

### Q. Difference between function statement and expression 
when the EC created first happen the memory creation phase in this phase function statement assign the whole defination on function to the memory it means function has allocated memory and assigned its defination, but when we use function expression it has variable so it will be treated like varibale not like function and in the memory creation phase the variable will be assigned undefined not the function defination.


### Q. Named function 
when we assign a normal function to a varibale without anonymous function then its called named function .

### Q. Parameters vs Arguments
the label or identifier which gets values are known as parametes of we can say whenever we deifne a function and pass value to the parenthisis that called paameters and the parameters are the local variables for the function
the values which we pass inside a function where we invoke funtions are known as Arguments


### Q. First class functions
the ability of function to be used as values and can be pass it as argument to another  and can be returend from the functions. this ability is konwn as first class functions in javascript . this ability all together iis known as first class functions.

- js is a syncronous single threated landguage.
- call stack is main thread.





