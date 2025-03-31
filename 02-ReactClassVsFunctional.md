# React: Class Components vs Functional Components

## **Introduction**
React provides two ways to create components: **Class Components** and **Functional Components**. This document compares both approaches and provides code examples for a simple counter component.

---

## **Comparison Table**

| Feature              | Functional Components | Class Components |
|----------------------|----------------------|------------------|
| **Definition**       | A function that returns JSX. | A class that extends `React.Component` and has a `render()` method. |
| **State Management** | Uses hooks like `useState`. | Uses `this.state` and updates with `this.setState()`. |
| **Lifecycle Methods** | Uses `useEffect` instead of lifecycle methods. | Uses methods like `componentDidMount`, `componentDidUpdate`, etc. |
| **Syntax**          | Simpler and cleaner. | More verbose due to class syntax. |
| **Performance**     | Lightweight and faster. | Slightly heavier due to class overhead. |
| **Hooks Usage**     | Can use hooks like `useState`, `useEffect`. | Cannot use hooks. |
| **Rendering**       | Directly returns JSX. | Requires a `render()` method. |
| **Context API**     | Uses `useContext` for state management. | Uses `Context.Consumer` to access context. |

---

## **Example: Counter Component in Both Approaches**

### **1. Class Component**
```jsx
import React, { Component } from "react";

class Counter extends Component {
  constructor() {
    super();
    this.state = { count: 0 };
  }

  increment = () => {
    this.setState({ count: this.state.count + 1 });
  };

  decrement = () => {
    this.setState({ count: this.state.count - 1 });
  };

  render() {
    return (
      <div>
        <h2>Count: {this.state.count}</h2>
        <button onClick={this.increment}>Increment</button>
        <button onClick={this.decrement}>Decrement</button>
      </div>
    );
  }
}

export default Counter;
```

---

### **2. Functional Component (with Hooks)**
```jsx
import React, { useState } from "react";

const Counter = () => {
  const [count, setCount] = useState(0);

  return (
    <div>
      <h2>Count: {count}</h2>
      <button onClick={() => setCount(count + 1)}>Increment</button>
      <button onClick={() => setCount(count - 1)}>Decrement</button>
    </div>
  );
};

export default Counter;
```

---

## **Key Differences in the Example**
1. **State Handling**:
   - Class components use `this.state` and `this.setState()`.
   - Functional components use `useState()` for state management.
   
2. **Event Handling**:
   - In class components, event handlers use `this.methodName`.
   - In functional components, event handlers can be inline.

3. **Code Simplicity**:
   - The functional component is **shorter and easier** to understand.
   - The class component is **more structured but verbose**.

---

## **Conclusion**
For modern React development, **functional components with hooks** are preferred due to their simplicity and better performance.

Would you like to extend this guide with additional topics like lifecycle management (`useEffect`) or context API integration? 🚀

