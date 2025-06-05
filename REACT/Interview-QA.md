
# 📘 React.js Interview Questions & Answers

---

## ✅ 1. What is React?
**Answer**: React is a JavaScript library for building user interfaces using a component-based architecture.

---

## ✅ 2. What are the key features of React?
- Declarative
- Component-Based
- Virtual DOM
- One-Way Data Binding
- JSX

---

## ✅ 3. What is JSX?
**Answer**: JSX stands for JavaScript XML. It allows writing HTML-like syntax in JavaScript.

---

## ✅ 4. What is the Virtual DOM?
**Answer**: A lightweight copy of the actual DOM that React uses to optimize rendering by diffing changes.

---

## ✅ 5. Difference between Real DOM and Virtual DOM?
| Real DOM | Virtual DOM |
|----------|--------------|
| Updates slow | Updates fast |
| Directly manipulates DOM | Uses diffing |
| More memory | Less memory |

---

## ✅ 6. What are components in React?
**Answer**: Components are independent and reusable blocks of UI in React.

---

## ✅ 7. What is the difference between Functional and Class Components?
| Functional | Class |
|------------|--------|
| Uses hooks | Uses lifecycle methods |
| Shorter syntax | More verbose |
| Recommended | Legacy |

---

## ✅ 8. What are Props?
**Answer**: Props are inputs passed from parent to child components. They are read-only.

---

## ✅ 9. What is State?
**Answer**: State is an internal data storage used to manage dynamic data in components.

---

## ✅ 10. How do you create state in a functional component?
```jsx
const [count, setCount] = useState(0);
````

---

## ✅ 11. What is `useEffect` hook?

**Answer**: A hook that handles side effects like data fetching, subscriptions, etc.

---

## ✅ 12. What are side effects in React?

**Answer**: Any action that affects something outside the component (e.g., API calls, DOM updates).

---

## ✅ 13. What is the use of `useRef`?

**Answer**: To access or persist mutable values without causing re-renders.

---

## ✅ 14. How does one handle events in React?

**Answer**: By attaching event handlers like `onClick`, `onChange` etc.

```jsx
<button onClick={handleClick}>Click</button>
```

---

## ✅ 15. What is conditional rendering?

**Answer**: Rendering different UI based on a condition.

```jsx
{isLoggedIn ? <Logout /> : <Login />}
```

---

## ✅ 16. How to pass data from child to parent?

**Answer**: By calling a parent function via props.

---

## ✅ 17. What is `useContext`?

**Answer**: A hook to access global state without prop drilling.

---

## ✅ 18. What is lifting state up?

**Answer**: Moving shared state to the closest common ancestor component.

---

## ✅ 19. What is prop drilling?

**Answer**: Passing props through multiple levels of components unnecessarily.

---

## ✅ 20. What are React Hooks?

**Answer**: Functions that let you use state and other React features in functional components.

---

## ✅ 21. List a few commonly used hooks.

* `useState`
* `useEffect`
* `useContext`
* `useRef`
* `useMemo`
* `useCallback`

---

## ✅ 22. What is `useMemo`?

**Answer**: Memoizes a computed value to avoid re-computation on every render.

---

## ✅ 23. What is `useCallback`?

**Answer**: Returns a memoized version of a function to avoid unnecessary re-renders.

---

## ✅ 24. What are React Fragments?

**Answer**: A wrapper (`<> </>`) used to group elements without adding extra nodes to the DOM.

---

## ✅ 25. What are keys in React?

**Answer**: Unique identifiers used in lists to help React identify which items changed.

---

## ✅ 26. What is React Router?

**Answer**: A library for client-side routing in React.

---

## ✅ 27. How to define routes in React Router v6?

```jsx
<Routes>
  <Route path="/" element={<Home />} />
</Routes>
```

---

## ✅ 28. What is `useNavigate` in React Router?

**Answer**: A hook to navigate programmatically between routes.

---

## ✅ 29. What is Redux?

**Answer**: A state management library for JavaScript applications.

---

## ✅ 30. What are the main principles of Redux?

* Single Source of Truth
* State is Read-Only
* Changes via Pure Functions

---

## ✅ 31. What are actions in Redux?

**Answer**: Plain JS objects with a `type` field that describe what happened.

---

## ✅ 32. What is a reducer?

**Answer**: A function that determines how state changes in response to an action.

---

## ✅ 33. What is Redux Toolkit?

**Answer**: An official, recommended way to write Redux logic with less boilerplate.

---

## ✅ 34. What are controlled components?

**Answer**: Components where form data is handled by React state.

---

## ✅ 35. What are uncontrolled components?

**Answer**: Components that store form data in the DOM itself.

---

## ✅ 36. What is React.memo?

**Answer**: A HOC that prevents re-rendering if props don’t change.

---

## ✅ 37. What is `React.lazy()`?

**Answer**: Used for lazy-loading components to reduce bundle size.

---

## ✅ 38. What is the purpose of `Suspense`?

**Answer**: To wrap lazy components and show fallback while loading.

---

## ✅ 39. How to optimize performance in React?

* Use memoization (`React.memo`, `useMemo`)
* Lazy load components
* Avoid unnecessary re-renders
* Code splitting

---

## ✅ 40. What are Higher-Order Components (HOC)?

**Answer**: Functions that take a component and return a new enhanced component.

---

## ✅ 41. Difference between `useEffect` and `useLayoutEffect`?

* `useEffect`: Runs after paint.
* `useLayoutEffect`: Runs before paint (blocking render).

---

## ✅ 42. What is the difference between `null`, `undefined`, and `false` in JSX?

All are falsy, but each may behave differently in rendering or omission.

---

## ✅ 43. What are portals in React?

**Answer**: Allows rendering children into a DOM node outside the parent hierarchy.

---

## ✅ 44. What is reconciliation in React?

**Answer**: The process of comparing the new Virtual DOM with the previous one and updating the real DOM efficiently.

---

## ✅ 45. How does React handle forms?

With controlled or uncontrolled components using `onChange`, `value`, and refs.

---

## ✅ 46. What are synthetic events in React?

**Answer**: A cross-browser wrapper around the browser’s native event.

---

## ✅ 47. What is the default behavior of form submission in React?

**Answer**: It reloads the page. Use `e.preventDefault()` to prevent this.

---

## ✅ 48. How to share code between components in React?

* Higher Order Components (HOCs)
* Render Props
* Custom Hooks

---

## ✅ 49. What is Error Boundary?

**Answer**: A component that catches JavaScript errors in its child component tree.

---

## ✅ 50. Can browsers read JSX directly?

**Answer**: No, JSX must be compiled (via Babel) into regular JavaScript.

