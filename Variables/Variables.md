# Let, Const and Var

In JavaScript, `let`, `const`, and `var` are all used for declaring variables, but they have some differences in terms
of scope, hoisting, and mutability.

1. **var**:
    - Variables declared with `var` are function-scoped. They are visible throughout the function they are declared in,
      even if they are declared inside a block statement (like `if` or `for`).
    - `var` variables are hoisted to the top of their scope during the compilation phase, which means you can access
      them before they are declared, but they will be `undefined`.
    - `var` allows redeclaration and reassignment of variables within its scope.
    - Example:
      ```javascript
      function example() {
          if (true) {
              var x = 5;
          }
          console.log(x); // 5
      }
      example();
      ```

2. **let**:
    - Variables declared with `let` are block-scoped. They are only accessible within the block they are declared in,
      such as inside a loop or an `if` statement.
    - `let` variables are also hoisted, but unlike `var`, they are not initialized. So, if you try to access them before
      declaration, you'll get a ReferenceError.
    - `let` allows reassignment but not redeclaration within its scope.
    - Example:
      ```javascript
      function example() {
          if (true) {
              let x = 5;
          }
          console.log(x); // ReferenceError: x is not defined
      }
      example();
      ```

3. **const**:
    - Variables declared with `const` are block-scoped like `let`.
    - Unlike `let` and `var`, variables declared with `const` must be initialized during declaration, and their value
      cannot be changed once assigned. However, for objects and arrays, the assigned value cannot be changed, but
      properties of objects or elements of arrays can be modified.
    - Like `let`, `const` variables are also not hoisted and would result in a ReferenceError if accessed before
      declaration.
    - Example:
      ```javascript
      function example() {
          const x = 5;
          x = 6; // TypeError: Assignment to constant variable.
      }
      example();
      ```

In general, it's recommended to use `const` by default, and only use `let` when you need to reassign a variable's
value. `var` is rarely used in modern JavaScript due to its function-scoping behavior and the existence of `let`
and `const`.