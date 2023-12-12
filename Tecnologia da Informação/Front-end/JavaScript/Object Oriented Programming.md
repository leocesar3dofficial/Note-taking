# Object Oriented Programming

## Example

### Basic
```javascript
const cat = {
  "name": "Whiskers",
  "legs": 4,
  "tails": 1,
  "enemies": ["Water", "Dogs"]
};
```

### Complex
```javascript
const ourMusic = [
  {
    "artist": "Daft Punk",
    "title": "Homework",
    "release_year": 1997,
    "formats": [
      "CD",
      "Cassette",
      "LP"
    ],
    "gold": true
  }
];
```

## Accessing object properties

### Dot notation
```javascript
const prop1val = myObj.prop1;
```

### Bracket notation
```javascript
const prop1val = myObj["prop1"];
```

### Iterate over object properties
```javascript
for (let property in <object>) {
  // do something with property variable
}
```

## Accessing nested objects
```javascript
ourStorage.cabinet["top drawer"].folder2;
ourStorage.desk.drawer;
```

## Accessing Nested Arrays
```javascript
ourPets[0].names[1];
```

## Add new properties
```javascript
ourDog.bark = "bow-wow";
ourDog["bark"] = "bow-wow";
```

### To prototype

#### Single property
```javascript
Dog.prototype.numLegs = 4; // shared among all instances
```

#### Multiple properties
```javascript
Bird.prototype = { 
  constructor: Bird, // must be set or it will be treated as a regular object  
  numLegs: 2, 
  eat: function() {
    console.log("nom nom nom");
  },
  describe: function() {
    console.log("My name is " + this.name);
  }
};
```

## Delete properties
```javascript
delete ourDog.bark;
```

## Testing objects for properties
```javascript
users.hasOwnProperty('Alan');
'Alan' in users;
```

## List object keys with
```javascript
Object.keys(myObject); // this method returns an array with all key's value as strings
```

## Check if instance is object
```javascript
if (myHouse instanceof House) { // do something } // this is the preferred way 
if (beagle.constructor === Dog) { // do something } // constructor property can be overwritten or deleted, giving wrong results
```

## Check the prototype
```javascript
CustomObject.prototype.isPrototypeOf(<object instance>);
```

## Check prototype inheritance
```javascript
Object.prototype.isPrototypeOf(CustomObject.prototype);
```

## Inheritance

### Example
```javascript
function Animal() { }; // supertype 

Animal.prototype = {
  constructor: Animal, 
  describe: function() {
    console.log("My name is " + this.name);
  }
};

Bird.prototype = {
  constructor: Bird
};

Dog.prototype = {
  constructor: Dog
};
```

## Instancing

### Examples
```javascript
let animal = new Animal(); // has disadvantages
let animal = Object.create(Animal.prototype); // preferred way
```

### Step 1: Set child prototype
```javascript
animal.prototype = Object.create(Animal.prototype);
```

### Step 2: Set constructor property
```javascript
Bird.prototype.constructor = Bird;
```

### Step 3: Add methods after inheritance
```javascript
Bird.prototype.fly = function() { // make it fly! }
```

### Step 4: Override Inherited Methods
```javascript
ChildObject.prototype.methodName = function() {...}; // just redeclare parent's method with the same name
```

## Add common behavior between unrelated objects with Mixin

### Mixin is a form of composition

#### Example

##### Step 1: define mixin method
```javascript
let flyMixin = function(obj) {
  obj.fly = function() {
    console.log("Flying, wooosh!");
  }
};
```

##### Step 2: assign the fly method to any object
```javascript
flyMixin(bird);
flyMixin(plane);
```

## Create private properties with closure

### Example
```javascript
function Bird() { // object constructor
  let hatchedEgg = 10; // this property is now private

  this.getHatchedEggCount = function() { // the only way to access the private property externally
    return hatchedEgg;
  };
}
let ducky = new Bird();
ducky.getHatchedEggCount();
```

## Immediately Invoked Function Expression (IIFE)

- Function executed immediately after its declaration
- The function must be anonymous
- Just surround the method with parentheses: `(function () { console.log("Chirp, chirp!"); })();`
- It can be used to create a module to group behaviors

### Example

#### Before
```javascript
function glideMixin(obj) {
  obj.glide = function() {
    console.log("Gliding on the water");
  };
}
function flyMixin(obj) {
  obj.fly = function() {
    console.log("Flying, wooosh!");
  };
}
```

#### After
```javascript
let motionModule = (function () {
  return {
    glideMixin: function(obj) {
      obj.glide = function() {
        console.log("Gliding on the water");
      };
    },
    flyMixin: function(obj) {
      obj.fly = function() {
        console.log("Flying, wooosh!");
      };
    }
  }
})();
```

#### Invoke
```javascript
motionModule.glideMixin(duck);
duck.glide();
duck.fly();
```