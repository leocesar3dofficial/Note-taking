# React Accessibility

## Semantic HTML Breakage

- Elements: lists (`<ol>`, `<ul>`, `<dl>`) and `<table>`
- Must use React Fragments

### Example

```jsx
import React, { Fragment } from 'react';

function ListItem({ item }) {
  return (
    <Fragment key={item.id}>
      <dt>{item.term}</dt>
      <dd>{item.description}</dd>
    </Fragment>
  );
}

function Glossary(props) {
  return (
    <dl>
      {props.items.map(item => (
        <ListItem item={item} key={item.id} />
      ))}
    </dl>
  );
}
```

## Accessible Forms

### Labeling

```jsx
<label htmlFor="namedInput">Name:</label>
```

- HTML "for" attribute == "htmlFor" in React

### Programmatically Managing Focus Example

```jsx
class CustomTextInput extends React.Component {
  constructor(props) {
    super(props);
    this.textInput = React.createRef();
  }

  render() {
    return (
      <input
        type="text"
        ref={this.textInput}
      />
    );
  }

  focus() {
    this.textInput.current.focus();
  }
}
```

### Mouse and Pointer Events Example

```jsx
class BlurExample extends React.Component {
  constructor(props) {
    super(props);

    this.state = { isOpen: false };
    this.timeOutId = null;

    this.onClickHandler = this.onClickHandler.bind(this);
    this.onBlurHandler = this.onBlurHandler.bind(this);
    this.onFocusHandler = this.onFocusHandler.bind(this);
  }

  onClickHandler() {
    this.setState(currentState => ({
      isOpen: !currentState.isOpen
    }));
  }

  onBlurHandler() {
    this.timeOutId = setTimeout(() => {
      this.setState({
        isOpen: false
      });
    });
  }

  onFocusHandler() {
    clearTimeout(this.timeOutId);
  }

  render() {
    return (
      <div onBlur={this.onBlurHandler} onFocus={this.onFocusHandler}>
        <button
          onClick={this.onClickHandler}
          aria-haspopup="true"
          aria-expanded={this.state.isOpen}
        >
          Select an option
        </button>
        {this.state.isOpen && (
          <ul>
            <li>Option 1</li>
            <li>Option 2</li>
            <li>Option 3</li>
          </ul>
        )}
      </div>
    );
  }
}
```

## Development Assistance Tool

- ESLint provides AST linting feedback regarding accessibility issues in JSX
- The Create React App has it preinstalled as `eslint-plugin-jsx-a11y`
- Enable it: create an `.eslintrc` file in the root of the project

```json
{
  "extends": ["react-app", "plugin:jsx-a11y/recommended"],
  "plugins": ["jsx-a11y"]
}
```