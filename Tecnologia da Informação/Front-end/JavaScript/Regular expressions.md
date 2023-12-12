# Regular expressions

## Basic test
```javascript
let testStr = "freeCodeCamp";
let testRegex = /Code/; // case sensitive
testRegex.test(testStr); // returns true
```

## Bitwise OR (`|`)
```javascript
let petRegex = /dog|cat|bird|fish/;
```

## Case insensitive
```javascript
let fccRegex = /mystringpattern/i; // i -> insensitive
```

## Extract Matches
### Single occurrence:
```javascript
let result = extractStr.match(/mystringpattern/);
```
### All occurrences:
```javascript
let result = extractStr.match(/mystringpattern/g); // g -> global (all) search flag
```
### Multiple search flags:
```javascript
let result = twinkleStar.match(/twinkle/ig); // can be the other way around -> gi
```

## Wildcard
```javascript
let unRegex (dot or period) = /run./; // returns match word and one more character if it exists
```

## Character classes
### Return character:
```javascript
let bgRegex = /b[aiu]g/; // will match -> bag, big, bug. Can be one or more characters inside the brackets
```
### Return a range of characters or numbers
```javascript
let bgRegex = /[a-e]at/; // using the hyphen character (-)
let alphabetRegex = /[a-z]/gi; // the whole alphabet
let firstLetterIsUppercase = /(?=[A-Z])/;
let myRegex = /[a-z0-9]/ig; // matches all alphabet and numbers, but can be any range of characters and numbers
let longHand = /[A-Za-z0-9_]+/;
let shortHand = /\w+/;
let oppositeOfAlphanumerics = /\W/; // Matches any non-word character. This includes spaces and punctuation, but not underscores
let numbers = /\d/; // d stands for digits
let nonNumbers = /\D/;
let whitespace = /\s/; // shorthand for the character class [\r\t\f\n\v] or carriage return, tab, form feed, and new line characters
let nonWhitespace = /\S/;
```
### Negate:
```javascript
let myRegex = /[^0-9aeiou]/gi; // return everything but numbers and vowels, including spaces and punctuation
```
### Return consecutive characters:
```javascript
let myRegex = /s+/gi; // returns "s", "ss", "SSS", "sssss..."
```
### Find all combinations:
```javascript
let goRegex = /go*/; // May return ["goooooooo"], ["goo"], ["go"], ["g"] or null.
```

## Lazy Matching
Regular expressions are by default greedy, so the match would return the longest possible part of a string.
Lazy match finds the smallest possible part of the string.
### Example:
```javascript
let result = "<h1>Winter is coming</h1>".match(/<h.*?>/); // returns '<h1>'
```

## Match only
### Beginning of the string:
```javascript
let calRegex = /^Cal/; // if "Cal" is in the beginning of the string it will be found
```
### End of the string:
```javascript
let lastRegex = /caboose$/; // "caboose" must be in the end of the string
```

## Combined match
### Example 1
```javascript
let userCheck = /^[a-z][a-z]+\d*$|^[a-z]\d\d+$/i;
```
#### Code explanation
```
^ - start of input
[a-z] - first character is a letter
[a-z]+ - following characters are letters
\d*$ - input ends with 0 or more digits
| - or
^[a-z] - first character is a letter
\d\d+ - following characters are 2 or more digits
$ - end of input
```

### Example 2
```javascript
const userCheck = /^[a-z]([0-9]{2,}|[a-z]+\d*)$/i;
```
#### Code explanation
```
^ - start of input
[a-z] - first character is a letter
[0-9]{2,0} - ends with two or more numbers
| - or
[a-z]+ - has one or more letters next
\d* - and ends with zero or more numbers
$ - end of input
i - ignore case of input
```

## Quantity `{n}`
### Exact count:
```javascript
alert("I'm 12345 years old".match(/\d{5}/)); // "12345"
```
### Range
```javascript
alert("I'm not 12, but 1234 years old".match(/\d{3,5}/)); // "1234"
let result = /Oh{3,6}\sno/.test("Ohhh no"); // has 3 up to 6 repeated h characters
let haRegex = /haz{4,}ah/i; // has 4 or more z character
```
### All or None:
```javascript
let favRegex = /favou?rite/i; // true for "favorite" and "favourite"
```

## Lookahead
### Positive: `?=` 
### Negative: `?!`
### Example:
```javascript
let pwRegex = /(?=\w{6,})(?=\D*\d{2})/; // match passwords that are greater than 5 characters long, and have two consecutive digits
```

## Mixed Grouping of Characters
```javascript
let testRegex = /P(engu|umpk)in/; // true for "Pumpkin" and "Penguin"
let myRegex = /(Franklin|Eleanor).*Roosevelt/; // true for Franklin or Eleanor Roosevelt. .* accepts any middle name
```

## Capture Groups
### Basic
#### Example 1
```javascript
let repeatNum = "42 42 42";
let reRegex = /^(\d+)\s\1\s\1$/;
```
#### Example 2
```javascript
let testString = "test test test test test test";
let reRegex = /(test)(\s)\1\2\1/g;
```
#### Example 3
```javascript
let testString = "test test test";
let reRegex = /(test)(\s)\1\2\1/; // the number after the backslash means number of repetitions
```

### Search and Replace
#### Example 1
```javascript
let wrongText = "The sky is silver.";
let silverRegex = /silver/;
wrongText.replace(silverRegex, "blue"); // returns "The sky is blue."
```
#### Example 2
```javascript
"Code Camp".replace(/(\w+)\s(\w+)/, '$2 $1'); // returns "Camp Code"
```
#### Example 3
```javascript
let str = "one two three";
let fixRegex = /(\w+)\s(\w+)\s(\w+)/; // Change this line
let replaceText = "$3 $2 $1"; // Change this line
let result = str.replace

(fixRegex, replaceText); // returns "three two one"
```

### Remove Whitespace from Start and End
Work the same way as `String.prototype.trim()`
#### Example
```javascript
let hello = "   Hello, World!  ";
let wsRegex = /^\s+|\s+$/g;
let result = hello.replace(wsRegex, ""); // returns "Hello, World!"
```