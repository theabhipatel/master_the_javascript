# How JavaScript Exicutes.
---

as soon as the whole js program is run then the global execution context is created.

It has two components memory & code and it is created in two phases.

### phase 1 : Memory Creation Phase -

in the memory creation phase we are allocation memroy to all the variables and functions inside the global space. for variables it will allocate undefined. and for functions it will allocate the whole function on we can say the defination of function.

### phase 2 : Code Execution Phase - 

after the creation of memory now js engine  start executing  the code line by line in global execution context. so whenever its find variable then it will asign the value of a variable in memory, which was by now undefined. when it goes where the function invoke or we can say that when any function invoke again a execution context created and again there 2 phases will happen. 
 #### 1 : memory creation 
 #### 2 :  code execution 

now memory allocation same as we are discussed already. and in code execution phase again the value of parameters or variable assign to the variables in the memory  and the all calculation(execution ) happens. after that the 
`return keyword` tells his function that you are done with your task or work now just return the whole control back to the place where the function invoked. 

and now assign the value  which was returned by the function to the variable in the memory where was perviously stored the undefined. 

now the execution context which was created by the function will destroyed. and in global execution context execution will move on next line to be executed. 

if any function will invoke in another function, it will again create a execution context inside the execution context of the it's parent function. and after all execution will over then the global execution context also destroyed. 

whenever an execution context is created. it is pushed into the call stack and whenever an execution context is deleted it will poped out fo the call stack. after the whole thing is executed the call stack gets empty.

* call stack maintains the order of exection of the execution context
##### Call Stack also known as - 
 - Execution context stack 
 - Program stack
 - Cntrol stack
 - Runtime stack
 - Machine stack

 * memory creation phase also know as varibale environment. 

* whenever js code executes it will create Global Execution context then it will pushed into the Call Stack.


## what is window : 
 window is a actually global object which is created along with the GEC. So whenever any js program is runs a global object abd GEC is created and alog with that GEC a `this` variable is created . and this keyword represent that Global object. 

 ### Global Space : 

 any thing which is not inside the function is the global space.


 #### Undefined vs Not defined :
In case of undefined memory is allocated to any variable but it has not been assigned any value yet.
but in the case of not defined memory is not allocated to that variable.

#### Lexical environment :
 lexical environment is the local memory along with the lexical environment of its parent.
  




