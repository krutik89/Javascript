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

# **JavaScript Strict Mode: A Complete Guide with Examples**

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


