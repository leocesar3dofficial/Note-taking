# ES6

## Prevent Object Mutation
```javascript
Object.freeze(obj);
```

## Arrow Functions
### Example with function body
```javascript
const myFunc = () => {
  const myVar = "value";
  return myVar;
}
```

### One-liner
```javascript
const myFunc = () => "value";
```

### With parameters
```javascript
const doubler = (item) => item * 2;
const doubler = item => item * 2; // With a single parameter, the parentheses enclosing the parameter can be omitted
const multiplier = (item, multi) => item * multi;
```

## Default Parameters for Functions
### Basic
```javascript
const greeting = (name = "Anonymous") => "Hello " + name;
```

### Rest Parameter
```javascript
function howMany(...args) {
  return "You have passed " + args.length + " arguments.";
}
```

## Spread Operator
### Evaluate Arrays In-Place
#### Example
```javascript
const arr = [6, 89, 3, 45];
const maximus = Math.max(...arr); // ...arr returns an unpacked array (spreads the array)
```

## Destructuring
### Extract Values from Objects
#### Before (ES5)
```javascript
const user = { name: 'John Doe', age: 34 };
const name = user.name;
const age = user.age;
```

#### After (ES6)
```javascript
const user = { name: 'John Doe', age: 34 };
const { name, age } = user;
```

### Assign Variables from Objects
```javascript
const { name: userName, age: userAge } = user;
const { johnDoe: { age: userAge, email: userEmail }} = user;
```

### Assign Variables from Arrays
```javascript
const [a, b] = [1, 2, 3, 4, 5, 6]; // a and b as 1, 2
const [a, b,,, c] = [1, 2, 3, 4, 5, 6]; // a, b, and c as 1, 2, 5
```

### From Rest Parameter to Reassign Array Elements
```javascript
const [a, b, ...arr] = [1, 2, 3, 4, 5, 7]; // Results in 1, 2 and [3, 4, 5, 7]
```

### Pass an Object as a Function's Parameters
#### Example 1
```javascript
const profileUpdate = (profileData) => {
  const { name, age, nationality, location } = profileData;
}
```

#### Example 2
```javascript
const profileUpdate = ({ name, age, nationality, location }) => {}
```

## Strings using Template Literals
### Example
```javascript
const greeting = `Hello, my name is ${person.name}!
I am ${person.age} years old.`;
```

### No need for inserting \n within strings

## Object Property Shorthand
### Write Concise Object Literal Declarations
#### Before (ES5)
```javascript
const getMousePosition = (x, y) => ({
  x: x,
  y: y
});
```

#### After (ES6)
```javascript
const getMousePosition = (x, y) => ({ x, y });
```

## Concise Declarative Functions
#### Before (ES5)
```javascript
const person = {
  name: "Taylor",
  sayHello: function() {
    return `Hello! My name is ${this.name}.`;
  }
};
```

#### After (ES6)
```javascript
const person = {
  name: "Taylor",
  sayHello() {
    return `Hello! My name is ${this.name}.`;
  }
};
```

## Constructor Function using class syntax
#### Before (ES5)
```javascript
var SpaceShuttle = function(targetPlanet){
  this.targetPlanet = targetPlanet;
}
var zeus = new SpaceShuttle('Jupiter');
```

#### After (ES6)
```javascript
class SpaceShuttle {
  constructor(targetPlanet) {
    this.targetPlanet = targetPlanet;
  }
}
const zeus = new SpaceShuttle('Jupiter');
```

### Class names convention: UpperCamelCase

## Getters and setters
```javascript
class Book {
  constructor(author) {
    this._author = author;
  }

  // Getter
  get writer() {
    return this._author;
  }

  // Setter
  set writer(updatedAuthor) {
    this._author = updatedAuthor;
  }
}

const novel = new Book('anonymous');
console.log(novel.writer);
novel.writer = 'newAuthor';
console.log(novel.writer);

## Module Script
In HTML file: `<script type="module" src="filename.js"></script>`

### Export
#### Single function
```javascript
export { add };
```

#### Multiple functions
```javascript
export { add, subtract };
```

#### Fallback
Cannot use `export default` with `var`, `let`, or `const`

##### Named function
```javascript
export default function add(x, y) {
  return x + y;
}
```

##### Anonymous function
```javascript
export default function(x, y) {
  return x + y;
}
```

### Import
#### Single
```javascript
import { add } from './math_functions.js';
```

#### Multiple
```javascript
import { add, subtract } from './math_functions.js';
```

#### Everything
```javascript
import * as myMathModule from "./math_functions.js";
```

#### Default
```javascript
import defaultExport from "./math_functions.js";
```

## Promise
### Basic
```javascript
const myPromise = new Promise((resolve, reject) => {});
```

### With resolve and reject
```javascript
const myPromise = new Promise((resolve, reject) => {
  if(condition here) {
    resolve("Promise was fulfilled");
  } else {
    reject("Promise was rejected");
  }
});
```

### Fulfilled
```javascript
myPromise.then(result => {});
```

### Rejected
```javascript
myPromise.catch(error => {});
```