# Document Object Model (DOM)

## Finding HTML Elements

### Get element by ID
```javascript
var title = document.getElementById('header-title');
```

### Get elements by class name
```javascript
var items = document.getElementsByClassName('list-items');
```

### Get elements by tag name
```javascript
var listItems = document.getElementsByTagName('li');
```

### Queryselector

#### Get by id
```javascript
var header = document.querySelector('#header');
```

#### Get by class
```javascript
var items = document.querySelector('.list-items');
```

#### Get by tag
```javascript
var headings = document.querySelector('h1');
```

#### Get more specific elements
```javascript
document.querySelector('h1.heading');
```

#### Queryselectorall
```javascript
var heading = document.querySelectorAll('h1.heading');
```

## Changing HTML Elements

### Changing the HTML
```javascript
document.getElementById('header').innerHTML = 'Hello World!';
document.getElementsByTagName('div').innerHTML = '<h1>Hello World!</h1>';
```

### Changing a value of an attribute
```javascript
document.getElementsByTag('img').src = 'test.jpg';
```

### Changing the style
```javascript
document.getElementById(id).style.property = new style;
document.getElementsByTag('h1').style.borderBottom = 'solid 3px #000';
document.getElementById('master').classList.add('button'); // add class
document.getElementById('master').classList.remove('button'); // remove class
document.getElementById('master').classList.toggle('button'); // change class
```

The CSS properties need to be written in camelcase.

### Adding and deleting elements

#### Adding elements
```javascript
var div = document.createElement('div');
const parentEl = document.getElementById('parent').appendChild(div);
parentEl.insertBefore(createEl, firstchildEl);
```

#### Deleting elements
```javascript
var elem = document.querySelector('#header');
elem.parentNode.removeChild(elem);
```

#### Replace elements
```javascript
var div = document.querySelector('#div');
var newDiv = document.createElement('div');
newDiv.innerHTML = 'Hello World2';
div.parentNode.replaceChild(newDiv, div);
```

### Writing directly into the HTML output stream
```javascript
document.write('<h1>Hello World!</h1><p>This is a paragraph!</p>'); // HTML expression
document.write(Date()); // JavaScript expression
```

## Event Handlers

### Most used: mouse click, page load, mouse move, input field change

### Assign Events
```html
<h1 onclick="this.innerHTML = 'Hello!'">Click me!</h1>
<h1 onclick="changeText(this)">Click me!</h1> <!-- can also call functions -->
document.getElementById('btn').onclick = changeText();
```

### Assign Events Listeners
```javascript
document.getElementById('btn').addEventListener('click', runEvent);
document.getElementById('btn').addEventListener('mouseover', runEvent); // assign multiple events
```

## Node Relationships

### Navigating Between Nodes

#### Properties: parentNode, childNodes, firstChild, lastChild, nextSibling

```javascript
var parent = document.getElementById('heading').parentNode;
```

### Navigating Between Elements

#### Properties: children or children[i], previousElementSibling, lastElementChild, nextElementSibling