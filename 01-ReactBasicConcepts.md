# React Basic Concepts Reference

## React JS Introduction to JSX
JSX (JavaScript XML) is a syntax extension for React that allows developers to write HTML elements inside JavaScript.

### Example:
```jsx
const element = <h1>Hello, JSX!</h1>;
ReactDOM.render(element, document.getElementById('root'));
```

---

## React JS Rendering Elements
React updates the UI efficiently by re-rendering only the necessary parts when the state or props change.

### Example:
```jsx
const element = <h1>Time: {new Date().toLocaleTimeString()}</h1>;
ReactDOM.render(element, document.getElementById('root'));
```

---

## React JS Components
Components are modular, reusable UI blocks in React.

### Example:
```jsx
function Welcome(props) {
  return <h1>Hello, {props.name}!</h1>;
}
```

---

## React JS Fragments
Fragments allow multiple elements to be returned without adding extra `<div>` elements to the DOM.

### Example:
```jsx
function FragmentExample() {
  return (
    <>
      <h1>Title</h1>
      <p>This is a description.</p>
    </>
  );
}
```

---

## React JS Props
Props allow data to be passed from one component to another.

### Example:
```jsx
function Greeting(props) {
  return <h1>Welcome, {props.user}!</h1>;
}
<Greeting user="John" />;
```

---

## React JS PropTypes
PropTypes help validate props to ensure type safety.

### Example:
```jsx
import PropTypes from 'prop-types';

function Message({ text }) {
  return <p>{text}</p>;
}

Message.propTypes = {
  text: PropTypes.string.isRequired,
};
```

---

## React JS State
State allows components to store and manage data internally.

### Example:
```jsx
function Counter() {
  const [count, setCount] = React.useState(0);
  return <button onClick={() => setCount(count + 1)}>Count: {count}</button>;
}
```

---

## React JS Lifecycle of Components
Lifecycle methods manage component behavior at different stages.

### Example:
```jsx
class Lifecycle extends React.Component {
  componentDidMount() {
    console.log('Component Mounted');
  }

  render() {
    return <h1>Lifecycle Example</h1>;
  }
}
```

---

## React JS Conditional Rendering
Render UI elements based on conditions.

### Example:
```jsx
function Greeting(props) {
  return props.isLoggedIn ? <h1>Welcome back!</h1> : <h1>Please sign in.</h1>;
}
```

---

## React JS Lists
Render lists dynamically using `.map()`.

### Example:
```jsx
const names = ['Alice', 'Bob', 'Charlie'];
const nameList = names.map((name) => <li key={name}>{name}</li>);
```

---

## React JS Keys
Keys help React identify list items efficiently.

### Example:
```jsx
const numbers = [1, 2, 3];
const listItems = numbers.map((num) => <li key={num}>{num}</li>);
```

---

## React JS Refs
Refs allow direct manipulation of DOM elements.

### Example:
```jsx
function FocusInput() {
  const inputRef = React.useRef(null);

  function handleClick() {
    inputRef.current.focus();
  }

  return (
    <>
      <input ref={inputRef} />
      <button onClick={handleClick}>Focus Input</button>
    </>
  );
}
```

---

## React JS Forms
React forms store data in the component’s state.

### Example:
```jsx
function Form() {
  const [name, setName] = React.useState('');

  return (
    <form>
      <input value={name} onChange={(e) => setName(e.target.value)} />
      <p>Hello, {name}!</p>
    </form>
  );
}
```

---

## React JS Hooks
Hooks enable state and lifecycle features in functional components.

### Example (useState Hook):
```jsx
function Counter() {
  const [count, setCount] = React.useState(0);
  return <button onClick={() => setCount(count + 1)}>Count: {count}</button>;
}
```

---

## React JS Router
React Router enables navigation between different components.

### Example:
```jsx
import { BrowserRouter, Route, Link } from 'react-router-dom';

function App() {
  return (
    <BrowserRouter>
      <Link to="/about">Go to About</Link>
      <Route path="/about" component={() => <h1>About Page</h1>} />
    </BrowserRouter>
  );
}
```

---

## React JS ReactDOM
ReactDOM handles rendering of React elements to the real DOM.

### Example:
```jsx
const element = <h1>Hello, World!</h1>;
ReactDOM.render(element, document.getElementById('root'));
```

---

## React JS Event Handling
React uses synthetic events to handle user interactions.

### Example:
```jsx
function ClickHandler() {
  function handleClick() {
    alert('Button Clicked!');
  }
  return <button onClick={handleClick}>Click Me</button>;
}
```

---

## React JS Context API
Context API enables global state management.

### Example:
```jsx
const UserContext = React.createContext();

function Component() {
  return (
    <UserContext.Provider value="John Doe">
      <ChildComponent />
    </UserContext.Provider>
  );
}

function ChildComponent() {
  const user = React.useContext(UserContext);
  return <h1>User: {user}</h1>;
}
```

---

## React JS Controlled Components
Controlled components handle form input via state.

### Example:
```jsx
function ControlledForm() {
  const [text, setText] = React.useState('');

  return (
    <input type="text" value={text} onChange={(e) => setText(e.target.value)} />
  );
}
```

---

This guide provides clear explanations with relevant examples for each React concept. 🚀
