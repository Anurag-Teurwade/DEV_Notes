
# 🚀  React.js Notes :


## 1. ⚛️ Introduction to React
React is a JavaScript library for building user interfaces. It lets you create reusable UI components and efficiently update the DOM.

### Key Features:
- **Component-Based**: Build encapsulated components that manage their own state.
- **Declarative**: Describe what the UI should look like for each state.
- **Virtual DOM**: Improves performance by minimizing direct DOM manipulation.

### Example: Hello World
```jsx
function App() {
  return <h1>Hello, React!</h1>;
}
````

---

## 2. 📝 JSX (JavaScript XML)

JSX is a syntax extension that allows HTML-like code inside JavaScript.

### Why Use JSX?

* Makes code more readable.
* Allows embedding expressions inside `{ }`.

### Example:

```jsx
const name = "John";
const element = <h1>Hello, {name}</h1>;
```

### Key Rules:

* Always return a **single root element** (use `<div>` or `<>` fragments).
* Use `className` instead of `class`.
* Close all tags (`<img />`, `<input />`).

---

## 3. 🧩 Components

### Functional Components (Recommended)

```jsx
function Greeting(props) {
  return <h1>Hello, {props.name}</h1>;
}
```

### Class Components (Legacy)

```jsx
class Greeting extends React.Component {
  render() {
    return <h1>Hello, {this.props.name}</h1>;
  }
}
```

### Props (Properties)

* Pass data from parent to child.
* **Immutable** (cannot be modified inside the component).

Example usage:

```jsx
<Greeting name="Alice" />
```

---

## 4. 🎯 State & Hooks

### `useState` (Managing State)

```jsx
import { useState } from 'react';

function Counter() {
  const [count, setCount] = useState(0);

  return (
    <button onClick={() => setCount(count + 1)}>
      Clicked {count} times
    </button>
  );
}
```

### `useEffect` (Side Effects)

* Runs after render.
* Used for API calls, subscriptions, etc.

```jsx
useEffect(() => {
  fetch('https://api.example.com/data')
    .then(response => response.json())
    .then(data => console.log(data));
}, []); // Empty dependency array means it runs once on mount
```

### Other Important Hooks

| Hook          | Purpose                                    |
| ------------- | ------------------------------------------ |
| `useContext`  | Access global state (alternative to Redux) |
| `useReducer`  | Complex state logic (like Redux)           |
| `useRef`      | Access DOM elements or persist values      |
| `useMemo`     | Optimize expensive calculations            |
| `useCallback` | Memoize functions to prevent re-renders    |

---

## 5. 🎉 Event Handling

### Handling Clicks

```jsx
function Button() {
  const handleClick = () => alert('Clicked!');
  return <button onClick={handleClick}>Click Me</button>;
}
```

### Form Handling

```jsx
function Form() {
  const [input, setInput] = useState('');

  const handleSubmit = (e) => {
    e.preventDefault();
    alert(`Submitted: ${input}`);
  };

  return (
    <form onSubmit={handleSubmit}>
      <input 
        value={input} 
        onChange={(e) => setInput(e.target.value)} 
      />
      <button type="submit">Submit</button>
    </form>
  );
}
```

---

## 6. 🔄 Conditional Rendering

### If-Else

```jsx
function Greeting({ isLoggedIn }) {
  if (isLoggedIn) {
    return <h1>Welcome back!</h1>;
  } else {
    return <h1>Please log in.</h1>;
  }
}
```

### Ternary Operator

```jsx
{isLoggedIn ? <LogoutButton /> : <LoginButton />}
```

### Logical AND (`&&`)

```jsx
{unreadMessages.length > 0 && (
  <h2>You have {unreadMessages.length} unread messages.</h2>
)}
```

---

## 7. 📋 Lists & Keys

### Rendering Lists

```jsx
const numbers = [1, 2, 3];
const listItems = numbers.map((number) => (
  <li key={number.toString()}>{number}</li>
));
```

### Why Keys?

* Helps React identify which items changed.
* Should be **unique** (use `id` instead of index).

---

## 8. 🧭 React Router (Navigation)

### Basic Setup

```jsx
import { BrowserRouter, Routes, Route, Link } from 'react-router-dom';

function App() {
  return (
    <BrowserRouter>
      <nav>
        <Link to="/">Home</Link>
        <Link to="/about">About</Link>
      </nav>
      <Routes>
        <Route path="/" element={<Home />} />
        <Route path="/about" element={<About />} />
      </Routes>
    </BrowserRouter>
  );
}
```

---

## 9. 🌐 State Management

### Context API (Global State)

```jsx
import { createContext, useContext } from 'react';

const ThemeContext = createContext('light');

function App() {
  return (
    <ThemeContext.Provider value="dark">
      <Toolbar />
    </ThemeContext.Provider>
  );
}

function Toolbar() {
  const theme = useContext(ThemeContext);
  return <div>Current theme: {theme}</div>;
}
```

### Redux (Advanced State)

```jsx
// Store setup
const store = createStore(reducer);

// Component access
const count = useSelector(state => state.count);
const dispatch = useDispatch();

<button onClick={() => dispatch({ type: 'INCREMENT' })}>+</button>
```

---

## 10. 🎨 Styling

### CSS Modules

```jsx
import styles from './App.module.css';

function App() {
  return <h1 className={styles.title}>Hello</h1>;
}
```

### Styled Components

```jsx
import styled from 'styled-components';

const Button = styled.button`
  background: ${props => props.primary ? 'blue' : 'gray'};
  color: white;
`;

<Button primary>Click Me</Button>
```

---

## 11. 🌐 API Calls

### Using `fetch`

```jsx
useEffect(() => {
  fetch('https://api.example.com/users')
    .then(res => res.json())
    .then(data => setUsers(data));
}, []);
```

### Using `axios`

```jsx
import axios from 'axios';

axios.get('https://api.example.com/users')
  .then(response => setUsers(response.data));
```

---

## 12. 🧪 Testing

### Jest + React Testing Library

```jsx
import { render, screen } from '@testing-library/react';

test('renders button', () => {
  render(<Button>Click</Button>);
  expect(screen.getByText('Click')).toBeInTheDocument();
});
```

---

## 13. ⚡ Performance Optimization

### `React.memo` (Prevent Re-renders)

```jsx
const MemoComponent = React.memo(Component);
```

### Code Splitting (Lazy Loading)

```jsx
import React, { Suspense } from 'react';

const LazyComponent = React.lazy(() => import('./Component'));

function App() {
  return (
    <Suspense fallback={<div>Loading...</div>}>
      <LazyComponent />
    </Suspense>
  );
}
```

---

## 14. 🚀 Deployment

### Build & Deploy

```bash
npm run build  # Creates optimized /build folder
# Deploy to Netlify / Vercel / GitHub Pages
```

