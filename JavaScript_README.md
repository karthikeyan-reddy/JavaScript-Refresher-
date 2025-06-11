# JavaScript-Refresher

## What is Javascript ? 
  Js is a loosely typed, object oriented programming Language Managed by ECMA international and supported by all modren Browsers. <br />
  Latest Version of support by all browsers: ES2023+ / ES6 +  <br />
      <li> ECMAScript 2016 --> ES6 is advanced and growing. </li>
  <br />
  The process of Converting one version of code to another version example; ES6 to ES5 is known as transpiling. Babel is one such transpiler. 
  ### Why JS?
    * widely used in Web Development.
    * Has a large community.
    * Has many ready to use libraries for quicker development.
    * Supports Object Oriented Programming.
## How to Declare Variables and differences ? 
  we can declare variables in 3 different ways : 
  * var
  * let
  * const
  ```
     * var: used for Functional Scope, allows re-initializing the variable with same name and the value can be modified later. 
     * let: used for block level scope, restricts re-initializing the variable with same name and can be modified later. 
     * const: used for block level scope, restricts re-initializing and value cannot be changed after declaration.
```

**Note: <ins> let, const are introduce in 2015 ES6. </ins>**

## What are different Data Types and Finding Types in JS ? 
  ### Data Types: 
    1. Number: Any integer, decimal , float and double digits.
    2. String: A character literal or group of characters.  
    3. Object: Special datatype which can store different data type values into a one segment.  
    4. Boolean: truthy values (true or false). 
    5. Array: same as object but stores the order and has some special features. (Note: key is autoassigned and we call it as index)
    6. null:Used to represent No-Value or claer the variable refereces. 
    7. undefined: similar to null, but these are used when the variable is declared but not initialized.

  **Null and undefined looks same but, null is an object, whereas undefined is a type. loose equality(==) returns `true` as both has no value. but strict equality(===) returns `false`**

### Loose and strict Equality Operators in JS. 
  * `==` is known as loose equality operators. It can type cast and compares the values.
  * `===` is known as strict equality operator. It will compares the values but doesn't type cast them.
    
**Example:**
    ` 1 == '1' --> returns true . Here '1' is a string and 1 is a number, but == converted the string to number and compared the value.
    In same scenario, 1 === '1' returns false, as we are comparing two different data types. `

### How to Find the data type of a declared or passed variable? 
  `typeof` is a keyword which determines the data type of a variable declared. 

  ### Fun-Stuff
    1. typeof(1) //returns number 
    2. typeof(typeof(1)) //return string
    3. typeof(null) //returns object 
    4. typeof(typeof(null)) //??? ~~returns what, try Out~~
  ![image](https://github.com/user-attachments/assets/2c7b5002-6516-4254-ab72-e12dde0e6560)

    
## Conditional Statements in JS 
  conditional statements are used to determine whether an expression is correct or not and determines what to perform based on the result. 
  Example: assume if a number is divisible by 2 i should print Even, if not i should print Odd. (Let's use this later)
  
  Available Conditional Statements:

1. if: checking whether the condition is true or not and if correct when performing the commands inside the block. 
   ```
   var num = 2 ;
   if(num == 2) {console.log("Yay!! number is 2") ;
   ```
   
2. else-if: Checks for the condtions which are specified, if nothing matches else block will be executed. 
      ```var num = 1; 
       if(num === 1){console.log("Number is: 1");
       else if(num === 2) {console.log("Number is: 2"); 
       else{ console.log("idk"); }```
   
3. switch: 1 issue with else if's is it goes sequentially and checks each condition if fails goes for next, sometimes it would be not ideal, so in that case we can opt switch which is verbose and checks the condition and jumps into that block with out checking all.
   ```
     switch(num) {
        case 1: console.log(1); break; 
        case 2: console.log(2); break; 
        default: console.log("idk"); break; 
      }
   ```
   
    **break is an important keyword, whiuch terminated the block.**

4. Ternary if's: modren way of writing an if else condition, works similar to regular if-self but looks compact and clean. <br />
   ```
    num == 1 ? console.log("1") : console.log("idk") ; // here the statement after ? runs when the condition is true.
                                                        if not the code block after : will run. 
   ```
## Loop / Iterative Statements in JS.

   Loops are used to go through the same block of code or do the similar work until a condition fails. 

   why loops: loops promotes reusability, meaning instead of writing same code multiple times for the similar results we can use this. 

   Available LOOPS: 
   1. for
   2. for in (forEach)
   3. while
   4. do - while

#### for Loop:
```
  // 1. When we want to run a block of code repeatedly until a condition is met.
  // 2. Here the variable declaration , condition and variable updation happens at 1 place.
  // 3. When condition is known or iterations are known this is best and effective.

  Syntax:
    for(let i= 0; i< 10 ; i++){ console.log(i);}
  // let i = 0; declaration.
  // i<10 Condition
  // i++ value updation.  
```
#### for in 
```
// for in loop is used when we want to iterate through an object not depending on any condition and no indexation is required.
  Syntax:
  let nums = [1,2,3]; 
  for(var num in nums){console.log(nums[num])};
```
#### while loop 
```
// similar to for loop in terms of concept, but the variable declaration happens before the loop and updation happens inside the loop. \
// Best for when number of iterations are unknown and indexation is not a priority.
  Syntax:
  let i = 0 ;
  while(i < 10) {
    console.log(i);
    i++; // if we miss this, loop runs for infinite number of times. (Infinite Loop)
}
```
#### do-while 
```
// Same as while, but has an additional block called do which runs atleast once irrespective of the condition.
Syntax:
let i = 0;
do{console.log(i};while(i<10) ; 
```

## Function in Js, Variable Scope and Callback Functions ? 
  ### function: 
    reusable block of code that can be invoked using the decalred function name whenever required. 
    Why Functions: reduces the work on debugging a code, centralises the code and promotes reusability. And Best for maintenance. 

  ### Types in Functions: 
    1. Regular Function
    2. Function expression.
    3. Arrow functions. 
    4. anonymous Functions. 

  1. **Regular Functions:** actual functions.
     ```
       function something(){
         // I want to do something here ..... 
       }

      something(); // function invocation
     ```
  2. **Function Expression:** the function is declared like a variable .
     
    ```
      const something = function(){
       // I do samething as regular function but my declaration is different.
     };
     something(); // function invocation
    ```
  3. **Arrow Functions:** function is declared with out the function keyword.
     
    ```
    const something = () => {
      // I do same thing but, i'm short form of function expression. 
    };
        something(); // function invocation
    ```
  4. **anonymous Function:** Where the function is unknown, similar to arrow functions.
     
  ```
    // I don't have any name.
    // Example is set Timeout.
    setTimeout(()=>{
      // I'm an anonymous function, my functionality is restrited to this scope. 
    }, 1000);
// see this , there is a function in param1 but it doesn't have any name. 
  ```

### Call back Functions. 
    - Function is passed to another function and invoked inside. 
    - Think like a parent-child relation. 
    - A child can be called inside a parent, but child is declared outsiode and the child name is sent to parent to call. 
    #### Best Example: 
      * SetTimeout, setInterval are best examples for the callbacks. 
      setTimeout(functionName , timeInMilliSeconds); // Hey, i will call the function after the specified time. 
      setInterval(functionName, timeInMilliSeconds); // Hey, i will call function after the specified inteval throughout. 
      
### Important things
    * we have different ways to call a function and passing certain things requires scope, to control this we have 3 important helpers in functions. 
    * 1. call , 2. Apply, 3. Bind . These are used to invoke a function by passing the necesasary references. 
    
    1. call: I will call the function immediately but i take parameters in sequential order and sepereated by comma. 
        something.call(globalObject, param1,param2); 
    2. Apply: I do the same thing as call, but i take parameters as a array object.
        something.apply(globalObject,[param1,param2]); 
    3. Bind: i will generate a return the function and store it with the passing of necesaary params. 
      var newFunc = something.bind(globalObject);
      newFunc(param1,param2); 
    -- Everything does the same but the use case and way of passing params are differed.
    
### Controlling variable scope in side function. 
    let, const are used to cointrol the scope block level. 
    if we declared a variable with let or const the varaible is restricted with in that scopr. 
    ```
      function iWillDo(){
        let something = 0 ; 
        console.log(something); // prints 0 in console.
      }
      console.log(something); // refernece error     
    ```
    
## Asynchronous Programming using JS. 
### Asynchronous: 
    Leaving a piece to work on itself and comeback after it's completion. 
    Say, i have 3 things to do , in regular way , i will do 1st thing first  then second and third. sequentially. if second fails third wont start. foce stop. 
    Now, i have seperated 3 things into 1 each and started all , now which ever is completed that will comes out. and if any fails, it doesn't impact other.

    -- Internally, JS runs on single thread but when asynchronous comes in it will allocate a partial thread to it and works on remaining. 

Why I need this: 
1. it is fail safe. meaning, if anything fails that will be stopped and remaining continues.
2. removes tight couply and segregates the responsibilities.
3. Good for understanding and debugging.

SetTimeout, setInterval are examples for asynchronous programming, which delays the result based on the specified time. 
When the number of callbacks increases, handles of code becomes tidious and becomes as a giant stack. we call it as callback hell. which is not readable. 

Inorder to remove this issue, ES6 came up with promises. which are modular way of doing things. and removes the confusion and improves readability. 

ES6 also introduced async await. which are similar to promises but makes code more modular and easy to understand. 

## Promises ? 
### A explained above, promises are used to reduce the complexity. 
    Promises has a cycle / tree which takes the decisions. Below is the tree. 
<img src="https://github.com/user-attachments/assets/c27f0bdf-34d7-428c-861a-851c7679135b" style="width:10%;height:10%" />


    new Promise((resolve, reject)) --> way of declaring a priomise, takes two params resolve and reject, 
    then --> used to run specify what to do next. 

    Promises also become doom's pyramid, if number of events increase, to eliminate this we have promise chaining and we also have combinators. 

    #### Promise Chaining: 
      Instead of calling the next promise inside another promise, just return the next promise and handle it outside of current promise. 
<img src="https://github.com/user-attachments/assets/d3add52a-5c30-4750-adaa-c859560afa87" style="width:10%;height:10%" />

What to Optimize more: Use Combinators: 
we have 4 combinators, 1. All, 2. race , 3. AllSettled , 4.Any
1. All: Runs all the promises and returns the results. if any 1 fails / rejected all will get rejected.
2. Race: Runs all until the any promise is settled. (First come first win) .
3. AllSettled : Similar to All, but
4. Any: Similar to Race, but ignores rejections. Rejected when all promises are rejected.

### They are confusing to me, is there any better approach?? 
    Yes, we have a better approach that is async,. await. which aree introduced in ES8. 
    They are much cleaner compared to promises, and internally works almost the smae. 
    use await before calling any promise and make use of async keyword before the function declaration. 
    --> How to handle the errors here: 
        Simple , wrap the function body in try catch block and catch handles the errors. 

## 
