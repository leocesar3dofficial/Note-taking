# Debugging

- Check for intermediate values: `console.log('someVariable/function');`
- Clear the console: `console.clear();`

## Recognized primitive data types

- Immutable: Boolean, Null, Undefined, Number, String, Symbol, BigInt
- Mutable: Object

## Check for type

```javascript
let seven = 7;
let three = "3";
console.log(typeof seven); // prints: number
console.log(typeof three); // prints: string
```

## Errors

### Syntax

- Reference error: transposed, missing, or mis-capitalized characters in a variable or function name
- Unexpected token: unclosed parentheses, brackets, braces and quotes
- Mixed usage of single and double quotes: use the backslash (\) escape character
- Use of assignment Operator (=) instead of Equality Operator (== or ===)
- Missing open and closing parenthesis after a function call

### Runtime

- Arguments passed in the wrong order when calling a function: function returns unexpected values
- Off by one errors when using indexing for arrays: console prints index out of range or undefined
- Caution when reinitializing variables inside a loop: may cause an infinite loop
- Prevent infinite loops with a valid terminal condition: this is context based