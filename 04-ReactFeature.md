# React.js Features with Examples

## 1. Components
React components help break the UI into reusable pieces.

### Functional Component
```jsx
const Greeting = ({ name }) => {
  return <h1>Hello, {name}!</h1>;
};
```

### Class Component (Older Approach)
```jsx
class Greeting extends React.Component {
  render() {
    return <h1>Hello, {this.props.name}!</h1>;
  }
}
```

---

## 2. Hooks
Hooks allow functional components to use state and other React features.

### useState (State Management)
```jsx
import { useState } from "react";

const Counter = () => {
  const [count, setCount] = useState(0);

  return (
    <button onClick={() => setCount(count + 1)}>
      Clicked {count} times
    </button>
  );
};
```

### useEffect (Side Effects like API Calls)
```jsx
import { useEffect, useState } from "react";
import axios from "axios";

const Users = () => {
  const [users, setUsers] = useState([]);

  useEffect(() => {
    axios.get("https://jsonplaceholder.typicode.com/users")
      .then(response => setUsers(response.data));
  }, []);

  return <ul>{users.map(user => <li key={user.id}>{user.name}</li>)}</ul>;
};
```

### useContext (Global State)
```jsx
import { createContext, useContext } from "react";

const ThemeContext = createContext("light");

const ThemedComponent = () => {
  const theme = useContext(ThemeContext);
  return <p>Current theme: {theme}</p>;
};
```

---

## 3. Props & State Management
Props allow passing data between components.
```jsx
const Welcome = ({ name }) => <h1>Welcome, {name}!</h1>;

const App = () => <Welcome name="John" />;
```

---

## 4. Event Handling
Handling user events in React.
```jsx
const Button = () => {
  const handleClick = () => alert("Button Clicked!");
  return <button onClick={handleClick}>Click Me</button>;
};
```

---

## 5. Conditional Rendering
Rendering components based on conditions.
```jsx
const UserGreeting = ({ isLoggedIn }) => (
  isLoggedIn ? <h1>Welcome Back!</h1> : <h1>Please Sign In</h1>
);
```

---

## 6. Lists & Keys
Rendering lists dynamically.
```jsx
const NamesList = ({ names }) => (
  <ul>
    {names.map((name, index) => <li key={index}>{name}</li>)}
  </ul>
);
```

---

## 7. Routing (React Router)
Using `react-router-dom` for navigation.
```jsx
import { BrowserRouter as Router, Route, Routes, Link } from "react-router-dom";

const Home = () => <h1>Home Page</h1>;
const About = () => <h1>About Page</h1>;

const App = () => (
  <Router>
    <nav>
      <Link to="/">Home</Link>
      <Link to="/about">About</Link>
    </nav>
    <Routes>
      <Route path="/" element={<Home />} />
      <Route path="/about" element={<About />} />
    </Routes>
  </Router>
);
```

---

## 8. API Calls (Axios or Fetch)
Fetching data using Axios.
```jsx
import { useEffect, useState } from "react";
import axios from "axios";

const FetchData = () => {
  const [data, setData] = useState([]);

  useEffect(() => {
    axios.get("https://jsonplaceholder.typicode.com/posts")
      .then(response => setData(response.data));
  }, []);

  return <ul>{data.map(post => <li key={post.id}>{post.title}</li>)}</ul>;
};
```

---

## 9. Context API & State Management Libraries
Global state management using Context API.
```jsx
import { createContext, useContext, useState } from "react";

const CounterContext = createContext();

const CounterProvider = ({ children }) => {
  const [count, setCount] = useState(0);
  return (
    <CounterContext.Provider value={{ count, setCount }}>
      {children}
    </CounterContext.Provider>
  );
};

const CounterDisplay = () => {
  const { count } = useContext(CounterContext);
  return <h1>Count: {count}</h1>;
};

const CounterButton = () => {
  const { setCount } = useContext(CounterContext);
  return <button onClick={() => setCount(prev => prev + 1)}>Increase</button>;
};

const App = () => (
  <CounterProvider>
    <CounterDisplay />
    <CounterButton />
  </CounterProvider>
);
```

---

## 10. Lazy Loading & Code Splitting
Using `React.lazy()` and `Suspense`.
```jsx
import { lazy, Suspense } from "react";

const LazyComponent = lazy(() => import("./LazyComponent"));

const App = () => (
  <Suspense fallback={<h1>Loading...</h1>}>
    <LazyComponent />
  </Suspense>
);
```

---

## 11. CSS & Styling
### Inline Styles
```jsx
const style = { color: "blue", fontSize: "20px" };

const StyledText = () => <p style={style}>Styled Text</p>;
```

### CSS Modules
```jsx
import styles from "./styles.module.css";

const StyledComponent = () => <p className={styles.text}>Styled Text</p>;
```

---

## 12. Form Handling & Validation
Handling forms in React.
```jsx
import { useState } from "react";

const FormExample = () => {
  const [name, setName] = useState("");

  const handleSubmit = (e) => {
    e.preventDefault();
    alert(`Submitted: ${name}`);
  };

  return (
    <form onSubmit={handleSubmit}>
      <input type="text" value={name} onChange={(e) => setName(e.target.value)} />
      <button type="submit">Submit</button>
    </form>
  );
};
```

---

## 🚀 Need help implementing any of these in your project? 😊

