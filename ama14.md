# AMA Questions and Answers

## Adhikya Edammala: What happens when we update the state without `setState`?

Updating React state directly (e.g. `state.count = 1`) does **not** trigger a re-render. React only knows that state has changed when you use `setState` (class components) or the state updater function returned by `useState` (functional components). Direct mutation can also lead to inconsistent UI and bugs.

## Allanki VV Manikanta Sai: What is Strict Mode in React?

React Strict Mode is a development-only feature that helps identify potential problems in an application. It highlights unsafe lifecycle methods, detects unexpected side effects, and intentionally invokes certain functions twice in development to help find issues. It has no effect in production builds.

## Arpit Yadav: What is Babel?

Babel is a JavaScript compiler (transpiler) that converts modern JavaScript (ES6+) and JSX into code that is compatible with older browsers. It allows developers to use the latest language features without worrying about browser support.

## Boorle Sowmya Sri Lakshmi: How do keys help in exchanges in RabbitMQ?

In RabbitMQ, routing keys determine how messages are routed from an exchange to one or more queues.
- **Direct Exchange:** Exact routing key match.
- **Topic Exchange:** Pattern matching using wildcards (`*` and `#`).
- **Fanout Exchange:** Ignores routing keys and broadcasts to all bound queues.
- **Headers Exchange:** Uses message headers instead of routing keys.

## Nayunipatruni Harsha Vardhan: Different hooks in React

Common React hooks include:
- `useState` – Manage component state.
- `useEffect` – Handle side effects.
- `useContext` – Access context values.
- `useReducer` – Manage complex state logic.
- `useRef` – Store mutable values or access DOM elements.
- `useMemo` – Memoize expensive computations.
- `useCallback` – Memoize function references.
- `useLayoutEffect` – Run effects before the browser paints.
- `useImperativeHandle` – Customize ref values.
- `useTransition`, `useDeferredValue`, `useId` – Performance and UI optimization hooks.

## Parlapalli Sulochana: What is the dependency array in `useEffect`?

The dependency array is the second argument of `useEffect`. It controls when the effect runs.
- No array: Runs after every render.
- Empty array (`[]`): Runs only once after the initial render.
- `[value]`: Runs whenever `value` changes.
- Multiple dependencies: Runs when any listed dependency changes.

## Rongala Vasu: What is the use of `useParams`?

`useParams` is a React Router hook used to access dynamic parameters from the URL. For example, for the route `/users/:id`, `useParams()` returns `{ id: "..." }`, allowing the component to use the route parameter.

## Vikas Mehta: Why do we use keys in React lists?

Keys uniquely identify list items so React can efficiently determine which items have changed, been added, or removed. This improves rendering performance and helps preserve component state. Keys should be stable and unique; avoid using array indexes when list order can change.
