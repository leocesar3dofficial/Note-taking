# Arrays

- Mutable and type agnostic.

## Dimension

- Single or one dimension.
- N-dimensional.

## Bracket notation to access and modify array values

- Number of elements in an array: `Array.length` // it is a property and not a function.

## Add items

- to the end: `Array.push()`
- to the beginning: `Array.unshift()`

## Remove items

- in the end: `Array.pop()`
- in the beginning: `Array.shift()`

## Add or remove items from arbitrary indexes

- `Array.splice()` // one or more values.

## Extract part of an array

- `Array.slice()`

## Copy and combine an array with the spread operator

- `[...myArray]`
- `let thatArray = [...thisArray];` // copy
- `let thatArray = ['basil', 'cilantro', ...myArray, 'coriander'];` // combine.

## Check for the presence of an element with `indexOf()`

- if not found returns: -1
- else returns the element's index

## Iterate over an array

- **for loop (most flexible)**
  ```javascript
  for (let i = 0; i < arr.length; i++) { // do something}
  ```
- **Using "in" keyword:**
  ```javascript
  for (let user in users)  { // do something}
  ```

- `every()`: executes a function for each array element

  Example 1
  ```javascript
  function isEveryoneHere(userObj) {
    return ["Alan", "Jeff", "Sarah", "Ryan"].every(name =>
      userObj.hasOwnProperty(name)
    );
  }
  ```

  Example 2
  ```javascript
  function checkPositive(arr) {
    return arr.every(val => val > 0); // arrow function with a single instruction
  }
  checkPositive([1, 2, 3, -4, 5]);
  ```

  Example 3
  ```javascript
  function checkPositive(arr) {
    return arr.every(function(value) {
      return value > 0; // can have several instructions
    });
  }
  ```

- `some()`: Same as `every()`, but returns true if ANY array element meets a criteria

- `forEach()`

- `map()`: Populates a new array with the results of calling a provided function on every element in the calling array. It doesn't alter the original array and doesn't change the length of the array.

  Examples
  ```javascript
  const names = users.map(user => user.name);
  const ratings = watchList.map(({ Title: title, imdbRating: rating }) => ({ title, rating }));
  ```

  Implementation
  ```javascript
  var s = [23, 65, 98, 5];

  Array.prototype.myMap = function(callback) {
    var newArray = [];
    this.forEach(a => newArray.push(callback(a))); // can use for loop instead
    return newArray;
  };

  var new_s = s.myMap(function(item) {
    return item * 2;
  });
  ```

- `filter()`: Change the length of the resulting array based on the filter expression

  Examples
  ```javascript
  const usersUnder30 = users.filter(user => user.age < 30);

  const filteredList = watchList.filter(({ imdbRating }) => imdbRating >= 8.0).map(({ Title: title, imdbRating: rating }) => ({ title, rating }));

  const squaredNumbers = arr.filter(num => num > 0 && Number.isInteger(num)).map(integer => integer ** 2); // filter positive integers and square them with map function
  ```

  Implementation
  ```javascript
  let s = [23, 65, 98, 5];

  Array.prototype.myFilter = function(callback) {
    var newArray = [];
    for (let i = 0; i < this.length; i++) { // can use forEach instead
      if (callback(this[i]) === true) {
        newArray.push(this[i]);
      }
    }
    return newArray;
  };

  var new_s = s.myFilter(function(item) {
    return item % 2 === 1;
  });
  ```

- `slice()`
  ```javascript
  const newArray = arr.slice(<first index>, <last index (non-inclusive)>); // return a new array from and to
  const newArray = arr.slice(); // return a copy of the array
  ```

- `concat()`
  ```javascript
  [1, 2, 3].concat([4, 5, 6]); // returns a new array: [1, 2, 3, 4, 5, 6]
  ```

- `reduce()`: Filter and map functions are special applications of reduce. Returns a single value (i.e. string, number, object, array).

  Examples
  ```javascript
  const sumOfAges = users.reduce((sum, user) => sum + user.age, 0);

  const usersObj = users.reduce((obj, user) => { obj[user.name] = user.age; return obj; }, {}); // returns key/value pair: { John: 34, Amy: 20, camperCat: 10 }

  // Return average movie rating from a specific Director

  // Solution 1:
  function getAverageRatingFromDirector(watchList, director) {
    let filteredArr = watchList.filter(movie => movie.Director == director);
    let averageRating = filteredArr.reduce((sum, movie) => sum + parseFloat(movie.imdbRating), 0) / filteredArr.length;
    return averageRating;
  }

  // Solution 2:
  function getRating(watchList) {
    const nolanData = watchList
      .reduce((data, { Director: director, imdbRating: rating }) => {
        if (director === 'Christopher Nolan') {
          data.count++;
          data.sum += Number(rating);
        }
        return data;
      }, { sum: 0, count: 0 });
    const averageRating = nolanData.sum / nolanData.count;
    return averageRating;
  }
  ```

  Squared list
  ```javascript
  const squareList = arr => {
    return arr.reduce((sqrIntegers, num) => {
      return Number.isInteger(num) && num > 0
        ? sqrIntegers.concat(num * num)
        : sqrIntegers;
    }, []);
  };
  ```

- `sort()`: Mutates the array in place

  Alphabetical
  ```javascript
  function alphabeticalOrder(arr) {
    return arr.sort(function(a, b) {
      return a === b ? 0 : a > b ? 1 : -1;
    });
  }
  ```

  Alphabetical reversed
  ```javascript
  function reverseAlpha(arr) {
    return arr.sort(function(a, b) {
      return a === b ? 0 : a < b ? 1 : -1;
    });
  }
  ```

  Ascending

  - Mutable
    ```javascript
    function ascendingOrder(arr) { // use: ascendingOrder([1, 5, 2, 3, 4]); returns: [1, 2, 3, 4, 5]
      return arr.sort(function(a, b) {
        return a - b;
      });
    }
    ```

  - Non-mutable
    ```javascript
    function nonMutatingSort(arr) {
      let newArr = [].concat(arr); // concat with an empty array returns a new array, this is another way to copy an array
      return newArr.sort(function(a, b) { return a - b; });
    }
    ```

- `split()`
  ```javascript
  const bySpace = str.split(" "); // an empty string ("") returns an array of characters
  const byDigits = otherString.split(/\d/); // regex
  const bySpaceAndPunctuation = str.split(/\W/); // regex
  ```

- `join()`: Combine the elements of an array into a string
  ```javascript
  const arr = ["Hello", "World"];
  const str = arr.join(" "); // returns: "Hello World"
  ```

- URL slugs

  Solution 1
  ```javascript
  // the global variable
  var globalTitle = "Winter Is Coming";

  function urlSlug(title) {
    return title
      .toLowerCase()
      .trim()
      .split(/\s+/)
      .join("-");
  }

  var winterComing = urlSlug(globalTitle); // Should be "winter-is-coming"
  ```

  Solution 2
  ```javascript
  // the global variable
  var globalTitle = "Winter Is Coming";

  function urlSlug(title) {
    return title
      .split(" ")
      .filter(substr => substr !== "") // or .filter(word => word.length > 0)
      .join("-")
      .toLowerCase();
  }

  var winterComing = urlSlug(globalTitle); // Should be "winter-is-coming"
  ```