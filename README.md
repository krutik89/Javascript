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

