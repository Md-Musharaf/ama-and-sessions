# AMA Questions & Answers

## 1. Adhikya Edammala — Can we have multiple `useEffect` in a component?

**Yes.** We can have multiple `useEffect` hooks in the same component. Each can handle a different side effect, such as API calls, event listeners, or updating the document title.

```js
useEffect(() => {
  // API call
}, []);

useEffect(() => {
  // Event listener
}, []);
```

---

## 2. Boorle Sowmya Sri Lakshmi — Can the dependency array be empty?

**Yes.** An empty dependency array `[]` means the effect runs **once after the component mounts**.

```js
useEffect(() => {
  console.log("Runs once");
}, []);
```

It's commonly used for initial API calls or setup logic.

---

## 3. Nayunipatruni Harsha Vardhan — What is the use of `useRef`?

`useRef` is mainly used to:

- Access a DOM element directly.
- Store a value that persists between renders **without causing a re-render**.

```js
const inputRef = useRef(null);

inputRef.current.focus();
```

---

## 4. Rongala Vasu — What is the use of `useMemo`?

`useMemo` is used to **memoize (cache) the result of an expensive calculation** so it doesn't have to be recalculated on every render.

```js
const result = useMemo(() => {
  return expensiveCalculation(data);
}, [data]);
```

It recalculates only when `data` changes.

---

## 5. Vikas Mehta — What is `useSelector`?

`useSelector` is a **React-Redux hook** used to read data from the Redux store.

```js
const user = useSelector(state => state.user);
```

When the selected Redux state changes, the component can re-render with the updated value.
