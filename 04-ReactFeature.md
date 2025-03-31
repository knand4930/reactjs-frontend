# React.js Features with Examples

## 1. Components
React applications are built using components. **Functional components** are preferred over class components.

### Example:
```jsx
function Greeting({ name }) {
  return <h1>Hello, {name}!</h1>;
}
```

---

## 2. Hooks
### - `useState` (Manage state)
```jsx
const [count, setCount] = useState(0);
<button onClick={() => setCount(count + 1)}>Increment</button>
```

### - `useEffect` (Side effects like API calls)
```jsx
useEffect(() => {
  console.log("Component mounted");
}, []);
```

### - `useContext` (Global state management)
```jsx
const theme = useContext(ThemeContext);
```

### - `useReducer` (Complex state logic)
```jsx
const [state, dispatch] = useReducer(reducer, initialState);
```

### - `useRef` (DOM access)
```jsx
const inputRef = useRef(null);
<input ref={inputRef} />
```

### - `useMemo` (Optimize performance)
```jsx
const expensiveCalculation = useMemo(() => compute(value), [value]);
```

### - `useCallback` (Memoize functions)
```jsx
const memoizedFunction = useCallback(() => doSomething(), []);
```

---

## 3. Props & State Management
Props pass data between components.
```jsx
<Greeting name="John" />
```
State manages component data.
```jsx
const [isOpen, setIsOpen] = useState(false);
```

---

## 4. Event Handling
Handles user interactions.
```jsx
<button onClick={() => alert("Clicked!")}>Click Me</button>
```

---

## 5. Conditional Rendering
```jsx
{isLoggedIn ? <Dashboard /> : <Login />}
```

---

## 6. Lists & Keys
```jsx
{users.map(user => <User key={user.id} name={user.name} />)}
```

---

## 7. Routing (React Router)
```jsx
<Route path="/about" element={<About />} />
```
Use `useNavigate` for navigation:
```jsx
const navigate = useNavigate();
<button onClick={() => navigate("/home")}>Go Home</button>
```

---

## 8. API Calls (Axios or Fetch)
```jsx
useEffect(() => {
  axios.get("/api/data").then(response => setData(response.data));
}, []);
```

---

## 9. Context API & State Management Libraries
Using Context API:
```jsx
const ThemeContext = createContext();
```
For large-scale apps, use **Redux**, **Zustand**, or **Recoil**.

---

## 10. Lazy Loading & Code Splitting
Load components lazily.
```jsx
const LazyComponent = React.lazy(() => import("./LazyComponent"));
```

---

## 11. Error Boundaries
Catch UI errors in class components.
```jsx
class ErrorBoundary extends React.Component {
  componentDidCatch(error, info) {
    console.log(error, info);
  }
}
```

---

## 12. React Portals
Render elements outside the parent hierarchy.
```jsx
ReactDOM.createPortal(<Modal />, document.getElementById("modal-root"));
```

---

## 13. CSS & Styling
```jsx
import "./styles.css";  // CSS file
const styles = { color: "red" };  // Inline styles
```
Libraries like **Tailwind CSS** or **Bootstrap** can be used.

---

## 14. Form Handling & Validation
```jsx
const [input, setInput] = useState("");
<input value={input} onChange={e => setInput(e.target.value)} />
```
For validation, use **Formik** or **React Hook Form**.

---

## 15. Server-Side Rendering (SSR) & Static Generation (SSG)
Use **Next.js** for SEO-friendly rendering.
```jsx
export async function getServerSideProps() {
  return { props: { data: await fetchData() } };
}
```

These features make React powerful and efficient for building modern web applications! 🚀

