# Basic Algorithm Scripting

## Convert Celsius to Fahrenheit
```javascript
let fahrenheit = (celsius * 9 / 5) + 32;
```

## Reverse a String

### Solution 1
```javascript
function reverseString(str) {
  let reversedStr = "";
  for (let i = str.length - 1; i >= 0; i--) {
    reversedStr += str[i];
  }
  return reversedStr;
}
```

### Solution 2
```javascript
function reverseString(str) {
  return str
    .split("")
    .reverse()
    .join("");
}
```

## Factorial

### Solution 1
```javascript
function factorialize(num) {
  let product = 1;
  for (let i = 2; i <= num; i++) {
    product *= i;
  }
  return product;
}
```

### Solution 2
```javascript
function factorialize(num) { // recursive function
  if (num === 0) {
    return 1;
  }
  return num * factorialize(num - 1);
}
```

### Solution 3
```javascript
function factorialize(num) { // using reduce function
  return num < 0 ? 1 :
    new Array(num)
      .fill(undefined)
      .reduce((product, _, index) => product * (index + 1), 1);
}
```

## Find the Longest Word in a String

### Solution 1
```javascript
function findLongestWordLength(str) {
  let words = str.split(' ');
  let maxLength = 0;

  for (let i = 0; i < words.length; i++) {
    if (words[i].length > maxLength) {
      maxLength = words[i].length;
    }
  }

  return maxLength;
}
```

### Solution 2
```javascript
function findLongestWordLength(s) {
  return s.split(' ')
    .reduce(function(longest, word) {
      return Math.max(longest, word.length)
    }, 0);
}
```

### Solution 3
```javascript
function findLongestWordLength(str) {
  return Math.max(...str.split(" ").map(word => word.length));
}
```

## Return Largest Numbers in Arrays

### Solution 1
```javascript
function largestNumbersInArrays(arr) {
  let bigNumbersInArray = [];

  for (let i = 0; i < arr.length; i++){
    let biggerNumberInNestedArray = Number.NEGATIVE_INFINITY;

    for (let j = 0; j < arr[i].length; j++){
      biggerNumberInNestedArray = arr[i][j] > biggerNumberInNestedArray ? arr[i][j] : biggerNumberInNestedArray; 
    }

    bigNumbersInArray.push(biggerNumberInNestedArray);
  }

  return bigNumbersInArray;
}
```

### Solution 2
```javascript
function largestOfFour(arr, finalArr = []) { // recursive function
  return !arr.length
    ? finalArr
    : largestOfFour(arr.slice(1), finalArr.concat(Math.max(...arr[0])))
}
```

### Solution 3
```javascript
function largestOfFour(arr) {
  return arr.map(Function.apply.bind(Math.max, null));
}
```

## Confirm the Ending (has target string in the end of the provided)

### Solution 1
```javascript
function confirmEnding(str, target) {
  return str = str.substring(str.length - target.length, str.length) == target;
}
```

### Solution 2
```javascript
function confirmEnding(str, target) {
  return str.slice(-target.length) === target
}
```

### Solution 3
```javascript
function confirmEnding(str, target) { // using regex
  let re = new RegExp(target + "$", "i");
  return re.test(str);
}
```

## Repeat a String Repeat a String

### Solution 1
```javascript
function repeatStringNumTimes(str, num) {
  let result = "";
  let i = 0;

  while (i < num) {
    result += str;
    i++;
  }  

  return result;
}
```

### Solution 2
```javascript
function repeatStringNumTimes(str, num) { // recursive function
  return num > 0 ? str + repeatStringNumTimes(str, num - 1) : '';
}
```

## Truncate a String

### Solution 1
```javascript
function truncateString(str, num) {
  return str.length > num ? str.substring(0, num) + "..." : str;
}
```

### Solution 2
```javascript
function truncateString(str, num) {
  return str.length > num ? str.slice(0, num) + "..." : str;
}
```

## Finders Keepers

### Solution 1
```javascript
function findElement(arr, func) {
  let num = 0;

  for (let i = 0; i < arr.length; i++) {
    num = arr[i];
    if (func(num)) {
      return num;
    }
  }

  return undefined;
}
```

### Solution 2
```javascript
function findElement(arr, func) {
  return arr.find(func);
}
```

### Solution 3
```javascript
function findElement(arr, func) {
  return arr[arr.map(func).indexOf(true)];
}
```

### Solution 4
```javascript
function findElement(arr, func) { // recursive function
  if (arr.length > 0 && !func(arr[0])) {
    return findElement(arr.slice(1), func);
  } else {
    return arr[0];
  }
}
```
## Boo Who

```javascript
function booWho(bool) {
  return typeof bool === "boolean";
}
```

## Title Case a Sentence

### Solution 1

```javascript
function titleCase(str) {
  const newTitle = str.split(" ");
  const updatedTitle = [];
  for (let st in newTitle) {
    updatedTitle[st] = newTitle[st][0].toUpperCase() + newTitle[st].slice(1).toLowerCase();
  }
  return updatedTitle.join(" ");
}
```

### Solution 2

```javascript
function titleCase(str) {
  return str
    .toLowerCase()
    .split(" ")
    .map(val => val.replace(val.charAt(0), val.charAt(0).toUpperCase()))
    .join(" ");
}
```

### Solution 3

```javascript
function titleCase(str) {
  return str
    .toLowerCase()
    .replace(/(^|\s)\S/g, L => L.toUpperCase());
}
```

### Solution 4

```javascript
function titleCase(str) {
  let strArray = str.toLowerCase().split(" ");
  let result = "";

  for (let i = 0; i < strArray.length; i++){
    strArray[i][0].toUpperCase();
    result += strArray[i][0].toUpperCase() + strArray[i].substring(1) + " ";
  }

  return result.trim();
}
```

## Slice and Splice

### Solution 1

```javascript
function frankenSplice(arr1, arr2, n) {
  let localArray = arr2.slice();
  
  for (let i = 0; i < arr1.length; i++) {
    localArray.splice(n, 0, arr1[i]);
    n++;
  }
  
  return localArray;
}
```

### Solution 2

```javascript
function frankenSplice(arr1, arr2, n) {
  let localArr = arr2.slice();
  localArr.splice(n, 0, ...arr1);
  return localArr;
}
```

### Solution 3

```javascript
function frankenSplice(arr1, arr2, n) {
  return [...arr2.slice(0, n), ...arr1, ...arr2.slice(n)];
}
```

### My messy solution

```javascript
function frankenSplice(arr1, arr2, n) {
  let result = [];
  let done = false;
  
  if (arr2.length == 0){
    return arr1;
  }

  for (let i = 0; i < arr2.length; i++){
    result.push(arr2[i]);

    if (i >= n -1 && !done){
      for (let j = 0; j < arr1.length; j++){
        result.push(arr1[j])
      }

      done = true;
    }
  }

  return result;
}
```

## Falsy Bouncer

Falsy values in JavaScript are false, null, 0, "", undefined, and NaN. Add to a new array only the non-falsy values.

### Solution 1

```javascript
function bouncer(arr) {
  let newArr = []
  for(let i = 0; i < arr.length; i++) if (arr[i]) newArr.push(arr[i]); // or (!!arr[i] == true) or (!Boolean(arr[i])
  return newArr; 
}
```

### Solution 2

```javascript
function bouncer(arr) {
  return arr.filter(Boolean);
}
```

## Where do I Belong

Return the lowest index at which a value (second argument) should be inserted into an array.

### Solution 1

```javascript
function getIndexToIns(arr, num) {
  arr.sort((a, b) => a - b); // use arrow function to sort numerically and not alphabetically (default)

  for (let i = 0; i < arr.length; i++) {
    if (arr[i] >= num)
      return i;
  }

  return arr.length;
}
```

### Solution 2

```javascript
function getIndexToIns(arr, num) {
  return arr.filter(val => num > val).length;
}
```

### Solution 3

```javascript
function getIndexToIns(arr, num) {
  return arr.concat(num).sort((a, b) => a - b).indexOf(num);
}
```

### Solution 4

```javascript
function getIndexToIns(arr, num) {
  // sort and find the right index
  let index = arr.sort((curr, next) => curr - next).findIndex(currNum => num <= currNum);
  // Returns index or total length of arr
  return index === -1 ? arr.length : index;
}
```

## Mutations

### Solution 1
```javascript
function mutation(arr) { // procedural
  let test = arr[1].toLowerCase();
  let target = arr[0].toLowerCase();
  for (let i = 0; i < test.length; i++) {
    if (target.indexOf(test[i]) < 0) return false;
  }
  return true;
}
```

### Solution 2
```javascript
function mutation(arr) { // declarative
  return arr[1]
    .toLowerCase()
    .split("")
    .every(function(letter) {
      return arr[0].toLowerCase().indexOf(letter) !== -1;
    });
}
```

### Solution 3
```javascript
function mutation([ target, test ], i = 0) { // recursive
  target = target.toLowerCase();
  test = test.toLowerCase();
  return i >= test.length
    ? true
    : !target.includes(test[i])
      ? false
      : mutation([ target, test ], i + 1);
}
```

### My solution
```javascript
function mutation(arr) {
  let hasCount = 0;

  // convert to a lowercase array of characters
  arr[0] = arr[0].toLowerCase().split("");
  arr[1] = arr[1].toLowerCase().split("");

  // remove duplicates
  let arr0 = [...new Set(arr[0])];
  let arr1 = [...new Set(arr[1])];

  // my own indexOf
  for (let i = 0; i < arr0.length; i++){
    for (let j = 0; j < arr1.length; j++){
      if (arr0[i] == arr1[j]){
        hasCount++;
        if (hasCount >= arr1.length) return true;
      }
    }
  }

  return false;
}
```

## Chunky Monkey

### Solution 1
```javascript
function chunkArrayInGroups(arr, size) {
  let temp = [];
  let result = [];

  for (let a = 0; a < arr.length; a++) {
    if (a % size !== size - 1) temp.push(arr[a]);
    else {
      temp.push(arr[a]);
      result.push(temp);
      temp = [];
    }
  }

  if (temp.length !== 0) result.push(temp);
  return result;
}
```

### Solution 2
```javascript
function chunkArrayInGroups(arr, size) { // cleaner solution
  let newArr = [];
  for (let i = 0; i < arr.length; i += size) {
    newArr.push(arr.slice(i, i + size));
  }
  return newArr;
}
```

### Solution 3
```javascript
function chunkArrayInGroups(arr, size) { // using while instead of for loop
  let newArr = [];
  let i = 0;

  while (i < arr.length) { 
    newArr.push(arr.slice(i, i + size));
    i += size;
  }
  return newArr;
}
```

### Solution 4
```javascript
function chunkArrayInGroups(arr, size) { // using splice
  let newArr = [];
  while (arr.length > 0) {
    newArr.push(arr.splice(0, size));
  }
  return newArr;
}
```

### Solution 5
```javascript
function chunkArrayInGroups(arr, size) { // recursive
  if (arr.length <= size) {
    return [arr];
  } else {
    return [arr.slice(0, size)].concat(
      chunkArrayInGroups(arr.slice(size), size)
    );
  }
}
```
