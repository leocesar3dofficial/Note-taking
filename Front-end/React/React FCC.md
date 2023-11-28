# React

## JSX

### Comments

```jsx
{/* some comment */}
```

## Components

### Simple

```jsx
const JSX = (
  <div className="myDiv">
    <h1>Hello World</h1>
    <hr />
    <br />
    <p>Lets render this to the DOM</p>
  </div>
);

ReactDOM.render(JSX or <Component />, document.getElementById("challenge-node"))
```

### Stateless to Compose UI

```jsx
const DemoComponent = function() {
  return (
    <div className='customClass' />
  );
};
```

### React Stateless Component

```jsx
// this component has access to local state and lifecycle hooks
class Kitten extends React.Component {
  constructor(props) {
    super(props);
  }

  render() {
    return (
      <h1>Hi</h1>
    );
  }
}
```

### Composition

#### Example 1

```jsx
render() {
  return (
    <App>
      <Navbar />
      <Dashboard />
      <Footer />
    </App>
  )
}
```

#### Example 2

```jsx
const ChildComponent = () => {
  return (
    <div>
      <p>I am the child</p>
    </div>
  );
};

class ParentComponent extends React.Component {
  constructor(props) {
    super(props);
  }

  render() {
    return (
      <div>
        <h1>I am the parent</h1>
        <ChildComponent />
      </div>
    );
  }
};
```

### Props

#### Stateless Functional Component

These components act like pure functions. It is a function that accepts props and returns JSX.

#### Basics

Pass the property `user` to the `Welcome` component.

```jsx
<App>
  <Welcome user='Mark' />
</App>
```

In the component itself, read the property.

```jsx
const Welcome = (props) => <h1>Hello, {props.user}!</h1>
```

Passing an Array.

```jsx
<ParentComponent>
  {/* the value within the braces is interpreted as JavaScript */}
  <ChildComponent colors={["green", "blue", "red"]} />
</ParentComponent>
```

Set default props for a component.

```jsx
ShoppingCart.defaultProps = { property: defaultValue }
```

#### Example

```jsx
const CurrentDate = (props) => {
  return (
    <div>
      <p>The current date is: {props.date}</p>
    </div>
  );
};

class Calendar extends React.Component {
  constructor(props) {
    super(props);
  }

  render() {
    return (
      <div>
        <h3>What date is it?</h3>
        <CurrentDate date={Date()}/>
      </div>
    );
  }
};

Calendar.defaultProps = {date: 'Default date' };
Calendar.propTypes = { date: PropTypes.string.isRequired };
```

#### Typed Props or PropTypes

```jsx
// must be imported first
import PropTypes from 'prop-types';
// throw a warning when the data is of any other type
MyComponent.propTypes = { handleClick: PropTypes.func.isRequired }; // handleClick must be a function passed as props
Items.propTypes = { quantity: PropTypes.number.isRequired }; // quantity must be a number
```

#### Class Component

Access `props` properties.

```jsx
{this.props.<property>} // must use the "this" keyword
```

Example: 

```jsx
<p>Hello, <strong>{this.props.name}</strong>!</p>
```

### Stateful Component

#### Basic

```jsx
class StatefulComponent extends React.Component {
  constructor(props) {
    super(props);
    this.state = { 
      // define the component state inside the class constructor
      firstName: "Bob"
    }
  }

  render() {
    return (
      <div>
        <h1>{this.state.firstName}</h1>
      </div>
    );
  }
};
```

#### Update State

##### Basic

```jsx
class MyComponent extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      name: 'Initial State'
    };
    this.handleClick = this.handleClick.bind(this);
  }

  handleClick() { // update code here
    this.setState({
      name: 'React Rocks!'
    });
  }

  render() {
    return (
      <div>
        <button onClick={this.handleClick}>Click Me</button>
        <h1>{this.state.name}</h1>
      </div>
    );
  }
};
```

##### State and Props

```jsx
this.setState((state, props) => ({
  counter: state.counter + props.increment
}));
```

##### State Only

```jsx
this.setState(state => ({
  counter: state.counter + 1
}));
```

Example

```jsx
class Toggle extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      visibility: false
    };
    this.toggleVisibility = this.toggleVisibility.bind(this);
  }

  toggleVisibility() {
    this.setState(state => ({
      visibility: !state.visibility
    }));
  }

  render() {
    if (this.state.visibility) {
      return (
        <div>
          <button onClick = {this.toggleVisibility}>Click Me</button>
          <h1>Now you see me!</h1>
        </div>
      );
    } else {
      return (
        <div>
          <button onClick = {this.toggleVisibility}>Click Me</button>
        </div>
      );
    }
  }
};
```

### Controlled Input

```jsx
class ControlledInput extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      input: ''
    };

    this.handleChange = this.handleChange.bind(this);
  }

  handleChange(event) {
    this.setState({
      input: event.target.value
    })
  }

  render() {
    return (
      <div>
        <input value={this.state.input} onChange={this.handleChange} />
        <h4>Controlled Input:</h4>
        <p>{this.state.input}</p>
      </div>
    );
  }
};
```

### Controlled Form

```jsx
class MyForm extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      input: '',
      submit: ''
    };
    this.handleChange = this.handleChange.bind(this);
    this.handleSubmit = this.handleSubmit.bind(this);
  }

  handleChange(event) {
    this.setState({
      input: event.target.value
    });
  }

  handleSubmit(event) {
    event.preventDefault()
    this.setState({
      submit: this.state.input
    });
  }
  
  render() {
    return (
      <div>
        <form onSubmit={this.handleSubmit}>
          <input
            value={this.state.input}
            onChange={this.handleChange} />
          <button type='submit'>Submit!</button>
        </form>
        <h1>{this.state.submit}</h1>
      </div>
    );
  }
};
```