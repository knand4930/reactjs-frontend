# React JS Props Guide

## 1. Props Introduction
Props (short for "properties") in React are used to pass data from one component to another.

### Example:
```jsx
function Greeting(props) {
  return <h1>Hello, {props.name}!</h1>;
}

function App() {
  return <Greeting name="John" />;
}
```

---

## 2. React JS Props – Set 1
Props are immutable and help make components reusable.

### Example:
```jsx
function Welcome(props) {
  return <h1>Welcome, {props.user}!</h1>;
}

<Welcome user="Alice" />
```

---

## 3. React JS Props – Set 2
Props can be objects or functions.

### Example:
```jsx
function UserInfo(props) {
  return (
    <div>
      <h2>{props.data.name}</h2>
      <p>Age: {props.data.age}</p>
    </div>
  );
}

const userData = { name: "John", age: 30 };

<UserInfo data={userData} />
```

---

## 4. React JS PropTypes
PropTypes help validate the type of props.

### Example:
```jsx
import PropTypes from 'prop-types';

function Person(props) {
  return <h1>{props.age} years old</h1>;
}

Person.propTypes = {
  age: PropTypes.number.isRequired
};

<Person age={25} />
```

---

## 5. Passing Props
Props can be passed from one component to another.

### Example:
```jsx
function Message(props) {
  return <p>{props.text}</p>;
}

<Message text="Hello, React!" />
```

---

## 6. Pass Props from Parent to Child
Parent can pass props to child components.

### Example:
```jsx
function Child(props) {
  return <h2>{props.message}</h2>;
}

function Parent() {
  return <Child message="Hello from Parent" />;
}
```

---

## 7. Pass Props from Child to Parent
Child component can send data to the parent using a callback function.

### Example:
```jsx
function Child(props) {
  return <button onClick={() => props.handleClick("Data from child")}>Click</button>;
}

function Parent() {
  const handleData = (data) => alert(data);
  return <Child handleClick={handleData} />;
}
```

---

## 8. Access Props
Props can be accessed using `props.propertyName`.

### Example:
```jsx
function ShowProps({ name, age }) {
  return <h2>{name} is {age} years old.</h2>;
}

<ShowProps name="Alice" age={25} />
```

---

## 9. ReactJS Render Props
A render prop is a function passed as a prop to a component.

### Example:
```jsx
function RenderPropsComponent(props) {
  return <div>{props.render("John")}</div>;
}

function App() {
  return <RenderPropsComponent render={(name) => <h1>Hello, {name}!</h1>} />;
}
```

---

## 10. Unidirectional Data Flow
Data flows from parent to child, not the other way around.

### Example:
```jsx
function Parent() {
  const name = "Alice";
  return <Child name={name} />;
}
```

---

## 11. Ways to Access Props
- **Using `props` object**  
- **Using destructuring**  
- **Using default values**

### Example:
```jsx
function Example({ message = "Default Message" }) {
  return <h2>{message}</h2>;
}

<Example message="Hello, Props!" />
```

---

## 12. Prop Drilling
When props are passed through multiple components.

### Example:
```jsx
function Grandparent() {
  return <Parent message="Hello!" />;
}

function Parent(props) {
  return <Child message={props.message} />;
}

function Child(props) {
  return <h2>{props.message}</h2>;
}
```

---

## 13. React JS State vs Props

| Feature | Props | State |
|---------|------|-------|
| Mutable? | ❌ No | ✅ Yes |
| Parent Control? | ✅ Yes | ❌ No |
| Used For? | Passing data | Managing component data |

### Example:
```jsx
function Example() {
  const [count, setCount] = React.useState(0);
  return <Counter value={count} />;
}

function Counter(props) {
  return <h2>Count: {props.value}</h2>;
}
```

---

## 14. Props Validation
Ensuring the correct type of props using PropTypes.

### Example:
```jsx
import PropTypes from "prop-types";

function Product({ price }) {
  return <h2>Price: ${price}</h2>;
}

Product.propTypes = {
  price: PropTypes.number.isRequired
};
```

---

## 15. Restrict Props
Default values can restrict props.

### Example:
```jsx
function Greeting({ name = "Guest" }) {
  return <h1>Hello, {name}!</h1>;
}

<Greeting />
```

