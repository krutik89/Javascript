# What is Variable
  **Variable** is named storage used to hold data that can be change later during program execution. think variable as container which is used to store data like number, string and 
  object. with the help of variable we can create dynamic programs which is used to store, modify and retrieve the data.

# Types of variables in Javascript.
  In Javascript there are three different types to create variables `var`, `let` and `const`. <br>
  1. **`var` (Variable Declaration)**
     - **Scope**: `var` keyword has **function scope**. This means variable declared with `var` keyword are accesible throughout the function that declared in or globally if not in                         function
     - **Hoisting** : `var` keyword hoisted top of their scope. this means variable moves to the top of their scope but not initialized.
     - **Re-declaration**: variable declared with `var` keyword can be redeclared within same scope.
       ```javascript
           var x = 5;
           var x = 10; // No error, x is now 10

       ```

  2. **`let` (Block Scope)**
     - **Scope**: `let` keyword has block scope. This means variable declared with `let` keyword are accesible within the block they are declared.
     - **Hoisting**: `let` keyword hoisted top of their scope but not initialized. This means accesing the variable before declaration will give reference error.
     - **Re-declaration**: variable declared with `let` keyword cannot be re-declared within same scope.
     - **Example**
       ```javascript
           let y = 5;
           y = 10; // Allowed, y is now 10
           let y = 15; // Error: Identifier 'y' has already been declared

       ```
  3. **`const` (constant Variable)**
     - **Scope**: `const` keyword has block scope. This means variable declared with `const` keyword are accesible within the block they are declared.
     - **Hoisting**: `const` keyword hoisted top of their scope but not initialized. This means accesing the variable before declaration will give reference error.
     - **Re-declaration and Re-assignment**: variable declared with `const` keyword cannot be re-declared or re-assigned after initial assignment. however for the `objects` and for the        `arrays` content still be modified.
     - **Example**
      ```javascript
           const z = 5;
           z = 10; // Error: Assignment to constant variable.
           const obj = { key: "value" };
           obj.key = "newValue"; // Allowed, modifying the object property
       ```
# Scope in Javscript
  1. **Global Scope**: any variable declared outside function or block has global scope. This means that variable are accesible anywhere in code.
  2. **Function Scope**: varibale declared with `var` keyword inside function has function scope. This means that variable is accesible in only that function.
  3. **Block Scope**: variable declared using `let` and `const` keyword in block `{}` has block scope. This means variable is accesible within only that block.

# Hoisting
  Hoisting is default behaviour of javascript to move the declaration top of their scope. `var` keyword is hoisted and initialized with `undefined`. `let` and `const` keyword hoisted     but not initialized. 

# Shadowing
  The variable can be `shadowed` if variable with same name declared in different scope. if variable declared in inner block (close to execution context) will shadow the variable      
  declared in outer block.

# Best practices
  - use `const` and `let` keyword to avoid scope and hoisting issue.
  - use `const` keyword if value is not gonna change and `let` if value gonna change.
  - use meaningful variable name to enhace code readability.
  - follow consistent naming convention, like camelCase

# Pseudocode for Using Variables

  ```javascript
      // Declare a global variable using var
      var globalVar = "I'm global";

      // Function to demonstrate function-scoped variable
      function demonstrateVar() {
        var functionScopedVar = "I'm function-scoped"; 
        console.log(functionScopedVar); // Outputs: I'm function-scoped
      }

      // Block to demonstrate block-scoped variables
      if (condition) {
        let blockScopedLet = "I'm block-scoped";
        const blockScopedConst = "I'm also block-scoped";
    
        console.log(blockScopedLet); // Outputs: I'm block-scoped
        console.log(blockScopedConst); // Outputs: I'm also block-scoped
      }

      // Hoisting example
      console.log(hoistedVar); // Outputs: undefined
      var hoistedVar = "I'm hoisted";

      // Trying to access block-scoped variable outside the block
      console.log(blockScopedLet); // Error: blockScopedLet is not defined
  ```

# Data Types
  1. **Primitive Data Types** <br>
     Primitive data types are the most basic data type and represents single value. They are immutable in nature, means once value is assigned it can't be changed.
     Primitive Data Types has following sub types;
     1. **Number**: Number represents both integer and floating point numbers. example, `42` and `3.14` Javascript doesn't distinguish between Integer and Floating-Point numbers they           both treated as Number.
     2. **String**: Strings are the sequence of characters. Strings are used to store text and are enclosed in single quotes `''`, double quotes `""` or backticks ``. example `"Hello"`
     3. **Boolean**: Boolean represent logical entity value `true` or `false`.
     4. **Undefined**: when variable is declared without initialiaztion it's automically assigned `undefined` value.
     5. **Null**: Null is intentional absence of value. it is explicitly assigned to indicate that varibale has no value.
     6. **Symbol**: Symbol is unique and immutable value. it is oftnely used as object property keys to avoid same property name collision. example, `Symbol('unique')`.
     7. **bigInt**: Represents integers with arbitrary precision, useful for handling very large integers. Example: `1234567890123456789012345678901234567890n`.
    
     **Notes** <br>
     1. **Type Coercion With `null` and `undefined`** <br>
       - using `undefined` with number result is in `NaN` value. example 5+`undefined` will return `NaN`.
       - `null` is treated as `0` in arithmetic operation. example 5+`null` will return `5`.
     2. **BigInt and Number Interaction**: <br>
       - `BigInt` cannot be directly mixed with `number` in arithmetic operation. `5n + 1` is valid but will throw `TypeError`.
     3. **String Conversion** <br>
       - when concatenating `number` and `string`, The `number` is converted to `string` example `5 + '5'` will return `55`.
     4. **Symbol Uniqueness** <br>
       - Symbols are unique and can't be replicated. Even if we create symbol with same description it will not be equal to original symbol.

  2. **Non-Primitive Data Types** <br>
     Non-Primitive data types are mutable in nature. strored as reference. operations can change original value.

     1. **Objects** <br>
        In Javascript, object is a collection of properties, where each property is key-value pair. object can hold multiple data types, including function and other objects.
        - Creating an Object
          ```javascript

             const person = {
             name: 'Alice',
             age: 30,
             greet() {
               return `Hello, my name is ${this.name}`;
             }
            };

          ```
        - Accessing and Modifying Object
          ```javascript
            console.log(person.name); // Alice
            person.age = 31;
            console.log(person['age']); // 31

          ```

        - Adding New Properties
          ```javascript
             person.job = 'Engineer';
          ```

        - Deleting Properties
          ```javascript
             delete person.job;
          ```
     2. **Built In Objects** <br>
        Javascript provides several built in projects as following:

        - **Object**: The base object from which all objects inherit. <br>
          ```javascript
             const obj = new Object();
          ```
        - **Array**: For storing ordered collections.
          ```javascript
             const numbers = [1, 2, 3];
          ```
        - **String**: For manipulating text.
          ```javascript
            const str = 'Hello';
          ```
        - **Number**: For Numeric Operations.
          ```javascript
             const num = 123;
          ```
        - **Boolean**: For logical values.
          ```javascript
             const flag = true;
          ```
        - **Date**: For working with dates and times.
          ```javascript
             const date = new Date();
          ```
        - **RegExp**: for pattern matching in string.
          ```javascript
             const pattern = /ab+c/;
          ```
        - **Error**: For handling errors.
          ```javascript
             const error = new Error('Something went wrong');
          ```
     3. **Prototypal Inheritance** <br>
        Prototypal Inheritance allows objects to innherit properties from other objects. every object has prototype from which it inherits methods and properties.
        - Prototype Chain:
          Every object in JavaScript has a prototype. When you access a property or method on an object, JavaScript first looks at the object itself. If it doesn’t find the property,            it looks up the prototype chain, starting from the object's prototype and continuing up the chain until it reaches Object.prototype (which is the end of the chain).


          ```javascript
             function Animal(name) {
               this.name = name;
             }

             Animal.prototype.speak = function() {
                  console.log(`${this.name} makes a noise.`);
             };

             const dog = new Animal('Rex');
             dog.speak(); // Rex makes a noise.
          ```
        - Inheriting from Prototypes:
          ```javascript
             function Dog(name, breed) {
                Animal.call(this, name);
                this.breed = breed;
             }

             Dog.prototype = Object.create(Animal.prototype);
             Dog.prototype.constructor = Dog;

             Dog.prototype.bark = function() {
                console.log(`${this.name} barks.`);
             };

             const myDog = new Dog('Buddy', 'Golden Retriever');
             myDog.speak(); // Buddy makes a noise.
             myDog.bark(); // Buddy barks.

          ```
      4. **Object Prototype** <br>
         Prototype of an object is another object from which it inherits properties. this allows to create shared properties and methods.
         - Accessing Prototype
           ```javascript
              const obj = {};
              console.log(Object.getPrototypeOf(obj)); // Logs the prototype of obj
           ```
           
         - **Setting Prototype**
           ```javascript
              const proto = { greet: 'Hello' };
              const obj = Object.create(proto);
              console.log(obj.greet); // Hello
           ```
         - **Prototype Property**
           ```javascript
              function Person(name) {
                 this.name = name;
              }

              Person.prototype.sayHello = function() {
                return `Hello, ${this.name}`;
              };

              const person = new Person('Alice');
              console.log(person.sayHello()); // Hello, Alice

           ```
# `typeof` Operator
   `typeof` operator is used to determine type of variable or expression. it returns string representig type of operand. typeof is useful for debugging and type checking in javascript.
   ```javascript
      // Primitive types
      let num: number = 42;
      let str: string = 'Hello';
      let bool: boolean = true;
      let undef: undefined;
      let sym: symbol = Symbol('id');
      let big: bigint = 1234567890123456789012345678901234567890n;
      
      // Object types
      let obj: object = { name: 'Alice' };
      let arr: object = [1, 2, 3];
      let func: Function = function() {};
      let nothing: null = null;
      
      // Type checks
      console.log(typeof num); // "number"
      console.log(typeof str); // "string"
      console.log(typeof bool); // "boolean"
      console.log(typeof undef); // "undefined"
      console.log(typeof sym); // "symbol"
      console.log(typeof big); // "bigint"
      console.log(typeof obj); // "object"
      console.log(typeof arr); // "object"
      console.log(typeof func); // "function"
      console.log(typeof nothing); // "object"
  ```

  **Notes** <br>
  1. Arrays <br>
     `typeof` [1,2,3] return `object` not `array`. To check if variable is an array use `Array.isArray()`.

  2. `null` <br>
     `typeof` null is `object`.
  3. Function <br>
     `typeof` function is `function` but technically it is an array.
  4. Undefined <br>
     variables that are not initialized return `undefined`.
  5. Symbol and bigInt <br>
     `typeof` Symbols returns `Symbol` and `typeof` bigInt return `bigInt`.

# Type Casting
  In Javascript **Type Casting** is the process to converts a value from one data type to another. It is necessary as javascript is **dynamically typed** langugae, menas data type of    variable determines at runtime and can change as needed

  **Type Conversion vs Type Coercion**
  1. **Type Conversion** (Explicitly Type Casting) <br>
     when programmer manually converts one type into another using built in javascript functions.

     **Examples of Type Conversion** <br>
     ```javascript
        // Number to String
        let num = 42;
        let str = String(num); // Explicitly converts the number to a string
        console.log(typeof str); // Outputs: "string"
        
        // String to Number
        let strNum = "123";
        let convertedNum = Number(strNum); // Explicit conversion to number
        console.log(typeof convertedNum); // Outputs: "number"
        
        // Boolean to Number
        console.log(Number(true)); // Outputs: 1
        console.log(Number(false)); // Outputs: 0

     ```
     
  3. **Type Coercion** (Implicitly Type Casting) <br>
     This happens automatically when javascript **Implicitly** converts one type to another to perform an operation.
     ```javascript
        // String concatenation due to coercion
        console.log(5 + "5"); // Outputs: "55" (Number 5 is coerced to a string)
        console.log(true + 1); // Outputs: 2 (Boolean true is coerced to 1)
        console.log(null + 5); // Outputs: 5 (null is coerced to 0)
        console.log(undefined + 5); // Outputs: NaN (undefined is coerced to NaN)

     ```

  4. **Common Javascript Type Conversions** <br>
     - **String** <br>
       you can convert any value to string by using String() or concatenating any value with empty string.

       **Example** <br>
       ```javascript
          let num = 100;
          let str = String(num); // Explicit conversion to string
          console.log(typeof str); // "string"
          
          let implicitStr = 100 + ""; // Implicit conversion to string via concatenation
          console.log(typeof implicitStr); // "string"

       ```

     - **Number** <br>
       values can be converted to number using **Number()** function

# Data Structures
  1. **Keyed Collections** <br>
     - **Map** <br>
       `Map` is collection key-value pairs where key can be of any type including functions and objects.

       **Key Features**
         1. Maintains Insertion Order
         2. Provides efficient retrieval (has(),get(),set())
         3. Iterated Using `for...of, forEach`
      **Example**
        ```javascript
           let map = new Map();
           map.set('name', 'John');
           map.set(123, 'ID');
           console.log(map.get('name')); // Output: John
        ```
     - **WeakMap** <br>
       `WeakMap` is similar to `Map` but only accepts Objects as key and doesn't prevent garbage collection.

       **Example**
       ```javascript
          let weakMap = new WeakMap();
          let obj = {};
          weakMap.set(obj, 'Value');
          console.log(weakMap.get(obj)); // Output: Value
      ```
     - **set** <br>
       `set` stores unqiue values of any type
       **key features**
        1. order of values based on insertion.
        2. useful for filtering duplicates in array.

       ```javascript
          let set = new Set([1, 2, 2, 3]);
          console.log(set.size); // Output: 3
       ```
     - **WeakSet** <br>
        `WeakSet` is same as `set` but only allows object to add and doesn't prevent garbage collection
       **key features**
        1. prevent memory leaks.

       **Example**
       ```javascript
          let weakSet = new WeakSet();
          let obj = {};
          weakSet.add(obj);
       ```

      **Behaviour In Map**
        1. In `Map` keys are **strongly referenced** means no other part of program references key, it will remain in memory as long as `Map` holds it.
        2. Example:
           ```Javascript
              let map = new Map();
              let obj = { key: "value" };
              map.set(obj, "data");

              // Even if `obj` is not used anywhere else, it stays in memory
              obj = null;  // Map keeps a strong reference, so the key is not garbage collected
              console.log(map.size); // Output: 1
           ```
    
       **Behaviour In WeakMap**
       1. In `WeakMap` keys are **weakly referenced** which means if an object key is no longer referenced anywhere it will be garbage collected and will be removed from the map.
       2. Example:
         ```Javascript
            let weakMap = new WeakMap();
            let obj = { key: "value" };
            weakMap.set(obj, "data");

            // Once `obj` is no longer referenced, it can be garbage collected
            obj = null;  // The key-value pair is automatically removed from WeakMap
            console.log(weakMap.has(obj)); // Output: false
         ```
   2. **Structured Data**
      1. **JSON**
         JSON is text-based format that represents structured data commonly used for APIs and Data Transfer
         **Key Features**
           1. Easily converted into Javascript Objects and JSON Strings
           2. Methods: JSON.stringify() and JSON.parse()

         **Example**
         ```Javascript
            let obj = { name: 'Alice', age: 25 };
            let jsonString = JSON.stringify(obj); // Converts object to JSON string
            console.log(jsonString); // Output: {"name":"Alice","age":25}
            let parsedObj = JSON.parse(jsonString); // Converts JSON string back to object
         ```
   3. **Indexed Collections**

      1. **Arrays**
         Array stores indexed elements with each item accessible by numeric indices.

         **Key Features**
           1. supports various methods (Pop,Push,filter,map) etc
           2. can store any data type.

      2. **Typed Arrays**
          Typed Arrays provide a way to work with binary data efficiently.         
         
# Equality Comparisons
  Equality comparison is a process to determine whether two variables have identical values. <br>
  1. **Value Comparison Operators** <br>
     - == (Loosely Equality) <br>
       `==` operator does the type conversion of the operands before comparison.<br>
       The behavior of performing loose equality using `==` is as follows:<br>
       - If the operands have the same values they are compared as follows:<br>
         - `object`: returns `true` only if both operands are referenced to the same object.<br>
         **Example**:
         
          ```javascript
             let map = new Map();
             map.set('name', 'John');
             map.set(123, 'ID');
             console.log(map.get('name')); // Output: John
          ```
           - `string`: return `true` only if both operands have the same number of characters in the same order.
           - `Number`: return `true` only if both operands have the same values, +0 and -0 are treated as the same.<be>
                       If either operand is `NaN`, it returns `false` so NaN never equals to NaN
           - `boolean`: return `true` if both operands are `true` or both are `false`.
           - `symbol`: return `true` if both operands referenced the same symbol.
     - === (Strict Equality) <br>
       - Strict equality (===) compares operands for both value and type equality.
       - Strict equality does not perform type coercion. If the operands are of different types, it returns false.
     - Object.is() <br>
       `Object.is()` does no type conversion and no special handling for NaN, -0, and +0 (giving it the same behavior as === except on those special numeric values).

# Loops and Iteration
  Loops provide a mechanism for iterating over a block of code repeatedly. <br>
  This is analogous to instructing a computer to perform a specific task a predefined number of times.

  javascript offers a different kind of loops but all are essentially doing the same thing they repeat the same action a number of times.

  1. **For** <br>
     `For` loop repeats action until a specified condition evaluates false.<br>
     **Example**:
     ```Javascript
        for(let i=1;i<5;i++){
          console.log(`repeated action ${i} time`);
        }
        /*
          repeated action 1 time
          repeated action 2 time
          repeated action 3 time
          repeated action 4 time
         */
     ```
  3. **do...while** <br>
     The `do-while` loop is a looping construct that executes a block of code at least once.<br>
     It then repeatedly evaluates a specified condition. If the condition is false, the loop  terminates.<br>
     Unlike the `while` loop, the `do-while` loop guarantees that the code block executes at least once, even if the condition is initially false.
     **Example**
     ```Javascript
        let result = '';
        let i = 0;

        do {
          i = i + 1;
          result = result + i;
        } while (i < 5);

        console.log(result);
        // Expected output: "12345"
     ```
  4. **while** <br>
     - The `while` loop repeatedly executes a block of code as long as a specified condition remains true. <br>
     - The `while` loop evaluates the condition before executing the code block. If the condition is false initially, the code block is never executed. <br>
     **Example**
       ```Javascript
          let n = 0;

          while (n < 3) {
            n++;
          }

         console.log(n);
         // Expected output: 3
      ```
  5. **For...of** 
     - The JavaScript for of statement loops through the values of an iterable object.<br>
     - It lets you loop over iterable data structures such as Arrays, Strings, Maps, NodeLists, and more <br>
     **Example**
     ```Javascript
        const arr = [1,2,3,4];
        for(let number of arr){
           console.log(number);
        }
     ```
     - To print the index using a for...of loop in JavaScript, you can use the entries() method:
     ```Javascript
        const numbers = [10, 20, 30, 40];

        for (const [index, value] of numbers.entries()) {
             console.log(`Index: ${index}, Value: ${value}`);
        }
     ```

  6. **For...in**<br>
     The JavaScript `for in` statement loops through the properties of an Object. <br>
     ```Javascript
        const object = {name:"krutik",age:25,role:"frontend developer"};
        for(let key in object){
           console.log(key, object[key])
        }
     ```
     The `For...in` loop can also iterate over the array.

  7. **break** <br>
     The break statement "jumps out" of a loop.
     ```Javascript
        for (let i = 0; i < 10; i++) {
          if (i === 3) { break; }
        }
     ```
     In the example above, the `break` statement ends the loop ("breaks" the loop) when the loop counter (i) is 3.
  
  8. **continue** <br>
     The `continue` statement breaks one iteration (in the loop), if a specified condition occurs, and continues with the next iteration in the loop. <br>
     This example skips the value of 3:
     ```Javascript
        for (let i = 0; i < 10; i++) {
          if (i === 3) { continue; }
        }
     ```

# JavaScript Control Flow: A Comprehensive Guide with Examples  

Control flow in JavaScript refers to the order in which the instructions or statements in a script are executed. It includes constructs like conditional statements and exception handling mechanisms that allow developers to control the execution of code in a meaningful way.  

This guide provides a detailed overview with examples of:  
1. **Conditional Statements**
   - **if-else**  
   - **switch**  
2. **Exception Handling**
   - **throw statement**  
   - **try/catch/finally**  
   - **Error Objects**  

---

## 1. **Conditional Statements**  

### a. **If-Else**  

The `if` statement allows you to execute a block of code if a specified condition is `true`. The `else` block runs when the condition is `false`.  

**Syntax:**  
```javascript
if (condition) {
    // code to execute if condition is true
} else {
    // code to execute if condition is false
}
```

**Example 1: Basic If-Else**  
```javascript
const age = 18;

if (age >= 18) {
    console.log("You are eligible to vote.");
} else {
    console.log("You are not eligible to vote.");
}
```

**Example 2: If-Else If Ladder**  
```javascript
const score = 75;

if (score >= 90) {
    console.log("Grade: A");
} else if (score >= 75) {
    console.log("Grade: B");
} else {
    console.log("Grade: C");
}
```

---

### b. **Switch Statement**  

The `switch` statement is used to execute one block of code among many options based on the value of an expression.  

**Syntax:**  
```javascript
switch (expression) {
    case value1:
        // code to execute if expression === value1
        break;
    case value2:
        // code to execute if expression === value2
        break;
    default:
        // code to execute if no cases match
}
```

**Example: Using Switch**  
```javascript
const day = "Monday";

switch (day) {
    case "Monday":
        console.log("Start of the work week!");
        break;
    case "Friday":
        console.log("Almost the weekend!");
        break;
    case "Saturday":
    case "Sunday":
        console.log("It's the weekend!");
        break;
    default:
        console.log("Midweek hustle!");
}
```

---

## 2. **Exception Handling**  

JavaScript provides mechanisms to handle errors gracefully to avoid crashing the application. These mechanisms include the `throw` statement, `try/catch/finally` blocks, and working with error objects.  

---

### a. **Throw Statement**  

The `throw` statement lets you create custom errors in JavaScript. It can throw exceptions of any type (e.g., strings, numbers, objects).  

**Syntax:**  
```javascript
throw expression;
```

**Example: Throwing a Custom Error**  
```javascript
function checkNumber(num) {
    if (typeof num !== "number") {
        throw "Not a number!";
    }
    console.log("The number is:", num);
}

try {
    checkNumber("abc");
} catch (error) {
    console.log("Error:", error);
}
```

---

### b. **Try/Catch/Finally**  

The `try` block contains code that may throw an exception. The `catch` block contains code to handle the exception. The `finally` block executes regardless of the outcome of the `try` block.  

**Syntax:**  
```javascript
try {
    // code that might throw an error
} catch (error) {
    // code to handle the error
} finally {
    // code that always runs
}
```

**Example: Handling Errors with Try/Catch/Finally**  
```javascript
try {
    const result = 10 / 0;
    console.log("Result:", result);
    throw new Error("Division by zero is not allowed!");
} catch (error) {
    console.log("Caught an error:", error.message);
} finally {
    console.log("Execution complete.");
}
```

---

### c. **Error Objects**  

JavaScript has a built-in `Error` object that contains information about the error. You can also create custom error types.  

**Common Error Properties:**  
- `name`: Name of the error (e.g., `TypeError`, `SyntaxError`)  
- `message`: Describes what went wrong  
- `stack`: A string describing the point in the code where the error occurred  

**Example: Using Error Object**  
```javascript
function divide(a, b) {
    if (b === 0) {
        throw new Error("Cannot divide by zero.");
    }
    return a / b;
}

try {
    console.log(divide(10, 0));
} catch (error) {
    console.log("Error Name:", error.name);
    console.log("Error Message:", error.message);
    console.log("Error Stack:", error.stack);
}
```

**Creating a Custom Error Class:**  
```javascript
class ValidationError extends Error {
    constructor(message) {
        super(message);
        this.name = "ValidationError";
    }
}

try {
    throw new ValidationError("This is a validation error.");
} catch (error) {
    console.log(error.name); // ValidationError
    console.log(error.message); // This is a validation error.
}
```
