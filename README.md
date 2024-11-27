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
         

