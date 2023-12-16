# Basic JavaScript

## Comments

- **In-line**
  ```javascript
  // This is an in-line comment.
  ```
- **Multi-line**
  ```javascript
  /* This is a
     multi-line comment */
  ```

## Variables

- **Declaration**
  ```javascript
  var myVar;
  ```
- **Initializing**
  ```javascript
  var myVar = 0;
  ```
- **Uninitialized**
  - Declared returns: `undefined`
  - Mathematical operation returns: `NaN`
  - Concatenate string returns: `"undefined"`
- **Assignment**
  ```javascript
  myVar = 5;
  ```
- **Passing value**
  ```javascript
  myNum = myVar;
  ```
- **String**
  ```javascript
  var myString = 'A string';
  ```
- **Naming**: camelCase

## Keywords

- **var**
  - Can be redeclared without throwing an error
- **let**
  - Can only be declared once; else it throws an error
- **const**
  - Read-only
  - Has all the features of the `let` keyword
  - Naming: uppercase

## Scope

- **Global**
  - Defined outside of a function block
  - Declared with the `var` keyword
- **Local**
  - Defined inside of a function block
  - Local variable takes precedence over the global variable

## Mathematical Operations

- **Addition**: `5 + 10;`
  - Augmented: `myVar += 5;`
- **Subtraction**: `10 - 5;`
  - Augmented: `myVar -= 5;`
- **Multiply**: `2 * 5;`
  - Augmented: `myVar *= 5;`
- **Division**: `10 / 5;`
  - Augmented: `myVar /= 5;`
- **Remainder**
  - Incorrectly referred to as the modulus operator
  - Similar to modulus but doesn't work properly with negative numbers
  - `5 % 2 = 1`
  - `17 % 2 = 1` (17 is Odd)
  - `48 % 2 = 0` (48 is Even)
- **Increment**: `i++;`
- **Decrement**: `i--;`
- **Decimal or floating point**: `1.5;`

## Data Types

- **String**

  - String values are immutable but can be reassigned
  - **Escaping**
    - Literal quotes: `\"`
    - Backslash: `\\`
    - Newline: `\n`
    - Carriage return: `\r`
    - Tab: `\t`
    - Word boundary: `\b`
    - Form feed: `\f`
  - **Concatenation**
    ```javascript
    const ourStr = 'I come first. ' + 'I come second.';
    ourStr += 'I come second.';
    const ourStr =
      'Hello, our name is ' + someStringVariable + ', how are you?';
    ourStr += anAdjective;
    ```
  - **Basic String Manipulation**
    - Length: `someString.length`
    - Character index
      ```javascript
      firstLetter = firstName[0];
      lastLetter = firstName[firstName.length - 1];
      thirdToLastLetter = firstName[firstName.length - 3];
      ```

- **Array**

  - **Simple**: `const sandwich = ["peanut butter", "jelly", "bread"];`
  - **Nested**: `const teams = [["Bulls", 23], ["White Sox", 45]];`
  - **Indexes**
    - **Access Data**
      - Simple: `const data = array[1];`
      - Multi-Dimensional
        ```javascript
        const nestedSubarray = arr[3][0];
        const element = arr[3][0][1];
        ```
    - **Modify Data**: `ourArray[0] = 15;`
    - **Append Data**
      - To the beginning: `ourArray.unshift("Happy");`
      - To the end: `arr1.push(4);`
    - **Remove Data**
      - The first element: `ourArray.shift();`
      - The last element: `threeArr.pop();`

- **Boolean**
  - May only be one of two values: `true` or `false`

## Functions

- **Functional Programming**: All about creating and using non-mutating functions
- **Basics**
  ```javascript
  function functionName(arg1, arg2, ...args) {
    return 'Hello World' + arg1;
  }
  ```
- No specified return value: The function processes the inner code, but the returned value is `undefined`
- **Assignment with a Returned Value**: `ourSum = sum(5, 12);`

## Data Structure

- **Queue**
  ```javascript
  function nextInLine(arr, item) {
    arr.push(item);
    const removed = arr.shift();
    return removed;
  }
  ```

## Statements

- **Conditionals**

  - **Basics**
    ```javascript
    function test(myCondition) {
      if (myCondition) {
        return 'It was true';
      }
      return 'It was false';
    }
    ```
  - **Else Statement**
    ```javascript
    if (num > 10) {
      return 'Bigger than 10';
    } else {
      return '10 or Less';
    }
    ```
  - **Else If Statements**
    ```javascript
    if (num > 15) {
      return 'Bigger than 15';
    } else if (num < 5) {
      return 'Smaller than 5';
    } else {
      return 'Between 5 and 15';
    }
    ```
  - **Chaining If Else Statements**
    ```javascript
    if (condition1) {
      statement1;
    } else if (condition2) {
      statement2;
    } else if (condition3) {
      statement3;
      // ...
    } else {
      statementN;
    }
    ```
  - **Switch**
    - Used to replace chaining if-else statements
    - **Basics**
      ```javascript
      switch (lowercaseLetter) {
        case 'a':
          console.log('A');
          break;
        case 'b':
          console.log('B');
          break;
        default:
          defaultStatement;
          break;
      }
      ```
    - **Multiple Options**
      ```javascript
      switch (val) {
        case 1:
        case 2:
        case 3:
          result = '1, 2, or 3';
          break;
        case 4:
          result = '4 alone';
      }
      ```
  - **Ternary Operator**
    - **Basic**
      ```javascript
      function findGreater(a, b) {
        return a > b ? 'a is greater' : 'b is greater or equal';
      }
      ```
    - **Multiple**
      ```javascript
      function findGreaterOrEqual(a, b) {
        return a === b
          ? 'a and b are equal'
          : a > b
          ? 'a is greater'
          : 'b is greater';
      }
      ```

- **Comparison Operators**

  - **Equality**
    - Normal: `==` (compares values)
    - Strict: `===` (compares values and types)
  - **Inequality**: `!=` or `!==`
  - **Greater Than**: `>`
  - **Greater or Equal Than**: `>=`
  - **Less Than**: `<`
  - **Less or Equal Than**: `<=`

- **Logical Operators**
  - **And**: `&&` (true if both operands are true)
  - **Or**: `||` (true if either of the operands is true)

## Loops

- **While**
  ```javascript
  while (i < 5) {
    ourArray.push(i);
    i++;
  }
  ```
- **For**
  - **Basic**
    ```javascript
    for (let i = 0; i < 5; i++) {
      ourArray.push(i);
    }
    ```
  - **Odd Numbers**
    ```javascript
    for (let i = 0; i < 10; i += 2) {
      ourArray.push(i);
    }
    ```
  - **Count Backwards**
    ```javascript
    for (let i = 10; i > 0; i -= 2) {
      ourArray.push(i);
    }
    ```
  - **Nested**
    ```javascript
    for (let i = 0; i < arr.length; i++) {
      for (let j = 0; j < arr[i].length; j++) {
        console.log(arr[i][j]);
      }
    }
    ```
- **Do While**
  ```javascript
  let i = 0;
  do {
    ourArray.push(i);
    i++;
  } while (i < 5);
  ```

## Algorithms

- **Recursion**

  - **Basic**
    ```javascript
    function multiply(arr, n) {
      if (n <= 0) {
        return 1;
      } else {
        return multiply(arr, n - 1) * arr[n - 1];
      }
    }
    ```
  - **Countdown**
    ```javascript
    function countdown(n) {
      if (n < 1) {
        return [];
      } else {
        const arr = countdown(n - 1);
        arr.unshift(n);
        return arr;
      }
    }
    ```
  - **Range of Numbers**
    ```javascript
    function rangeOfNumbers(startNum, endNum) {
      if (endNum < startNum) {
        return [];
      } else {
        const numbers = rangeOfNumbers(startNum, endNum - 1);
        numbers.push(endNum);
        return numbers;
      }
    }
    ```

- **Random Numbers**

  - Decimal number between 0 (inclusive) and 1 (exclusive): `Math.random()`
  - Whole Numbers: `Math.floor(Math.random() * 20);` (whole number between 0 and 19)
  - Whole Numbers within a Range: `Math.floor(Math.random() * (max - min + 1)) + min`

- **Parsing**

  - String to Integer: `parseInt("007");`
  - String to Float: `parseFloat()`
    - **Radix**
      - Base of the number in the string
      - Integer between 2 and 36
      - `parseInt("11", 2);` (base 2 or binary system)

- **Functional Programming**

  - **Currying a Function**

    - It restructures a function so it takes one argument, then returns another function that takes the next argument, and so on.
    - **Example 1**

      ```javascript
      function curried(x) {
        return function (y) {
          return x + y;
        };
      }

      // or use arrow function
      const curried = (x) => (y) => x + y;

      // use
      curried(1)(2); // returns 3

      // another use
      const funcForY = curried(1);
      console.log(funcForY(2)); // 3
      ```

    - **Example 2**

      ```javascript
      function add(x) {
        return function (y) {
          return function (z) {
            return x + y + z;
          };
        };
      }

      // or use arrow function
      function add(x) {
        return (y) => (z) => x + y + z;
      }

      // use
      add(10)(20)(30); // 60
      ```

  - **Partial Application**

    - Apply a few arguments to a function and return another function that is applied to more arguments.
    - **Example**

      ```javascript
      function impartial(x, y, z) {
        return x + y + z;
      }

      const partialFn = impartial.bind(this, 1, 2);
      partialFn(10); // 13
      ```
