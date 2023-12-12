# Intermediate Algorithm Scripting

## Sum All Numbers in a Range

### Solution 1
```javascript
function sumAll(arr) {
  let max = Math.max(arr[0], arr[1]);
  let min = Math.min(arr[0], arr[1]);
  let sumBetween = 0;
  for (let i = min; i <= max; i++) {
    sumBetween += i;
  }
  return sumBetween;
}

sumAll([1, 4]);
```

### Solution 2
```javascript
const sumAll = arr => {
  // Buckle up everything to one!
  const startNum = arr[0];
  const endNum = arr[1];

  // Get the count of numbers between the two numbers by subtracting them and add 1 to the absolute value.
  // ex. There are |1-4| + 1 = 4, (1, 2, 3, 4), 4 numbers between 1 and 4.
  const numCount = Math.abs(startNum - endNum) + 1;

  // Using Arithmetic Progression summing formula
  const sum = ((startNum + endNum) * numCount) / 2;
  return sum;
};
```

### Solution 3
```javascript
function sumAll(arr) {
  const [first, last] = [...arr].sort((a, b) => a - b);
  return first !== last
    ? first + sumAll([first + 1, last])
    : first;
}

sumAll([1, 4]);
```

## Diff Two Arrays

### Solution 1
```javascript
function diffArray(arr1, arr2) {
  const newArr = [];

  function onlyInFirst(first, second) {
    // Looping through an array to find elements that don't exist in another array
    for (let i = 0; i < first.length; i++) {
      if (second.indexOf(first[i]) === -1) {
        // Pushing the elements unique to first to newArr
        newArr.push(first[i]);
      }
    }
  }

  onlyInFirst(arr1, arr2);
  onlyInFirst(arr2, arr1);

  return newArr;
}
```

### Solution 2
```javascript
function diffArray(arr1, arr2) {
  return arr1
    .concat(arr2)
    .filter(item => !arr1.includes(item) || !arr2.includes(item));
}
```

### Solution 3
```javascript
function diffArray(arr1, arr2) {
  return [...diff(arr1, arr2), ...diff(arr2, arr1)];

  function diff(a, b) {
    return a.filter(item => b.indexOf(item) === -1);
  }
}
```

## Seek and Destroy

```javascript
// destroyer([1, 2, 3, 1, 2, 3], 2, 3); return [1, 1]
```

### Solution 1
```javascript
function destroyer(arr) {
  const valsToRemove = Object.values(arguments).slice(1);
  const filteredArray = [];

  for (let i = 0; i < arr.length; i++) {
    let removeElement = false;
    for (let j = 0; j < valsToRemove.length; j++) {
      if (arr[i] === valsToRemove[j]) {
        removeElement = true;
      }
    }
    if (!removeElement) {
      filteredArray.push(arr[i]);
    }
  }
  return filteredArray;
}
```

### Solution 2
```javascript
function destroyer(arr) {
  const valsToRemove = Array.from(arguments).slice(1);
  return arr.filter(function(val) {
    return !valsToRemove.includes(val);
  });
}
```

### Solution 3
```javascript
function destroyer(arr, ...valsToRemove) {
  return arr.filter(elem => !valsToRemove.includes(elem));
}
```

## Wherefore art thou

### Description
Will take an array for the first argument and return an array with all the objects that match all the properties and values in the Object passed as the second parameter.

### Usage
```javascript
whatIsInAName(
  [
    { first: "Romeo", last: "Montague" },
    { first: "Mercutio", last: null },
    { first: "Tybalt", last: "Capulet" }
  ],
  { last: "Capulet" }
);
```

### Solution 1
```javascript
function whatIsInAName(collection, source) {
  const sourceKeys = Object.keys(source);

  // filter the collection
  return collection.filter(obj => {
    for (let i = 0; i < sourceKeys.length; i++) {
      if (!obj.hasOwnProperty(sourceKeys[i]) ||
          obj[sourceKeys[i]] !== source[sourceKeys[i]]) {
        return false;
      }
    }
    return true;
  });
}
```

### Solution 2
```javascript
function whatIsInAName(collection, source) {
  const sourceKeys = Object.keys(source);

  return collection
    .filter(obj => sourceKeys
                     .every(key => obj.hasOwnProperty(key) &&
                         obj[key] === source[key]));
}
```

### Solution 3
```javascript
function whatIsInAName(collection, source) {
  const sourceKeys = Object.keys(source);

  // filter the collection
  return collection.filter(obj => sourceKeys
      .map(key => obj.hasOwnProperty(key) && obj[key] === source[key])
      .reduce((a, b) => a && b));
}
```

## Spinal Tap Case

### Description
It's a URL slug, but it also splits capitalized words.

### Solution 1
```javascript
function spinalCase(str) {
  // Create a variable for the white space and underscores.
  var regex = /\s+|_+/g;

  // Replace low-upper case to low-space-uppercase
  str = str.replace(/([a-z])([A-Z])/g, "$1 $2");

  // Replace space and underscore with -
  return str.replace(regex, "-").toLowerCase();
}
```

### Solution 2
```javascript
function spinalCase(str) {
  // Replace low-upper case to low-space-uppercase
  str = str.replace(/([a-z])([A-Z])/g, "$1 $2");
  // Split on whitespace and underscores and join with dash
  return str
    .toLowerCase()
    .split(/(?:_| )+/)
    .join("-");
}
```

### Solution 3
```javascript
function spinalCase(str) {
  return str
    .split(/\s|_|(?=[A-Z])/)
    .join("-")
    .toLowerCase();
}
```

## Pig Latin

### Description
Pig Latin takes the first consonant (or consonant cluster) of an English word, moves it to the end of the word, and suffixes an “ay”. If a word begins with a vowel you just add “way” to the end.

### Usage
```javascript
translatePigLatin("consonant"); // return "onsonantcay"
```

### Solution 1
```javascript
function translatePigLatin(str) {
  let consonantRegex =

 /^[^aeiou]+/;
  let myConsonants = str.match(consonantRegex);
  return myConsonants !== null
    ? str
        .replace(consonantRegex, "")
        .concat(myConsonants)
        .concat("ay")
    : str.concat("way");
}
```

### Solution 2
```javascript
function translatePigLatin(str) {
  return str
    .replace(/^[aeiou]\w*/, "$&way")
    .replace(/(^[^aeiou]+)(\w*)/, "$2$1ay");
}
```

### Solution 3
```javascript
function translatePigLatin(str, charPos = 0) {
  return ['a', 'e', 'i', 'o', 'u'].includes(str[0])
    ? str + (charPos === 0 ? 'way' : 'ay')
    : charPos === str.length
      ? str + 'ay'
      : translatePigLatin(str.slice(1) + str[0], charPos + 1);
}
```

## Search and Replace

**Description:** Takes a sentence, then search for a word in it and replaces it for a new one while preserving the uppercase if there is one.

**Usage:**
```javascript
myReplace("A quick brown fox jumped over the lazy dog", "jumped", "leaped");
// return "A quick brown fox leaped over the lazy dog"
```

### Solution 1
```javascript
function myReplace(str, before, after) {
  const strArr = str.split(" ");
  const [wordToReplace] = strArr.filter(item => item === before);
  const replacement = wordToReplace[0] === wordToReplace[0].toUpperCase()
    ? after[0].toUpperCase() + after.slice(1)
    : after[0].toLowerCase() + after.slice(1);
  return strArr.map(item => (item === before ? replacement : item)).join(" ");
}
```

### Solution 2
```javascript
function myReplace(str, before, after) {
  // Check if the first character of the argument "before" is a capital or lowercase letter and
  // change the first character of the argument "after" to match the case
  if (/^[A-Z]/.test(before)) {
    after = after[0].toUpperCase() + after.substring(1);
  } else {
    after = after[0].toLowerCase() + after.substring(1);
  }

  // return the string with the argument "before" replaced by argument "after" (with correct case)
  return str.replace(before, after);
}
```

### Solution 3
```javascript
function myReplace(str, before, after) {
  // Find the index where "before" is on the string
  var index = str.indexOf(before);
  // Check to see if the first letter is uppercase or not
  if (str[index] === str[index].toUpperCase()) {
    // Change the "after" word to be capitalized before we use it.
    after = after.charAt(0).toUpperCase() + after.slice(1);
  } else {
    // Change the "after" word to be uncapitalized before we use it.
    after = after.charAt(0).toLowerCase() + after.slice(1);
  }
  // Now replace the original str with the edited one.
  str = str.replace(before, after);

  return str;
}
```

## DNA Pairing

**Description:** There are four potential characters that exist in DNA: “A”, “T”, “G”, and “C”. “A” and “T” are always paired together, and “G” and “C” are always paired together.

**Usage:**
```javascript
pairElement("ATCGA") // return [["A","T"],["T","A"],["C","G"],["G","C"],["A","T"]]
```

### Solution 1
```javascript
function pairElement(str) {
  // Function to match each character with the base pair
  let matchWithBasePair = function(char, pairedArray) {
    switch (char) {
      case "A":
        pairedArray.push(["A", "T"]);
        break;
      case "T":
        pairedArray.push(["T", "A"]);
        break;
      case "C":
        pairedArray.push(["C", "G"]);
        break;
      case "G":
        pairedArray.push(["G", "C"]);
        break;
    }
  };

  // Find a pair for every character in the string
  const paired = [];
  for (let i = 0; i < str.length; i++) {
    matchWithBasePair(str[i], paired);
  }

  return paired;
}
```

### Solution 2
```javascript
function pairElement(str) {
  // create an object for pair lookup
  var pairs = {
    A: "T",
    T: "A",
    C: "G",
    G: "C"
  };
  // split the string into an array of characters
  var arr = str.split("");
  // map each character to an array of character and matching pair
  return arr.map(x => [x, pairs[x]]);
}
```

## Missing letters

**Description:** Find the missing letter in the passed letter range and return it. If all letters are present in the range, return undefined.

**Usage:**
```javascript
fearNotLetter("abce"); // return "d"
```

### Solution 1
```javascript
function fearNotLetter(str) {
  for (let i = 1; i < str.length; ++i) {
    if (str.charCodeAt(i) - str.charCodeAt(i - 1) > 1) {
      return String.fromCharCode(str.charCodeAt(i - 1) + 1);
    }
  }
}
```

### Solution 2
```javascript
function fearNotLetter(str) {
  let currCharCode = str.charCodeAt(0);
  let missing = undefined;

  str.split("").forEach(letter => {
    if (letter.charCodeAt(0) === currCharCode) {
      currCharCode++;
    } else {
      missing = String.fromCharCode(currCharCode);
    }
  });

  return missing;
}
```

## Sorted Union

**Description:** Return a new array of unique values from two original arrays in the order they show up. So there is no sorting required, and there shouldn’t be any duplicates.

**Usage:**
```javascript
uniteUnique([1, 3, 2], [5, 2, 1, 4], [2, 1]); // return [1, 3, 2, 5, 4]
```

### Solution 1
```javascript
function uniteUnique(...arr) {
  return [...new Set(arr.flat())];
}
```

### Solution 2
```javascript
function uniteUnique() {
  return [...arguments]
    .flat()
    .filter((item, ind, arr) => arr.indexOf(item) === ind);
}
```

## Convert HTML Entities (basic search and replace)

**Description:** Convert the characters &, <, >, " (double quote), and ' (apostrophe), in a string to their corresponding HTML entities.

**Usage:**
```javascript
convertHTML("Dolce & Gabbana") // return Dolce &amp; Gabbana
```

### Solution 1
```javascript
function convertHTML(str) {
  // Use Object Lookup to declare as many HTML entities as needed.
  const htmlEntities = {
    "&": "&amp;",
    "<": "&lt;",
    ">": "&gt;",
    '"': "&quot;",
    "'": "&apos;"
  };
  // Using a regex, replace characters with their corresponding HTML entities
  return str.replace(/([&<>\"'])/g, match => htmlEntities[match]);
}
```

### Solution 2
```javascript
function convertHTML(str) {
  // Use Object Lookup to declare as many HTML entities as needed.
  const htmlEntities = {
    "&": "&amp;",
    "<": "&lt;",
    ">": "&gt;",
    '"': "&quot;",
    "'": "&apos;"
  };
  // Use the map function to return a filtered string with all entities changed automatically.
  return str
    .split("")
    .map(entity => htmlEntities[entity] || entity

)
    .join("");
}
```

### Solution 3
```javascript
function convertHTML(str) {
  // Use Object Lookup to declare as many HTML entities as needed.
  const htmlEntities = {
    "&": "&amp;",
    "<": "&lt;",
    ">": "&gt;",
    '"': "&quot;",
    "'": "&apos;"
  };
  // Use map function to return a filtered string with all entities changed automatically.
  return str
    .split("")
    .map(entity => htmlEntities[entity] || entity)
    .join("");
}
```

## Sum All Odd Fibonacci Numbers

### Description
a) Given a positive integer num, return the sum of all odd Fibonacci numbers that are less than or equal to num.
The first two numbers in the Fibonacci sequence are 1 and 1.
Every additional number in the sequence is the sum of the two previous numbers.
The first six numbers of the Fibonacci sequence are 1, 1, 2, 3, 5, and 8.
For example, `sumFibs(10)` should return 10 because all odd Fibonacci numbers less than or equal to 10 are 1, 1, 3, and 5.
b) Gather all the Fibonacci numbers and then check for the odd ones.
Once you get the odd ones then you will add them all.
The last number should be the number given as a parameter if it actually happens to be an odd Fibonacci number.

### Solution 1
```javascript
function sumFibs(num) {
  let prevNumber = 0;
  let currNumber = 1;
  let result = 0;
  while (currNumber <= num) {
    if (currNumber % 2 !== 0) {
      result += currNumber;
    }
    currNumber += prevNumber;
    prevNumber = currNumber - prevNumber;
  }
  return result;
}
```

### Solution 2
```javascript
function sumFibs(num) {
  // Perform checks for the validity of the input
  if (num <= 0) return 0;

  // Create an array of fib numbers till num
  const arrFib = [1, 1];
  let nextFib = 0;

  // We put the new Fibonacci numbers to the front so we
  // don't need to calculate the length of the array on each
  // iteration
  while ((nextFib = arrFib[0] + arrFib[1]) <= num) {
    arrFib.unshift(nextFib);
  }

  // We filter the array to get the odd numbers and reduce them to get their sum.
  return arrFib.filter(x => x % 2 != 0).reduce((a, b) => a + b);
}
```

### Solution 3
```javascript
function sumFibs(num) {
  // Every third Fibonacci number is even
  //   and the rest are odd
  let f0 = 0;
  let f1 = 1;
  let f2 = 1;

  // Generate triples until num is reached
  let sum = 0;
  while (f1 <= num) {
    // Update sum
    sum += f1;
    if (f2 <= num) sum += f2;

    // Compute next three Fibonacci numbers
    [f0, f1] = [f1 + f2, f2 + (f1 + f2)];
    f2 = f0 + f1;
  }

  return sum;
}
```

## Sum All Primes

### Solution 1
```javascript
function sumPrimes(num) {
  // Helper function to check primality
  function isPrime(num) {
    for (let i = 2; i <= Math.sqrt(num); i++) {
      if (num % i == 0)
        return false;
    }
    return true;
  }

  // Check all numbers for primality
  let sum = 0;
  for (let i = 2; i <= num; i++) {
    if (isPrime(i))
      sum += i;
  }
  return sum;
}
```

### Solution 2
```javascript
function sumPrimes(num) {
  // Check all numbers for primality
  let primes = [];
  for (let i = 2; i <= num; i++) {
    if (primes.every((prime) => i % prime !== 0))
      primes.push(i);
  }
  return primes.reduce((sum, prime) => sum + prime, 0);
}
```

### Solution 3
```javascript
function sumPrimes(num) {
  // Prime number sieve
  let isPrime = Array(num + 1).fill(true);
  // 0 and 1 are not prime
  isPrime[0] = false;
  isPrime[1] = false;
  for (let i = 2; i <= Math.sqrt(num); i++) {
    if (isPrime[i]) {
      // i has not been marked false -- it is prime
      for (let j = i * i; j <= num; j += i)
        isPrime[j] = false;
    }
  }

  // Sum all values still marked prime
  return isPrime.reduce(
    (sum, prime, index) => prime ? sum + index : sum, 0
  );
}
```

## Smallest Common Multiple

### Description
The smallest common multiple between two numbers is the smallest number that both numbers can divide into evenly.
This concept can be extended to more than two numbers as well.

### Solution 1
```javascript
function smallestCommons(arr) {
  // Setup
  const [min, max] = arr.sort((a, b) => a - b);
  const range = Array(max - min + 1)
    .fill(0)
    .map((_, i) => i + min);
  // Largest possible value for SCM
  const upperBound = range.reduce((prod, curr) => prod * curr);
  // Test all multiples of 'max'
  for (let multiple = max; multiple <= upperBound; multiple += max) {
    // Check if every value in range divides 'multiple'
    const divisible = range.every((value) => multiple % value === 0);
    if (divisible) {
      return multiple;
    }
  }
}
```

### Solution 2
```javascript
function smallestCommons(arr) {
  // Setup
  const [min, max] = arr.sort((a, b) => a - b);
  const range = Array(max - min + 1)
    .fill(0)
    .map((_, i) => i + min);
  // GCD of two numbers
  // https://en.wikipedia.org/wiki/Greatest_common_divisor#Euclid's_algorithm
  const gcd = (a, b) => (b === 0) ? a : gcd(b, a % b);
  // LCM of two numbers
  // https://en.wikipedia.org/wiki/Least_common_multiple#Using_the_greatest_common_divisor
  const lcm = (a, b) => a * b / gcd(a, b);
  // LCM of multiple numbers
  // https://en.wikipedia.org/wiki/Least_common_multiple#Other
  return range.reduce((multiple, curr) => lcm(multiple, curr));
}
```

### Solution 3
```javascript
function smallestCommons(arr) {
  // Setup
  const [min, max] = arr.sort((a, b) => a - b);
  const numberDivisors = max - min + 1;
  // Largest possible value for SCM
  let upperBound = 1;
  for (let i = min; i <= max;

 i++) {
    upperBound *= i;
  }
  // Test all multiples of 'max'
  for (let multiple = max; multiple <= upperBound; multiple += max) {
    // Check if every value in range divides 'multiple'
    let divisorCount = 0;
    for (let i = min; i <= max; i++) {
      // Count divisors
      if (multiple % i === 0) {
        divisorCount += 1;
      }
    }
    if (divisorCount === numberDivisors) {
      return multiple;
    }
  }
}
```

### Drop it
**Description:**
Given the array `arr`, iterate through and remove each element starting from the first element (the 0 index) until the function `func` returns true when the iterated element is passed through it. Then return the rest of the array once the condition is satisfied; otherwise, `arr` should be returned as an empty array.

**Usage:**
```javascript
dropElements([1, 2, 3, 4], function(n) {return n >= 3;}) // return [3, 4]
```

**Solution 1:**
```javascript
function dropElements(arr, func) {
  let sliceIndex = arr.findIndex(func);
  return arr.slice(sliceIndex >= 0 ? sliceIndex : arr.length);
}

// test here
dropElements([1, 2, 3, 4], function(n) {
  return n >= 3;
});
```

**Solution 2:**
```javascript
function dropElements(arr, func) {
  while (arr.length > 0 && !func(arr[0])) {
    arr.shift();
  }
  return arr;
}

// test here
dropElements([1, 2, 3, 4], function(n) {
  return n >= 3;
});
```

**Solution 3:**
```javascript
function dropElements(arr, func) {
  // drop them elements.
  let originalLen = arr.length;
  for (let i = 0; i < originalLen; i++) {
    if (func(arr[0])) {
      break;
    } else {
      arr.shift();
    }
  }
  return arr;
}

// test here
dropElements([1, 2, 3, 4], function(n) {
  return n >= 3;
});
```

### Steamroller
**Description:**
Flatten a nested array. You must account for varying levels of nesting.

**Usage:**
```javascript
steamrollArray([1, [2], [3, [[4]]]]) // return [1, 2, 3, 4]
steamrollArray([[["a"]], [["b"]]]) // return [1, 2, 3, 4]
```

**Solution 1:**
```javascript
function steamrollArray(arr) {
  const flat = [].concat(...arr);
  return flat.some(Array.isArray) ? steamrollArray(flat) : flat;
}
```

**Solution 2:**
```javascript
function steamrollArray(val, flatArr = []) {
  val.forEach(item => {
    if (Array.isArray(item)) steamrollArray(item, flatArr);
    else flatArr.push(item);
  });
  return flatArr;
}
```

**Solution 3:**
```javascript
function steamrollArray(arr) {
  const flattenedArray = [];
  // Loop over array contents
  for (let i = 0; i < arr.length; i++) {
    if (Array.isArray(arr[i])) {
      // Recursively flatten entries that are arrays
      // and push into the flattenedArray
      flattenedArray.push(...steamrollArray(arr[i]));
    } else {
      // Copy contents that are not arrays
      flattenedArray.push(arr[i]);
    }
  }
  return flattenedArray;
};
```

### Binary Agents
**Description:**
Return an English translated sentence of the passed binary string. The binary string will be space-separated.

**Usage:**
```javascript
binaryAgent("01001001 00100000 01101100 01101111 01110110 01100101 00100000 01000110 01110010 01100101 01100101 01000011 01101111 01100100 01100101 01000011 01100001 01101101 01110000 00100001")
// return "I love FreeCodeCamp!"
```

**Solution 1:**
```javascript
function binaryAgent(str) {
  return String.fromCharCode(
    ...str.split(" ").map(function(char) {
      return parseInt(char, 2);
    })
  );
}
```

**Solution 2:**
```javascript
function binaryAgent(str) {
  var biString = str.split(" ");
  var uniString = [];

  /*using the radix (or base) parameter in parseInt, we can convert the binary
      number to a decimal number while simultaneously converting to a char*/

  for (var i = 0; i < biString.length; i++) {
    uniString.push(String.fromCharCode(parseInt(biString[i], 2)));
  }

  // we then simply join the string
  return uniString.join("");
}
```

**Solution 3:**
```javascript
function binaryAgent(str) {
  // Separate the binary code by space.
  str = str.split(" ");
  var power;
  var decValue = 0;
  var sentence = "";

  // Check each binary number from the array.
  for (var s = 0; s < str.length; s++) {
    // Check each bit from the binary number
    for (var t = 0; t < str[s].length; t++) {
      // This only takes into consideration the active ones.
      if (str[s][t] == 1) {
        // This is equivalent to 2 ** position
        power = Math.pow(2, +str[s].length - t - 1);
        decValue += power;

        // Record the decimal value by adding the number to the previous one.
      }
    }

    // After the binary number is converted to decimal, convert it to a string and store
    sentence += String.fromCharCode(decValue);

    // Reset decimal value for the next binary number.
    decValue = 0;
  }

  return sentence;
}
```

### Everything Be True
**Description:**
Check if the predicate (second argument) is truthy on all elements of a collection (first argument).

**Usage:**
```javascript
truthCheck([{name: "Pikachu", number: 25, caught: 3}, {name: "Togepi", number: 175, caught: 1}], "number")
// return true
```

**Solution 1:**
```javascript
function truthCheck(collection, pre) {
  return collection.every(function(element) {
    return element.hasOwnProperty(pre) && Boolean(element[pre]);
  });
}
```

**Solution 2:**
```javascript
function truthCheck(collection, pre) {
  // Is everyone being true?
  return collection.every(obj => obj[pre]);
}
```

### Arguments Optional
**Description:**
Create a function that sums two arguments together. If only one argument is provided, then return a function that expects one argument and returns the sum.

**Usage:**
```javascript
addTogether(5)(7) // return 12
addTogether(23, 30) // return 53
```

**Solution 1:**
```javascript
function addTogether() {
  const [first, second] = arguments;
  if (typeof(first) !== "number")
    return undefined;
  if (arguments.length === 1)
    return (second) => addTogether(first, second);
  if (typeof(second) !== "number")
    return undefined;


  return first + second;
}
```

**Solution 2:**
```javascript
function addTogether(...args) {
  const [first, second] = args;
  if (args.length === 1 && typeof first === 'number') {
    return num => {
      if (typeof num === 'number') {
        return first + num;
      }
    }
  }
  if (typeof first === 'number' && typeof second === 'number') {
    return first + second;
  }
}
```

**Solution 3:**
```javascript
function addTogether() {
  const [first, second] = arguments;
  // First argument is not a number
  if (typeof(first) !== "number") {
    return undefined;
  }
  // First argument is a number and the second argument is not defined
  else if (arguments.length === 1) {
    function addSecond(second) {
      // New argument is not a number
      if (typeof(second) !== "number") {
        return undefined;
      }
      // New argument is a number
      else {
        return first + second;
      }
    }
    // Note: returning a *function*
    return addSecond;
  }
  // First argument is a number and the second argument is not a number
  else if (typeof(second) !== "number") {
    return undefined;
  }
  // First argument is a number and the second argument is a number
  else {
    return first + second;
  }
}
```

## Make a Person
**Description**
Fill in the object constructor with the following methods below:
- `getFirstName()`
- `getLastName()`
- `getFullName()`
- `setFirstName(first)`
- `setLastName(last)`
- `setFullName(firstAndLast)`

Run the tests to see the expected output for each method. The methods that take an argument must accept only one argument, and it has to be a string. These methods must be the only available means of interacting with the object.

**Usage**
```javascript
bob.getFirstName(); // return "Bob"
```

**Solution 1**
```javascript
const Person = function(firstAndLast) {
  let fullName = firstAndLast;

  this.getFirstName = function() {
    return fullName.split(" ")[0];
  };

  this.getLastName = function() {
    return fullName.split(" ")[1];
  };

  this.getFullName = function() {
    return fullName;
  };

  this.setFirstName = function(name) {
    fullName = name + " " + fullName.split(" ")[1];
  };

  this.setLastName = function(name) {
    fullName = fullName.split(" ")[0] + " " + name;
  };

  this.setFullName = function(name) {
    fullName = name;
  };
};
```

## Map the Debris
**Description**
According to Kepler's Third Law, return a new array that transforms the elements' average altitude into their orbital periods (in seconds). The values should be rounded to the nearest whole number. The body being orbited is Earth.

**Usage**
```javascript
orbitalPeriod([{name : "sputnik", avgAlt : 35873.5553}]) // return [{name: "sputnik", orbitalPeriod: 86400}]
```

**Solution 1**
```javascript
function orbitalPeriod(arr) {
  const GM = 398600.4418;
  const earthRadius = 6367.4447;
  return arr.map(({ name, avgAlt }) => {
    const earth = earthRadius + avgAlt;
    const orbitalPeriod = Math.round(2 * Math.PI * Math.sqrt(Math.pow(earth, 3)/GM));
    return { name, orbitalPeriod };
  });
}
```

**Solution 2**
```javascript
function orbitalPeriod(arr) {
  const GM = 398600.4418;
  const earthRadius = 6367.4447;
  const newArr = [];

  // Looping through each key in arr object
  for (let elem in arr) {
    // Rounding off the orbital period value
    const orbitalPer = Math.round(
      2 * Math.PI * Math.sqrt(Math.pow(arr[elem].avgAlt + earthRadius, 3) / GM)
    );
    // Adding a new object with orbitalPeriod property
    newArr.push({ name: arr[elem].name, orbitalPeriod: orbitalPer });
  }

  return newArr;
}
```

**Solution 3**
```javascript
function orbitalPeriod(arr) {
  const GM = 398600.4418;
  const earthRadius = 6367.4447;
  // Create a new array to prevent modification of the original
  const newArr = JSON.parse(JSON.stringify(arr));
  // Loop through each item in the array arr
  newArr.forEach(function(item) {
    // Calculate the Orbital period value
    const tmp = Math.round(
      2 * Math.PI * Math.sqrt(Math.pow(earthRadius + item.avgAlt, 3) / GM)
    );
    // Delete the avgAlt property
    delete item.avgAlt;
    // Add the orbitalPeriod property
    item.orbitalPeriod = tmp;
  });

  return newArr;
}
```

## Palindrome Checker
**Description**
Return true if the given string is a palindrome. Otherwise, return false. A palindrome is a word or sentence that's spelled the same way both forward and backward, ignoring punctuation, case, and spacing.

**Solution**
```javascript
function palindrome(str) {
  const alphanumericOnly = str
    // 1) Lowercase the input
    .toLowerCase()
    // 2) Strip out non-alphanumeric characters
    .match(/[a-z0-9]/g);

  // 3) Return string === reversedString
  return alphanumericOnly.join('') ===
    alphanumericOnly.reverse().join('');
}
```

## Roman Numeral Converter
**Description**
Convert the given number (integer) into a roman numeral.

**Solution**
```javascript
function convertToRoman(num) {
  if (typeof num !== 'number') 
    return false; 

  var digits = String(+num).split(""),
    key = ["","C","CC","CCC","CD","D","DC","DCC","DCCC","CM",
    "","X","XX","XXX","XL","L","LX","LXX","LXXX","XC",
    "","I","II","III","IV","V","VI","VII","VIII","IX"],
    roman_num = "",
    i = 3;
  while (i--){
    roman_num = (key[+digits.pop() + (i * 10)] || "") + roman_num;	
  }
  return Array(+digits.join("") + 1).join("M") + roman_num;
}
```

## Caesar's Cipher
**Description**
In a shift cipher, the meanings of the letters are shifted by some set amount. ROT13 cipher, where the values of the letters are shifted by 13 places. Thus A ↔ N, B ↔ O, and so on.

**Usage**
```javascript
rot13("GUR DHVPX OEBJA SBK WHZCF BIRE GUR YNML QBT.")
// return THE QUICK BROWN FOX JUMPS OVER THE LAZY DOG
```

**Solution 1**
```javascript
function rot13(message) {
  return message.replace(/[a-z]/gi, letter => String.fromCharCode(letter.charCodeAt(0) + (letter.toLowerCase() <= 'm' ? 13 : -13)));
}
```

**Solution 2**
```javascript
const rot13 = (message) => {
  const alpha = 'abcdefghijklmnopqrstuvwxyzabcdefghijklmABCDEFGHIJKLMNOPQRSTUVWXYZABCDEFGHIJKLM';
  return message.replace(/[a-z]/gi, letter => alpha[alpha.indexOf(letter) + 13]);
}
```

**Solution 3**
```javascript
const rot13 = (message) => {
  const originalAlpha = "abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ";
  const cipher = "nopqrstuvwxyzabcdefghijklmNOPQRSTUVWXYZABCDEFGHIJKLM";
  return message.replace(/[a-z]/gi, letter => cipher[originalAlpha.indexOf(letter)]);
}
```

## Telephone Number Validator
**Description**
Return true if the passed string looks like a valid US phone number, examples:
- 555-555-5555
- (555)555-5555
- (555) 555-5555
- 555 555 5555
- 5555555555
- 1 555 555 5555

**Solution**
```javascript
function telephoneCheck(str) {
  const re = /^([+]?1[\s]?)?((?:[(](?:[2-9]1[02-9]|[2-9][02-8][0-9])[)][\s]?)|(?:(

?:[2-9]1[02-9]|[2-9][02-8][0-9])[\s.-]?)){1}([2-9]1[02-9]|[2-9][02-9]1|[2-9][02-9]{2}[\s.-]?){1}([0-9]{4}){1}$/;
  return re.test(str);
}
```

## Cash Register
**Description**
Accepts the purchase price as the first argument (price), payment as the second argument (cash), and cash-in-drawer (cid) as the third argument (2D array).

**Usage**
```javascript
checkCashRegister(19.5, 20, [["PENNY", 0.5], ["NICKEL", 0], ["DIME", 0], ["QUARTER", 0], ["ONE", 0], ["FIVE", 0], ["TEN", 0], ["TWENTY", 0], ["ONE HUNDRED", 0]])
// return {status: "CLOSED", change: [["PENNY", 0.5], ["NICKEL", 0], ["DIME", 0], ["QUARTER", 0], ["ONE", 0], ["FIVE", 0], ["TEN", 0], ["TWENTY", 0], ["ONE HUNDRED", 0]]}
```

**Solution**
```javascript
function checkCashRegister(price, cash, cid) {
  const denom = [
    { name: 'ONE HUNDRED', val: 100},
    { name: 'TWENTY', val: 20},
    { name: 'TEN', val: 10},
    { name: 'FIVE', val: 5},
    { name: 'ONE', val: 1},
    { name: 'QUARTER', val: 0.25},
    { name: 'DIME', val: 0.1},
    { name: 'NICKEL', val: 0.05},
    { name: 'PENNY', val: 0.01}
  ];

  let output = {status: null, change: []};
  let change = cash - price;
  let register = cid.reduce(function(acc, curr) {
    acc.total += curr[1];
    acc[curr[0]] = curr[1];
    return acc;
  }, {total: 0});

  if(register.total === change) {
    output.status = 'CLOSED';
    output.change = cid;
    return output;
  }

  if(register.total < change) {
    output.status = 'INSUFFICIENT_FUNDS';
    return output;
  }

  let change_arr = denom.reduce(function(acc, curr) {
    let value = 0;
    while(register[curr.name] > 0 && change >= curr.val) {
      change -= curr.val;
      register[curr.name] -= curr.val;
      value += curr.val;
      change = Math.round(change * 100) / 100;
    }

    if(value > 0) {
      acc.push([ curr.name, value ]);
    }

    return acc;
  }, []);

  if(change_arr.length < 1 || change > 0) {
    output.status = 'INSUFFICIENT_FUNDS';
    return output;
  }

  output.status = 'OPEN';
  output.change = change_arr;
  return output;
}
```