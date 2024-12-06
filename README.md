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

# JavaScript Control Flow  

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
# JavaScript Functions

Functions are core building blocks in JavaScript. They enable code reuse, modular design, and efficient problem solving. This guide provides a comprehensive understanding of JavaScript functions, including their declaration, behavior, and advanced concepts. 

## 1. **Defining Functions**  

### a. **Function Declaration**  

A function declaration defines a named function. It's hoisted, meaning it can be invoked before its declaration in the code.  

**Syntax:**  
```javascript
function functionName(parameters) {
    // function body
}
```

**Example:**  
```javascript
function greet(name) {
    return `Hello, ${name}!`;
}
console.log(greet("Alice")); // Output: Hello, Alice!
```

---

### b. **Function Expressions**  

Function expressions store a function in a variable. Unlike declarations, they are not hoisted.  

**Syntax:**  
```javascript
const variableName = function(parameters) {
    // function body
};
```

**Example:**  
```javascript
const square = function(number) {
    return number * number;
};
console.log(square(5)); // Output: 25
```

---

## 2. **Calling Functions**  

### a. **Function Hoisting**  

Function declarations are hoisted, so they can be called before being defined in the code. Function expressions are not hoisted.  

**Example:**  
```javascript
console.log(add(3, 4)); // Output: 7

function add(a, b) {
    return a + b;
}

// Below line will throw an error because expressions are not hoisted
// console.log(multiply(3, 4));
const multiply = function(a, b) {
    return a * b;
};
```

---

## 3. **Function Parameters**  

### a. **Default Parameters**  

Default parameters allow you to set a default value for a parameter if no argument is passed.  

**Syntax:**  
```javascript
function functionName(param = defaultValue) {
    // function body
}
```

**Example:**  
```javascript
function greet(name = "Guest") {
    return `Welcome, ${name}!`;
}
console.log(greet()); // Output: Welcome, Guest!
console.log(greet("Alice")); // Output: Welcome, Alice!
```

---

### b. **Rest Parameters**  

The `...rest` syntax collects all additional arguments into an array.  

**Syntax:**  
```javascript
function functionName(...rest) {
    // function body
}
```

**Example:**  
```javascript
function sum(...numbers) {
    return numbers.reduce((total, num) => total + num, 0);
}
console.log(sum(1, 2, 3, 4)); // Output: 10
```

---

## 4. **Arrow Functions**  

Arrow functions provide a concise syntax and do not bind their own `this` context.  

**Syntax:**  
```javascript
const functionName = (parameters) => {
    // function body
};
```

**Example:**  
```javascript
const multiply = (a, b) => a * b;
console.log(multiply(3, 4)); // Output: 12
```

---

## 5. **IIFEs (Immediately Invoked Function Expressions)**  

IIFEs are functions that are executed immediately after being defined.  

**Syntax:**  
```javascript
(function() {
    // function body
})();
```

**Example:**  
```javascript
(function() {
    const message = "This is an IIFE!";
    console.log(message);
})(); // Output: This is an IIFE!
```

---

## 6. **Arguments Object**  

The `arguments` object is an array-like object available inside all non-arrow functions. It contains the arguments passed to the function.  

**Example:**  
```javascript
function showArguments() {
    console.log(arguments);
}
showArguments(1, 2, 3); // Output: [1, 2, 3]
```

---

## 7. **Scope and Function Stack**  

### a. **Recursion**  

A recursive function is a function that calls itself until a base condition is met.  

**Example: Factorial**  
```javascript
function factorial(n) {
    if (n === 0) return 1;
    return n * factorial(n - 1);
}
console.log(factorial(5)); // Output: 120
```

---

### b. **Lexical Scoping**  

Functions have access to variables in their outer scope, even after the outer function has executed.  

**Example:**  
```javascript
function outer() {
    const outerVar = "I'm outer!";
    function inner() {
        console.log(outerVar); // Accesses variable from outer scope
    }
    inner();
}
outer(); // Output: I'm outer!
```

---

### c. **Closures**  

A closure is created when a function retains access to its lexical scope, even after the outer function has finished execution.  

**Example:**  
```javascript
function makeCounter() {
    let count = 0;
    return function() {
        count++;
        return count;
    };
}
const counter = makeCounter();
console.log(counter()); // Output: 1
console.log(counter()); // Output: 2
```

---

## 8. **Default Functions**  

Default functions are built-in methods that help with common tasks, such as `parseInt`, `isNaN`, or `setTimeout`.  

**Examples:**  

- `setTimeout`  
```javascript
setTimeout(() => {
    console.log("This message is displayed after 2 seconds");
}, 2000);
```

- `isNaN`  
```javascript
console.log(isNaN("Hello")); // Output: true
console.log(isNaN(123)); // Output: false
```
# **Understanding Lexical Scoping and Closures in JavaScript**

Lexical scoping and closures are fundamental concepts in JavaScript. Together, they explain how variables are resolved and accessed in nested functions. Let’s explore both in detail with examples.

---

## **1. Lexical Scoping**

### **Definition**  
Lexical scoping means that the scope of a variable is determined by its position in the source code, and nested functions have access to variables declared in their outer scope.

### **Key Points**
1. **Static Scope:** Variables are resolved based on where they are written in the code, not where they are called.
2. Inner functions have access to the variables of their parent function and global scope.
3. Scope is determined at **compile time** and does not change during runtime.

### **Example: Lexical Scope**
```javascript
function outer() {
    const outerVar = "I'm from the outer scope";

    function inner() {
        console.log(outerVar); // Accesses variable from the outer scope
    }

    inner();
}

outer(); // Output: I'm from the outer scope
```

Here’s what’s happening:
- The `inner` function is declared inside the `outer` function.
- `inner` has access to `outerVar` because of lexical scoping.

---

### **Scope Chain**
When a function looks for a variable:
1. It first checks its own scope.
2. If not found, it looks in its parent’s scope.
3. This continues up to the global scope.

**Example: Scope Chain**
```javascript
const globalVar = "I'm global";

function outer() {
    const outerVar = "I'm outer";

    function inner() {
        const innerVar = "I'm inner";
        console.log(globalVar); // Access globalVar
        console.log(outerVar);  // Access outerVar
    }

    inner();
}

outer();
// Output:
// I'm global
// I'm outer
```

---

## **2. Closures**

### **Definition**  
A closure is created when a function "remembers" the variables from its lexical scope, even after the outer function has completed execution.

### **Key Points**
1. A closure is formed when a function retains access to its outer scope.
2. It allows you to preserve data across multiple function calls.
3. This is possible because functions in JavaScript are **first-class citizens** (they can be returned, passed around, or assigned to variables).

---

### **Example 1: Closure Retaining Outer Variables**
```javascript
function makeCounter() {
    let count = 0; // Variable in the outer scope

    return function () {
        count++; // Inner function accesses count
        return count;
    };
}

const counter = makeCounter(); // Closure is created
console.log(counter()); // Output: 1
console.log(counter()); // Output: 2
console.log(counter()); // Output: 3
```

**Explanation:**
- The `makeCounter` function returns an inner function.
- Even after `makeCounter` finishes execution, the returned function retains access to the `count` variable from its lexical scope.
- The `count` variable is preserved because of the closure.

---

### **Example 2: Multiple Closures with Independent States**
```javascript
function createMultiplier(multiplier) {
    return function (num) {
        return num * multiplier; // Uses the outer multiplier
    };
}

const double = createMultiplier(2);
const triple = createMultiplier(3);

console.log(double(5)); // Output: 10
console.log(triple(5)); // Output: 15
```

**Explanation:**
- Each call to `createMultiplier` creates a new closure with its own `multiplier` variable.
- The inner function retains access to its specific `multiplier` value.

---

### **Example 3: Closures in Loops**
Closures are often used with loops to capture variables.

**Problem Without Closure:**
```javascript
for (var i = 1; i <= 3; i++) {
    setTimeout(function () {
        console.log(i); // All log 4 because `i` is shared
    }, 1000);
}
```

**Solution Using Closures:**
```javascript
for (var i = 1; i <= 3; i++) {
    (function (currentI) {
        setTimeout(function () {
            console.log(currentI); // Logs 1, 2, 3
        }, 1000);
    })(i); // IIFE captures the value of `i`
}
```

---

### **Practical Applications of Closures**

#### **1. Data Encapsulation**
Closures allow you to create private variables in JavaScript.

**Example:**
```javascript
function createSecret() {
    let secret = "My secret";

    return {
        getSecret: function () {
            return secret; // Access secret variable
        },
        setSecret: function (newSecret) {
            secret = newSecret; // Modify secret variable
        }
    };
}

const mySecret = createSecret();
console.log(mySecret.getSecret()); // Output: My secret
mySecret.setSecret("New secret");
console.log(mySecret.getSecret()); // Output: New secret
```

---

#### **2. Memoization**
Closures help in caching results of expensive function calls.

**Example:**
```javascript
function memoize(fn) {
    const cache = {};
    return function (arg) {
        if (cache[arg] !== undefined) {
            console.log("Fetching from cache");
            return cache[arg];
        }
        console.log("Computing result");
        const result = fn(arg);
        cache[arg] = result;
        return result;
    };
}

const square = memoize((num) => num * num);

console.log(square(5)); // Computing result; Output: 25
console.log(square(5)); // Fetching from cache; Output: 25
```

---

## **Key Differences Between Lexical Scoping and Closures**

| **Aspect**              | **Lexical Scoping**                           | **Closures**                                |
|-------------------------|----------------------------------------------|--------------------------------------------|
| **Definition**          | The ability of a function to access variables in its lexical scope. | When a function "remembers" its outer scope even after execution. |
| **Focus**               | Determines how variables are resolved.        | Enables persistent access to variables.     |
| **When It Happens**     | At the time of writing the code.              | At the time of execution.                   |
| **Example Usage**       | Resolving variable references.                | Maintaining private variables or states.    |


# **Complete Guide to JavaScript Web APIs with Examples**

JavaScript Web APIs are built-in interfaces provided by browsers to enable developers to interact with the browser environment and enhance web applications. These APIs allow you to manipulate the DOM, handle events, work with multimedia, make network requests, and much more.

---

## **Categories of Web APIs**

### 1. **Document Object Model (DOM) APIs**
   - Access and manipulate HTML and CSS.
   - Examples: `document`, `element`, `querySelector`.

### 2. **Browser APIs**
   - Enable browser-specific functionality.
   - Examples: `window`, `localStorage`, `sessionStorage`.

### 3. **Network APIs**
   - Handle HTTP requests.
   - Examples: `fetch`, `XMLHttpRequest`, `WebSocket`.

### 4. **Multimedia APIs**
   - Work with audio, video, and streams.
   - Examples: `MediaStream`, `Canvas`.

### 5. **Geolocation API**
   - Retrieve geographical location.

### 6. **Other APIs**
   - Timers (`setTimeout`, `setInterval`), Clipboard API, Notifications, etc.

---

## **Detailed Guide with Examples**

### **1. DOM Manipulation API**

#### **Accessing Elements**
```javascript
const heading = document.querySelector("h1"); // Select the first <h1>
console.log(heading.textContent);
```

#### **Modifying Elements**
```javascript
const heading = document.querySelector("h1");
heading.textContent = "Hello, Web APIs!"; // Change text
heading.style.color = "blue"; // Change CSS
```

#### **Creating and Appending Elements**
```javascript
const newDiv = document.createElement("div");
newDiv.textContent = "I am a new div!";
document.body.appendChild(newDiv);
```

---

### **2. Browser APIs**

#### **Working with Local Storage**
Store, retrieve, and delete data from the browser’s local storage.
```javascript
// Set an item
localStorage.setItem("username", "JohnDoe");

// Get the item
const username = localStorage.getItem("username");
console.log(username); // Output: JohnDoe

// Remove the item
localStorage.removeItem("username");
```

#### **Session Storage**
Similar to local storage, but data is cleared when the session ends.
```javascript
sessionStorage.setItem("isLoggedIn", "true");
console.log(sessionStorage.getItem("isLoggedIn")); // Output: true
sessionStorage.clear(); // Clear session storage
```

#### **Using the `window` Object**
```javascript
console.log(window.innerWidth); // Current width of the browser window
console.log(window.location.href); // Current URL
window.alert("Welcome to Web APIs!"); // Show an alert box
```

---

### **3. Network APIs**

#### **Fetching Data with `fetch`**
The `fetch` API simplifies making network requests.
```javascript
fetch("https://jsonplaceholder.typicode.com/posts")
    .then(response => response.json())
    .then(data => console.log(data))
    .catch(error => console.error("Error:", error));
```

#### **Using `XMLHttpRequest`**
An older way to make HTTP requests.
```javascript
const xhr = new XMLHttpRequest();
xhr.open("GET", "https://jsonplaceholder.typicode.com/posts");
xhr.onload = function () {
    console.log(JSON.parse(xhr.responseText));
};
xhr.send();
```

#### **WebSockets**
Real-time communication between the client and server.
```javascript
const socket = new WebSocket("wss://example.com/socket");

socket.onopen = () => console.log("Connected!");
socket.onmessage = (event) => console.log("Message:", event.data);
socket.onclose = () => console.log("Disconnected!");
```

---

### **4. Geolocation API**

#### **Retrieving the User's Location**
```javascript
if (navigator.geolocation) {
    navigator.geolocation.getCurrentPosition(
        position => {
            console.log("Latitude:", position.coords.latitude);
            console.log("Longitude:", position.coords.longitude);
        },
        error => console.error("Error:", error.message)
    );
} else {
    console.log("Geolocation is not supported by this browser.");
}
```

---

### **5. Multimedia APIs**

#### **Canvas API**
Drawing graphics on a webpage.
```javascript
const canvas = document.querySelector("canvas");
const ctx = canvas.getContext("2d");

// Draw a rectangle
ctx.fillStyle = "red";
ctx.fillRect(10, 10, 150, 100);
```

#### **Playing Video**
```javascript
const video = document.querySelector("video");
video.play(); // Start playing
video.pause(); // Pause
```

#### **Accessing Media Devices**
Capture video or audio using the MediaDevices API.
```javascript
navigator.mediaDevices.getUserMedia({ video: true })
    .then(stream => {
        const video = document.querySelector("video");
        video.srcObject = stream;
    })
    .catch(error => console.error("Error accessing camera:", error));
```

---

### **6. Timers and Intervals**

#### **`setTimeout`**
Execute a function after a specified delay.
```javascript
setTimeout(() => {
    console.log("This message appears after 2 seconds!");
}, 2000);
```

#### **`setInterval`**
Execute a function repeatedly at specified intervals.
```javascript
setInterval(() => {
    console.log("This message appears every second!");
}, 1000);
```

---

### **7. Notifications API**

#### **Requesting Permission**
```javascript
Notification.requestPermission().then(permission => {
    if (permission === "granted") {
        new Notification("Hello!", { body: "This is a notification!" });
    }
});
```

---

### **8. Clipboard API**

#### **Copy Text to Clipboard**
```javascript
navigator.clipboard.writeText("Hello, Clipboard!").then(() => {
    console.log("Text copied to clipboard!");
});
```

#### **Read Text from Clipboard**
```javascript
navigator.clipboard.readText().then(text => {
    console.log("Clipboard content:", text);
});
```

---

### **9. Intersection Observer API**

Efficiently detect when an element is visible in the viewport.
```javascript
const observer = new IntersectionObserver(entries => {
    entries.forEach(entry => {
        if (entry.isIntersecting) {
            console.log("Element is visible:", entry.target);
        }
    });
});

const element = document.querySelector(".target");
observer.observe(element);
```

---

### **10. Drag and Drop API**

#### **Enabling Drag and Drop**
```html
<div id="draggable" draggable="true">Drag me!</div>
<script>
    const draggable = document.getElementById("draggable");

    draggable.addEventListener("dragstart", event => {
        event.dataTransfer.setData("text/plain", "This is draggable!");
    });

    document.addEventListener("dragover", event => event.preventDefault());

    document.addEventListener("drop", event => {
        event.preventDefault();
        console.log(event.dataTransfer.getData("text"));
    });
</script>
```

# **JavaScript Strict Mode

JavaScript **Strict Mode** is a feature introduced in ECMAScript 5 (ES5) that helps you write cleaner and more robust code by enforcing stricter parsing and error handling. It eliminates some silent errors, improves performance, and ensures better security.

---

## **1. Enabling Strict Mode**

Strict mode can be enabled in two ways:
1. **Globally:** For the entire script.
2. **Locally:** Within a specific function.

### **1.1 Enabling Globally**
Add `"use strict";` at the beginning of a script file.

```javascript
"use strict";
x = 10; // Error: x is not defined
console.log(x);
```

### **1.2 Enabling Locally**
Place `"use strict";` inside a function to restrict it only to that function.

```javascript
function strictFunction() {
    "use strict";
    y = 20; // Error: y is not defined
}
strictFunction();
```

---

## **2. Features and Benefits of Strict Mode**

### **2.1 Prevents Usage of Undeclared Variables**
In non-strict mode, assigning to an undeclared variable automatically creates it as a global variable. Strict mode eliminates this.

```javascript
"use strict";
x = 10; // Error: x is not defined
```

---

### **2.2 Prevents Duplicates in Function Parameters**
Strict mode disallows duplicate parameter names, which can cause ambiguity.

```javascript
"use strict";
function add(a, a) { // Error: Duplicate parameter name not allowed
    return a + a;
}
```

---

### **2.3 Eliminates Silent Errors**
Some JavaScript errors fail silently in non-strict mode. Strict mode throws explicit errors.

**Example: Assigning to a non-writable property**
```javascript
"use strict";
const obj = {};
Object.defineProperty(obj, "prop", { value: 42, writable: false });

obj.prop = 100; // Error: Cannot assign to read-only property 'prop'
```

---

### **2.4 Prevents Deletion of Non-Deletable Properties**
In strict mode, you cannot delete properties that are not configurable.

```javascript
"use strict";
delete Object.prototype; // Error: Cannot delete 'prototype' property
```

---

### **2.5 Requires Secure `this` Binding**
In strict mode, `this` inside a function defaults to `undefined` instead of the global object.

```javascript
"use strict";
function showThis() {
    console.log(this); // Output: undefined
}
showThis();
```

---

### **2.6 Restricts the Use of Reserved Keywords**
Strict mode reserves certain keywords for future JavaScript versions, such as `implements`, `interface`, and `package`.

```javascript
"use strict";
const package = "strict mode"; // Error: Unexpected strict mode reserved word
```

---

## **3. Common Use Cases of Strict Mode**

### **3.1 Debugging Errors**
Strict mode helps identify potential bugs early, such as accidental global variable creation.

```javascript
"use strict";
function calculate() {
    result = 42; // Error: 'result' is not defined
    return result;
}
calculate();
```

---

### **3.2 Securing Code**
Strict mode ensures secure coding practices by preventing `this` from pointing to the global object.

```javascript
"use strict";
function secureFunction() {
    console.log(this); // Output: undefined
}
secureFunction();
```

---

### **3.3 Writing Modern JavaScript**
Strict mode aligns with modern ECMAScript standards and is often implicitly enabled in ES6 modules.

---

## **4. Restrictions Imposed by Strict Mode**

### **4.1 No Octal Literals**
Strict mode disallows the use of octal literals (numbers starting with `0`).

```javascript
"use strict";
const num = 010; // Error: Octal literals are not allowed
```

### **4.2 No `with` Statement**
The `with` statement is disallowed because it makes code harder to understand and debug.

```javascript
"use strict";
with (Math) { // Error: 'with' statement is not allowed
    console.log(sqrt(16));
}
```

---

### **4.3 Prevents `eval` from Introducing Variables**
In strict mode, variables declared inside `eval` do not leak into the surrounding scope.

```javascript
"use strict";
eval("var a = 5;");
console.log(a); // Error: a is not defined
```

---

## **5. When to Use Strict Mode**
1. When writing **secure applications** to avoid accidental global variable creation.
2. For **debugging and cleaner code**, as strict mode surfaces silent errors.
3. To ensure **modern JavaScript compatibility** and follow best practices.
4. When working with **third-party libraries** that may conflict with your code.

---

## **6. Example: Combining Strict Mode with Functions**

**Example 1: Securing a Function**
```javascript
function strictSum(a, b) {
    "use strict";
    return a + b;
}
console.log(strictSum(5, 10)); // Output: 15
```

**Example 2: Debugging Errors**
```javascript
"use strict";
function debug() {
    x = 100; // Error: x is not defined
}
debug();
```

---

## **7. Strict Mode in ES6 Modules**
By default, ES6 modules (`import`/`export`) are in strict mode. You do not need to manually enable it.

**Example: ES6 Module (auto strict mode)**
```javascript
export const greeting = "Hello!";
console.log(greeting);
```

---

## **8. Disabling Strict Mode**
If you need to use non-strict mode within strict code, wrap the non-strict code in a function without `"use strict";`.

**Example: Mixing Modes**
```javascript
"use strict";
function nonStrictFunction() {
    // Non-strict mode
    x = 42; // Works here
    console.log(x);
}
nonStrictFunction();
```

---

## **9. Strict Mode and Performance**
Strict mode can slightly improve performance in some cases because:
1. It allows the JavaScript engine to optimize code more effectively.
2. It eliminates the need for certain checks, such as handling accidental global variables.

# **Complete Guide to Asynchronous JavaScript with Examples**

Asynchronous JavaScript allows tasks to run in the background without blocking the main thread, enabling efficient and responsive web applications. This guide covers the fundamental concepts, tools, and best practices of asynchronous programming in JavaScript.

---

## **1. Event Loop**

### **What is the Event Loop?**
The event loop is the core mechanism that handles asynchronous operations in JavaScript. It ensures the **call stack** is never blocked by offloading tasks (e.g., I/O, timers, or promises) to the **Web APIs** or **Task Queue**, and then processing them when the stack is empty.

### **How It Works**
1. **Call Stack**: Contains functions that are currently being executed.
2. **Web APIs**: Executes async operations like `setTimeout`, `fetch`, etc.
3. **Task Queue (or Callback Queue)**: Holds callbacks from Web APIs to be added to the call stack.
4. **Microtask Queue**: For high-priority tasks like `Promise` resolution.
5. **Event Loop**: Continuously checks if the call stack is empty and processes tasks from the task queue or microtask queue.

**Example of Event Loop in Action:**
```javascript
console.log("Start");

setTimeout(() => {
    console.log("Timeout callback");
}, 0);

Promise.resolve().then(() => {
    console.log("Promise callback");
});

console.log("End");
```

**Output:**
```
Start
End
Promise callback
Timeout callback
```

**Explanation:**
- `setTimeout` adds its callback to the **Task Queue**.
- `Promise` adds its callback to the **Microtask Queue** (higher priority).
- The **call stack** processes synchronous tasks first (`Start`, `End`).
- The **microtask queue** executes next (`Promise callback`).
- Finally, the **task queue** is processed (`Timeout callback`).

---

## **2. `setTimeout`**

`setTimeout` schedules a function to be executed after a specified delay.

### **Syntax:**
```javascript
setTimeout(callback, delay, ...args);
```

- `callback`: Function to execute.
- `delay`: Delay in milliseconds (default is 0).
- `...args`: Arguments passed to the callback.

**Example: Basic `setTimeout`**
```javascript
setTimeout(() => {
    console.log("Executed after 2 seconds");
}, 2000);
```

**Example: Passing Arguments**
```javascript
function greet(name) {
    console.log(`Hello, ${name}`);
}

setTimeout(greet, 3000, "Alice"); // Output: Hello, Alice
```

---

## **3. `setInterval`**

`setInterval` repeatedly executes a function at a fixed time interval.

### **Syntax:**
```javascript
setInterval(callback, delay, ...args);
```

**Example: Basic `setInterval`**
```javascript
let counter = 0;

const intervalId = setInterval(() => {
    console.log(`Counter: ${++counter}`);
    if (counter === 5) {
        clearInterval(intervalId); // Stop the interval
    }
}, 1000);
```

---

## **4. `clearTimeout` and `clearInterval`**

- **`clearTimeout(timeoutId)`**: Cancels a `setTimeout` operation.
- **`clearInterval(intervalId)`**: Stops a `setInterval` operation.

**Example: Cancelling `setTimeout`**
```javascript
const timeoutId = setTimeout(() => {
    console.log("This will not run");
}, 3000);

clearTimeout(timeoutId);
```

---

## **5. Callbacks**

A **callback** is a function passed as an argument to another function and is executed after some operation is completed.

### **Example: Callback Function**
```javascript
function fetchData(callback) {
    setTimeout(() => {
        console.log("Data fetched");
        callback("Fetched data");
    }, 2000);
}

fetchData((data) => {
    console.log(data); // Output: Fetched data
});
```

---

### **5a. Callback Hell**
When callbacks are nested deeply, they lead to complex and hard-to-read code, known as **callback hell**.

**Example of Callback Hell:**
```javascript
setTimeout(() => {
    console.log("Step 1");
    setTimeout(() => {
        console.log("Step 2");
        setTimeout(() => {
            console.log("Step 3");
        }, 1000);
    }, 1000);
}, 1000);
```

### **Solution: Promises**

---

## **6. Promises**

A **Promise** represents the eventual result of an asynchronous operation. It has three states:
1. **Pending**: Initial state.
2. **Fulfilled**: Operation completed successfully.
3. **Rejected**: Operation failed.

### **Creating a Promise**
```javascript
const myPromise = new Promise((resolve, reject) => {
    const success = true;

    if (success) {
        resolve("Operation succeeded");
    } else {
        reject("Operation failed");
    }
});
```

### **Consuming a Promise**
- **`then`**: Handles success.
- **`catch`**: Handles errors.
- **`finally`**: Executes cleanup code.

**Example: Using Promises**
```javascript
myPromise
    .then((result) => console.log(result)) // Output: Operation succeeded
    .catch((error) => console.log(error))
    .finally(() => console.log("Done!"));
```

---

### **6a. `async/await`**

`async/await` simplifies working with promises, making asynchronous code look like synchronous code.

### **Syntax:**
- `async`: Marks a function as asynchronous, returning a Promise.
- `await`: Pauses execution until the Promise resolves or rejects.

**Example: Basic `async/await`**
```javascript
async function fetchData() {
    const response = await new Promise((resolve) =>
        setTimeout(() => resolve("Data fetched"), 2000)
    );
    console.log(response); // Output: Data fetched
}

fetchData();
```

**Example: Error Handling**
```javascript
async function fetchData() {
    try {
        const response = await Promise.reject("Fetch error");
        console.log(response);
    } catch (error) {
        console.log(error); // Output: Fetch error
    }
}

fetchData();
```

---

### **Combining Promises with `async/await`**
**Example: Fetching Data**
```javascript
function fetchUserData() {
    return new Promise((resolve) => {
        setTimeout(() => resolve({ id: 1, name: "Alice" }), 1000);
    });
}

async function main() {
    const user = await fetchUserData();
    console.log(user); // Output: { id: 1, name: "Alice" }
}

main();
```

---

## **Best Practices for Asynchronous Code**

1. **Avoid Callback Hell**:
   - Use Promises or `async/await`.
2. **Error Handling**:
   - Always use `.catch()` or `try/catch` with promises and `async/await`.
3. **Debounce and Throttle**:
   - Control event execution frequency for performance.
4. **Use Web Workers**:
   - Offload heavy computations to background threads.
5. **Understand the Event Loop**:
   - Helps debug asynchronous behavior.

---

## **Summary**

| **Topic**           | **Key Features**                                                                                            |
|---------------------|------------------------------------------------------------------------------------------------------------|
| **Event Loop**      | Handles asynchronous operations via the call stack, task queue, and microtask queue.                       |
| **`setTimeout`**    | Delays the execution of a function by a specified time.                                                    |
| **`setInterval`**   | Repeats a function at fixed intervals until cleared.                                                       |
| **Callbacks**       | Functions executed after an operation completes; can lead to callback hell.                                |
| **Promises**        | Manage asynchronous code more cleanly with `.then`, `.catch`, and `.finally`.                              |
| **`async/await`**   | Simplifies promise-based code to look synchronous; requires proper error handling with `try/catch`.        |

Here’s a **detailed guide** for each topic in JavaScript networking, with explanations, best practices, and code examples. 

---

### **1. Fetch API Basics**
The `fetch` API is a modern, promise-based way to make network requests. It simplifies the process of sending and receiving HTTP requests.

#### **Key Features:**
- Returns a `Promise`.
- Supports modern JavaScript syntax like `async/await`.

#### **Example: Basic GET Request**
```javascript
fetch('https://jsonplaceholder.typicode.com/posts')
  .then(response => {
    if (!response.ok) {
      throw new Error('Network response was not ok');
    }
    return response.json();
  })
  .then(data => console.log(data))
  .catch(error => console.error('Fetch error:', error));
```

#### **Best Practices:**
- Always handle errors with `.catch()`.
- Use `async/await` for better readability:
```javascript
async function fetchPosts() {
  try {
    const response = await fetch('https://jsonplaceholder.typicode.com/posts');
    if (!response.ok) throw new Error('Network error');
    const data = await response.json();
    console.log(data);
  } catch (error) {
    console.error('Error:', error);
  }
}
```

---

### **2. Working with FormData**
`FormData` simplifies working with form data, especially when dealing with files.

#### **Example: File Upload**
```javascript
const formData = new FormData();
formData.append('username', 'JohnDoe');
formData.append('profilePic', fileInput.files[0]); // fileInput is an `<input type="file">`

fetch('https://example.com/upload', {
  method: 'POST',
  body: formData,
})
  .then(response => response.json())
  .then(data => console.log('Success:', data))
  .catch(error => console.error('Error:', error));
```

#### **Best Practices:**
- Use `multipart/form-data` headers for file uploads.
- Avoid setting `Content-Type` manually; `fetch` sets it automatically.

---

### **3. Fetch: Download Progress**
Track download progress using `ReadableStream`.

#### **Example: Tracking Progress**
```javascript
fetch('https://example.com/large-file.zip')
  .then(response => {
    const reader = response.body.getReader();
    const contentLength = response.headers.get('Content-Length');
    let receivedLength = 0;

    return reader.read().then(function process({ done, value }) {
      if (done) {
        console.log('Download complete');
        return;
      }
      receivedLength += value.length;
      console.log(`Progress: ${(receivedLength / contentLength * 100).toFixed(2)}%`);
      return reader.read().then(process);
    });
  })
  .catch(error => console.error('Error:', error));
```

---

### **4. Fetch: Abort**
`AbortController` lets you cancel ongoing `fetch` requests.

#### **Example: Aborting a Request**
```javascript
const controller = new AbortController();

fetch('https://jsonplaceholder.typicode.com/posts', { signal: controller.signal })
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => {
    if (error.name === 'AbortError') {
      console.log('Fetch aborted');
    } else {
      console.error('Error:', error);
    }
  });

// Abort after 2 seconds
setTimeout(() => controller.abort(), 2000);
```

---

### **5. Fetch: Cross-Origin Requests**
Cross-Origin Resource Sharing (CORS) allows a resource on one domain to be requested from another domain.

#### **Example: Handling CORS**
```javascript
fetch('https://another-domain.com/api', { mode: 'cors' })
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('CORS error:', error));
```

#### **Best Practices:**
- The server must set `Access-Control-Allow-Origin` headers.
- Use a proxy if the server doesn't support CORS.

---

### **6. Fetch API Features**
`fetch` supports additional HTTP methods, custom headers, and request configurations.

#### **Example: POST Request**
```javascript
fetch('https://example.com/api', {
  method: 'POST',
  headers: {
    'Content-Type': 'application/json',
  },
  body: JSON.stringify({ name: 'John Doe', age: 30 }),
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

---

### **7. URL Objects**
The `URL` class simplifies URL manipulation.

#### **Example: Query Parameters**
```javascript
const url = new URL('https://api.example.com/data');
url.searchParams.append('q', 'javascript');
url.searchParams.append('limit', '10');

fetch(url)
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```

---

### **8. XMLHttpRequest**
The older `XMLHttpRequest` API provides fine-grained control over network requests.

#### **Example: Basic Request**
```javascript
const xhr = new XMLHttpRequest();
xhr.open('GET', 'https://jsonplaceholder.typicode.com/posts', true);

xhr.onload = () => {
  if (xhr.status === 200) {
    console.log(JSON.parse(xhr.responseText));
  } else {
    console.error('Request failed');
  }
};

xhr.onerror = () => console.error('Network error');
xhr.send();
```

---

### **9. Resumable File Upload**
Chunked file uploads allow pausing and resuming transfers.

#### **Example: File Chunking**
```javascript
const chunkSize = 1024 * 1024; // 1MB
const totalChunks = Math.ceil(file.size / chunkSize);

for (let i = 0; i < totalChunks; i++) {
  const start = i * chunkSize;
  const chunk = file.slice(start, start + chunkSize);

  fetch('https://example.com/upload', {
    method: 'POST',
    headers: {
      'Content-Range': `bytes ${start}-${start + chunkSize - 1}/${file.size}`,
    },
    body: chunk,
  }).then(response => console.log(`Chunk ${i + 1} uploaded`));
}
```

---

### **10. Long Polling**
Long polling maintains a connection to check for updates.

#### **Example: Polling for Updates**
```javascript
function poll() {
  fetch('https://example.com/updates')
    .then(response => response.json())
    .then(data => {
      console.log('Update:', data);
      poll(); // Keep polling
    })
    .catch(error => console.error('Error:', error));
}

poll();
```

---

### **11. WebSocket**
WebSockets enable real-time communication.

#### **Example: Chat Application**
```javascript
const ws = new WebSocket('wss://example.com/socket');

ws.onopen = () => console.log('Connected to WebSocket');
ws.onmessage = event => console.log('Message:', event.data);
ws.onerror = error => console.error('WebSocket Error:', error);
ws.onclose = () => console.log('WebSocket connection closed');
```

---

### **12. Server-Sent Events (SSE)**
SSE allows the server to send real-time updates to the client.

#### **Example: Receiving Events**
```javascript
const eventSource = new EventSource('https://example.com/events');

eventSource.onmessage = event => console.log('New message:', event.data);
eventSource.onerror = error => console.error('Error:', error);
```
### **JavaScript Classes: Complete Guide with Examples**

---

### **1. Classes Basic Syntax**

#### **Definition**  
A class is a blueprint for creating objects with predefined properties and methods. JavaScript classes were introduced in ES6 as syntactical sugar over JavaScript’s prototype-based inheritance.

#### **Example**: Creating and using a class  
```javascript
class Person {
    constructor(name, age) {
        this.name = name; // Instance property
        this.age = age;
    }

    // Instance method
    greet() {
        console.log(`Hello, my name is ${this.name} and I am ${this.age} years old.`);
    }
}

// Creating an instance
const person1 = new Person("Alice", 30);
person1.greet(); // Output: Hello, my name is Alice and I am 30 years old.
```
### **2. Class Inheritance in JavaScript**

#### **What is Class Inheritance?**
Class inheritance is a mechanism in JavaScript where a class (child class) can inherit properties and methods from another class (parent class). This allows code reuse and a logical hierarchical structure between classes.

Inheritance is implemented using the `extends` keyword. The child class can:
1. Use methods and properties of the parent class.
2. Override methods from the parent class.
3. Add its own methods and properties.

---

### **How to Use Class Inheritance**

#### **Defining a Parent Class**
A parent class is the base class that contains shared logic or properties that can be inherited by child classes.

```javascript
class Animal {
    constructor(name) {
        this.name = name;
    }

    speak() {
        console.log(`${this.name} makes a noise.`);
    }
}
```

#### **Creating a Child Class**
A child class is defined using the `extends` keyword. It inherits all the properties and methods of the parent class.

```javascript
class Dog extends Animal {
    speak() {
        console.log(`${this.name} barks.`);
    }
}

const dog = new Dog("Buddy");
dog.speak(); // Output: Buddy barks.
```

---

### **Key Concepts of Class Inheritance**

#### **1. The `super` Keyword**
- **Definition**: The `super` keyword is used to call the constructor or methods of the parent class.
- **Usage in Constructor**: When defining a constructor in the child class, the `super` keyword must be called before accessing `this`.

**Example: Using `super` in Constructor**
```javascript
class Animal {
    constructor(name) {
        this.name = name;
    }
}

class Dog extends Animal {
    constructor(name, breed) {
        super(name); // Call the parent class constructor
        this.breed = breed; // Add a new property
    }

    getDetails() {
        console.log(`${this.name} is a ${this.breed}.`);
    }
}

const dog = new Dog("Buddy", "Golden Retriever");
dog.getDetails(); // Output: Buddy is a Golden Retriever.
```

---

#### **2. Method Overriding**
- A child class can override a method inherited from the parent class by defining a method with the same name.

**Example: Overriding Methods**
```javascript
class Animal {
    speak() {
        console.log("Animal makes a sound.");
    }
}

class Cat extends Animal {
    speak() {
        console.log("Cat meows.");
    }
}

const cat = new Cat();
cat.speak(); // Output: Cat meows.
```

---

#### **3. Using Parent Methods in Overridden Methods**
- A child class can still access a method from the parent class using `super.methodName()`.

**Example: Combining Parent and Child Methods**
```javascript
class Animal {
    speak() {
        console.log("Animal speaks.");
    }
}

class Parrot extends Animal {
    speak() {
        super.speak(); // Call parent class method
        console.log("Parrot mimics speech.");
    }
}

const parrot = new Parrot();
parrot.speak();
// Output:
// Animal speaks.
// Parrot mimics speech.
```

---

#### **4. Adding New Methods and Properties in Child Classes**
Child classes can extend the parent class by adding their own properties and methods.

**Example: Adding Methods**
```javascript
class Vehicle {
    constructor(make) {
        this.make = make;
    }

    start() {
        console.log(`${this.make} starts.`);
    }
}

class Car extends Vehicle {
    drive() {
        console.log(`${this.make} drives.`);
    }
}

const car = new Car("Toyota");
car.start(); // Output: Toyota starts.
car.drive(); // Output: Toyota drives.
```

---

### **Practical Example of Class Inheritance**

#### Scenario: Hierarchy of Animals
You want to model different types of animals (e.g., dogs and birds), each with unique behaviors, while sharing common properties like a name and generic methods.

```javascript
// Parent class
class Animal {
    constructor(name) {
        this.name = name;
    }

    eat() {
        console.log(`${this.name} is eating.`);
    }
}

// Child class 1
class Dog extends Animal {
    speak() {
        console.log(`${this.name} barks.`);
    }
}

// Child class 2
class Bird extends Animal {
    fly() {
        console.log(`${this.name} is flying.`);
    }
}

const dog = new Dog("Buddy");
dog.eat();  // Output: Buddy is eating.
dog.speak(); // Output: Buddy barks.

const bird = new Bird("Tweety");
bird.eat();  // Output: Tweety is eating.
bird.fly();  // Output: Tweety is flying.
```

---

### **Key Rules of Class Inheritance**

1. **Constructors in Child Classes**
   - If you define a constructor in a child class, you must call `super()` before accessing `this`.

**Example: Constructor in a Child Class**
```javascript
class Parent {
    constructor(name) {
        this.name = name;
    }
}

class Child extends Parent {
    constructor(name, age) {
        super(name); // Calls the Parent constructor
        this.age = age;
    }
}
```

2. **Cannot Extend Multiple Classes**
   - JavaScript does not support multiple inheritance (a class cannot directly extend multiple classes). Mixins can be used as a workaround.

---

### **Extending Built-in Classes**

You can extend built-in classes like `Array`, `Error`, or `Date` to customize their behavior.

**Example: Extending Array**
```javascript
class CustomArray extends Array {
    average() {
        return this.reduce((acc, val) => acc + val, 0) / this.length;
    }
}

const numbers = new CustomArray(10, 20, 30);
console.log(numbers.average()); // Output: 20
```

**Example: Extending Error**
```javascript
class CustomError extends Error {
    constructor(message) {
        super(message);
        this.name = "CustomError";
    }
}

try {
    throw new CustomError("This is a custom error!");
} catch (error) {
    console.log(error.name);    // Output: CustomError
    console.log(error.message); // Output: This is a custom error!
}
```

---

### **Advantages of Class Inheritance**

1. **Code Reusability**: Share common logic across multiple classes.
2. **Logical Hierarchy**: Maintain a clear parent-child relationship.
3. **Extensibility**: Easily extend classes to add new features.

---

### **Disadvantages**

1. **Complexity**: Overuse of inheritance can make the code harder to understand.
2. **Tightly Coupled**: Changes in the parent class can affect child classes unexpectedly.

### **JavaScript Static Properties and Methods**

---

### **What are Static Properties and Methods?**

In JavaScript, **static properties and methods** are those that belong to a class itself, rather than to any instance of the class. You access static properties and methods using the class name, not through an instance of the class.

---

### **Key Characteristics of Static Properties and Methods**

1. **Class-Level Scope**:  
   Static properties and methods are shared across all instances and do not require an object instance to access.

2. **Declared with the `static` Keyword**:  
   Use the `static` keyword before defining a method or property in the class.

3. **Not Inherited by Instances**:  
   Static methods and properties cannot be accessed using `this` from an instance.

4. **Often Used for Utility Functions**:  
   Static methods are typically used for operations not specific to an instance, like utility or helper methods.

---

### **Syntax for Static Properties and Methods**

```javascript
class ClassName {
    static staticProperty = "I am static";
    
    static staticMethod() {
        return "This is a static method.";
    }
}

// Accessing static property
console.log(ClassName.staticProperty); // Output: I am static

// Accessing static method
console.log(ClassName.staticMethod()); // Output: This is a static method
```

---

### **Example: Static Method in Practice**

Here is an example of a utility method for basic mathematical operations:

```javascript
class MathUtil {
    static add(a, b) {
        return a + b;
    }

    static multiply(a, b) {
        return a * b;
    }
}

// Accessing static methods
console.log(MathUtil.add(3, 5));      // Output: 8
console.log(MathUtil.multiply(3, 5)); // Output: 15
```

---

### **Static vs Instance Methods and Properties**

| **Aspect**          | **Static**                                     | **Instance**                          |
|----------------------|-----------------------------------------------|---------------------------------------|
| **Access**           | Accessed using the class name.                | Accessed using an instance of the class. |
| **Context**          | Shared across all instances (class-level).     | Tied to a specific object instance.   |
| **Keyword**          | Declared with the `static` keyword.            | No special keyword.                   |
| **Example Access**   | `ClassName.method()`                          | `instance.method()`                   |

**Example**:  
```javascript
class Example {
    static staticMethod() {
        return "Static method";
    }

    instanceMethod() {
        return "Instance method";
    }
}

const exampleInstance = new Example();
console.log(Example.staticMethod());       // Output: Static method
console.log(exampleInstance.instanceMethod()); // Output: Instance method
```

---

### **Defining Static Properties**

As of ES6, static properties are not defined directly within the class body, but in ES2022+, they can be declared inline using the `static` keyword.

#### **Example 1: ES6 Way**
```javascript
class AppConfig {}
AppConfig.appName = "MyApp";
AppConfig.version = "1.0.0";

console.log(AppConfig.appName); // Output: MyApp
console.log(AppConfig.version); // Output: 1.0.0
```

#### **Example 2: ES2022+ Inline Static Properties**
```javascript
class AppConfig {
    static appName = "MyApp";
    static version = "1.0.0";
}

console.log(AppConfig.appName); // Output: MyApp
console.log(AppConfig.version); // Output: 1.0.0
```

---

### **Practical Use Cases**

#### **1. Singleton Pattern**
Static properties can be used to create singletons.

```javascript
class Singleton {
    static instance;

    constructor(name) {
        if (Singleton.instance) {
            return Singleton.instance;
        }
        Singleton.instance = this;
        this.name = name;
    }

    static getInstance(name) {
        if (!Singleton.instance) {
            Singleton.instance = new Singleton(name);
        }
        return Singleton.instance;
    }
}

const obj1 = Singleton.getInstance("FirstInstance");
const obj2 = Singleton.getInstance("SecondInstance");

console.log(obj1 === obj2); // Output: true
console.log(obj1.name);     // Output: FirstInstance
```

---

#### **2. Utility or Helper Classes**
Static methods are perfect for utility methods that do not depend on instance-specific data.

```javascript
class DateUtil {
    static getCurrentDate() {
        return new Date().toISOString();
    }
}

console.log(DateUtil.getCurrentDate()); // Output: Current date in ISO format
```

---

#### **3. Global Counters or Configuration**
Static properties can track shared states or configurations.

```javascript
class Counter {
    static count = 0;

    static increment() {
        return ++Counter.count;
    }

    static reset() {
        Counter.count = 0;
    }
}

console.log(Counter.increment()); // Output: 1
console.log(Counter.increment()); // Output: 2
Counter.reset();
console.log(Counter.count);       // Output: 0
```

---

### **Static Methods with `this` Context**

Within static methods, `this` refers to the class itself, not an instance.

```javascript
class Logger {
    static log(message) {
        console.log(`[${this.name}] ${message}`);
    }
}

Logger.log("Static method example."); // Output: [Logger] Static method example.
```

---

### **Common Interview Questions**

1. **What are static methods in JavaScript?**
   - **Answer**: Methods that belong to the class itself and can be accessed without creating an instance of the class.

2. **How do you declare and access a static property in ES2022+?**
   - **Answer**: Use the `static` keyword directly inside the class body:
     ```javascript
     class Example {
         static propertyName = "value";
     }
     console.log(Example.propertyName);
     ```

3. **What happens if you try to access a static method with an instance?**
   - **Answer**: It will throw an error because static methods are not accessible through instances.

4. **Can static methods access instance properties?**
   - **Answer**: No, static methods do not have access to instance-specific properties.

5. **How do you define static methods for utility functionality?**
   - **Answer**: Define methods with `static` and use the class name to call them. For example:
     ```javascript
     class MathUtil {
         static square(num) {
             return num * num;
         }
     }
     console.log(MathUtil.square(4));
     ```

### **Private and Protected Properties and Methods**

### **Introduction**

JavaScript introduced support for truly **private class fields and methods** with the **`#` syntax** in ECMAScript 2022. This allows developers to define properties and methods that cannot be accessed outside the class. Additionally, "protected" properties and methods can be simulated using naming conventions like `_propertyName`.

---

### **Private Properties and Methods**

#### **What are Private Properties and Methods?**

- **Private properties** and **methods** can only be accessed inside the class where they are defined. 
- They are denoted by the `#` prefix.
- They are not accessible by instances of the class or from outside the class.
- This provides true encapsulation, a key concept in object-oriented programming.

---

### **Declaring Private Properties**

#### **Syntax**
```javascript
class ClassName {
    #privateProperty; // Private field declaration
    #privateMethod() { /* Private method */ }
}
```

---

#### **Example: Private Properties**
```javascript
class BankAccount {
    #balance; // Private field

    constructor(initialBalance) {
        this.#balance = initialBalance; // Accessed within the class
    }

    deposit(amount) {
        this.#balance += amount;
        console.log(`Deposited ${amount}. New balance: ${this.#balance}`);
    }

    withdraw(amount) {
        if (amount > this.#balance) {
            console.log("Insufficient funds.");
        } else {
            this.#balance -= amount;
            console.log(`Withdrew ${amount}. New balance: ${this.#balance}`);
        }
    }
}

const account = new BankAccount(100);
account.deposit(50); // Output: Deposited 50. New balance: 150
account.withdraw(30); // Output: Withdrew 30. New balance: 120

// Attempt to access private field
console.log(account.#balance); // Error: Private field '#balance' must be declared in an enclosing class
```

---

### **Private Methods**

Private methods are similar to private properties but are used for encapsulating behavior that is only meant to be used internally within the class.

#### **Example: Private Methods**
```javascript
class User {
    #password;

    constructor(username, password) {
        this.username = username;
        this.#password = password;
    }

    // Private method
    #validatePassword(input) {
        return input === this.#password;
    }

    login(inputPassword) {
        if (this.#validatePassword(inputPassword)) {
            console.log("Login successful!");
        } else {
            console.log("Invalid password.");
        }
    }
}

const user = new User("john_doe", "secure123");
user.login("secure123"); // Output: Login successful!
user.login("wrongPass"); // Output: Invalid password

// Trying to call a private method
// user.#validatePassword("secure123"); // Error: Private field '#validatePassword' must be declared in an enclosing class
```

---

### **Protected Properties and Methods**

#### **What are Protected Properties and Methods?**

- JavaScript does not have a built-in `protected` keyword like some other languages (e.g., Java, C#).
- Developers simulate **protected properties** by using naming conventions (e.g., `_propertyName`).
- These properties are not strictly protected but signal to other developers that they are not meant for public access.

---

#### **Example: Simulating Protected Properties**
```javascript
class Parent {
    constructor(name) {
        this.name = name;
        this._protectedValue = 42; // Naming convention
    }

    showProtectedValue() {
        console.log(`Protected Value: ${this._protectedValue}`);
    }
}

class Child extends Parent {
    incrementProtectedValue() {
        this._protectedValue += 1;
    }
}

const child = new Child("Alice");
child.incrementProtectedValue();
child.showProtectedValue(); // Output: Protected Value: 43

// Conventionally, other developers know not to directly access _protectedValue.
console.log(child._protectedValue); // Output: 43
```

---

### **Combining Private and Public Members**

#### **Example: A Class with Mixed Access Levels**
```javascript
class Car {
    #engineStarted; // Private property

    constructor(brand) {
        this.brand = brand; // Public property
        this.#engineStarted = false;
    }

    startEngine() {
        this.#engineStarted = true;
        console.log(`${this.brand} engine started.`);
    }

    stopEngine() {
        this.#engineStarted = false;
        console.log(`${this.brand} engine stopped.`);
    }

    isEngineRunning() {
        return this.#engineStarted;
    }
}

const car = new Car("Toyota");
car.startEngine(); // Output: Toyota engine started.
console.log(car.isEngineRunning()); // Output: true
car.stopEngine(); // Output: Toyota engine stopped.
console.log(car.isEngineRunning()); // Output: false
```

---

### **Advantages of Private and Protected Members**

1. **Encapsulation**: Helps protect the internal state of the object.
2. **Data Hiding**: Prevents unintended interference from external code.
3. **Improved Code Maintenance**: Clearly separates internal and external interfaces.

---

### **Limitations**

1. **Private fields are inaccessible even for subclasses.**
   - Unlike protected members in other languages, private fields cannot be accessed in derived classes.
   
   **Example:**
   ```javascript
   class Parent {
       #privateValue = 42;
   }

   class Child extends Parent {
       showPrivateValue() {
           // console.log(this.#privateValue); // Error: Private field '#privateValue' is not accessible.
       }
   }
   ```

2. **Cannot Dynamically Add Private Fields**
   - Private fields must be explicitly declared in the class definition and cannot be added dynamically.

---

### **Comparison Table**

| **Feature**            | **Private**                                 | **Protected (Simulated)**             |
|-------------------------|---------------------------------------------|---------------------------------------|
| **Accessibility**       | Only within the class.                     | Accessible in subclasses.            |
| **Implementation**      | Use `#property` or `#method`.              | Use naming conventions like `_prop`. |
| **Encapsulation**       | Fully encapsulated.                        | Partially encapsulated.              |
| **Inheritance**         | Not accessible in derived classes.         | Accessible in derived classes.       |

---

### **Interview Questions on Private and Protected Members**

#### **1. What is the difference between private and protected properties in JavaScript?**
**Answer:**  
- Private properties are declared using the `#` prefix and can only be accessed within the class.
- Protected properties are simulated using naming conventions like `_propertyName` and can be accessed in subclasses.

---

#### **2. Can private fields be accessed in derived classes?**
**Answer:**  
No, private fields are not accessible in derived classes. They are strictly confined to the class where they are defined.

---

#### **3. How do you declare a private field in JavaScript?**
**Answer:**  
Use the `#` prefix before the property name. Example:
```javascript
class Example {
    #privateField;
}
```

---

#### **4. What are the benefits of using private fields over public fields?**
**Answer:**  
- Prevents accidental overwrites or modifications from outside the class.
- Ensures better encapsulation and protects the internal state of objects.

---

#### **5. How can you simulate protected properties in JavaScript?**
**Answer:**  
By using naming conventions like `_propertyName`, which signals to developers that the property is intended to be protected.

---

#### **6. Can private fields be serialized into JSON?**
**Answer:**  
No, private fields are not included in JSON serialization.
```javascript
class Example {
    #privateField = "secret";
    constructor(publicField) {
        this.publicField = publicField;
    }
}
const obj = new Example("visible");
console.log(JSON.stringify(obj)); // Output: {"publicField":"visible"}
```
### **Extending Built-In Classes in JavaScript**

---

### **Introduction**

In JavaScript, classes can extend **built-in classes** like `Array`, `Error`, `Date`, or even `Map`. This allows developers to create custom versions of these classes while still inheriting their native functionality. For example, you could create a specialized array class with additional methods for your specific use case.

---

### **How to Extend Built-In Classes**

To extend a built-in class:
1. Use the `extends` keyword.
2. Add your custom properties or methods.
3. Call the parent class methods when needed using `super()`.

**Syntax:**
```javascript
class CustomClass extends BuiltInClass {
    constructor(args) {
        super(args); // Call the parent constructor
        // Add custom properties or logic
    }

    customMethod() {
        // Custom functionality
    }
}
```

---

### **Example 1: Extending `Array`**

Let’s create a custom array class with an additional method `average()`.

```javascript
class CustomArray extends Array {
    average() {
        return this.reduce((acc, val) => acc + val, 0) / this.length;
    }
}

const numbers = new CustomArray(10, 20, 30, 40);
console.log(numbers.average()); // Output: 25
console.log(numbers instanceof CustomArray); // true
console.log(numbers instanceof Array);       // true
```

#### **Explanation:**
1. `CustomArray` inherits all methods from `Array` (e.g., `push`, `pop`).
2. The `average()` method is added to calculate the average of all elements.
3. `numbers` is an instance of both `CustomArray` and `Array`.

---

### **Example 2: Extending `Error`**

You can extend the `Error` class to create custom error types with additional properties.

```javascript
class CustomError extends Error {
    constructor(message, errorCode) {
        super(message); // Call the Error constructor
        this.name = "CustomError"; // Custom error name
        this.errorCode = errorCode; // Additional property
    }
}

try {
    throw new CustomError("Something went wrong!", 404);
} catch (error) {
    console.log(error.name);      // Output: CustomError
    console.log(error.message);   // Output: Something went wrong!
    console.log(error.errorCode); // Output: 404
}
```

#### **Explanation:**
1. `CustomError` extends `Error` to inherit its methods like `stack` and `message`.
2. Added a custom property `errorCode` for additional context.

---

### **Example 3: Extending `Date`**

You can create a custom date class with extra methods.

```javascript
class CustomDate extends Date {
    getFormattedDate() {
        const day = this.getDate().toString().padStart(2, "0");
        const month = (this.getMonth() + 1).toString().padStart(2, "0");
        const year = this.getFullYear();
        return `${day}-${month}-${year}`;
    }
}

const myDate = new CustomDate("2024-11-28");
console.log(myDate.getFormattedDate()); // Output: 28-11-2024
```

#### **Explanation:**
1. `CustomDate` inherits all methods of the `Date` class (e.g., `getDate`, `getMonth`).
2. Added a `getFormattedDate` method for custom date formatting.

---

### **Important Notes**

1. **Calling `super()`**:  
   When extending a built-in class, the parent constructor (`super()`) **must** be called in the child constructor. This ensures the base class is properly initialized.

   **Example:**
   ```javascript
   class CustomArray extends Array {
       constructor(...args) {
           super(...args); // Initialize the Array class
           this.createdAt = new Date(); // Additional property
       }
   }
   ```

2. **Instanceof Operator**:  
   Instances of a class that extends a built-in class will also pass the `instanceof` check for the parent class.

   ```javascript
   const numbers = new CustomArray(1, 2, 3);
   console.log(numbers instanceof CustomArray); // true
   console.log(numbers instanceof Array);       // true
   ```

3. **Overriding Methods**:  
   You can override built-in methods and provide custom behavior.
   ```javascript
   class CustomArray extends Array {
       push(...args) {
           console.log("Custom push method called!");
           return super.push(...args);
       }
   }

   const arr = new CustomArray();
   arr.push(5); // Output: Custom push method called!
   console.log(arr); // Output: [5]
   ```

---

### **Interview Questions**

#### **1. Why would you extend a built-in class in JavaScript?**  
**Answer:**  
To create specialized versions of built-in objects, adding custom properties or methods while retaining the core functionality of the parent class.

#### **2. What is the purpose of calling `super()` in a child class?**  
**Answer:**  
The `super()` method calls the constructor of the parent class. It is mandatory in a derived class before accessing `this`.

#### **3. Can you override built-in methods in a custom class?**  
**Answer:**  
Yes, you can override methods in a custom class and provide custom behavior. Use `super.methodName()` to call the original method if needed.

---

#### **4. Write a class that extends `Array` and adds a method to find the maximum element.**
**Answer:**
```javascript
class CustomArray extends Array {
    getMax() {
        return Math.max(...this);
    }
}

const numbers = new CustomArray(5, 10, 15, 20);
console.log(numbers.getMax()); // Output: 20
```

---

#### **5. What will this code output?**
```javascript
class CustomError extends Error {
    constructor(message) {
        super(message);
        this.name = "CustomError";
    }
}

try {
    throw new CustomError("Oops!");
} catch (error) {
    console.log(error instanceof CustomError); // ?
    console.log(error instanceof Error);       // ?
}
```
**Answer:**  
- `true` (because `error` is an instance of `CustomError`).
- `true` (because `CustomError` extends `Error`).

---

#### **6. Can you create a class that extends multiple built-in classes?**  
**Answer:**  
No, JavaScript does not support multiple inheritance directly. However, you can use **mixins** to combine functionality from multiple classes.

---

#### **7. How do you extend a class and add new functionality without overriding the parent behavior?**  
**Answer:**  
Use `super.methodName()` to call the parent method and add custom behavior.

**Example:**
```javascript
class CustomArray extends Array {
    push(...args) {
        console.log("Adding elements:", args);
        return super.push(...args); // Call parent method
    }
}
```
