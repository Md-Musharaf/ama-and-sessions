# JavaScript Interview Questions – Short Answers

## 1. Adhikya Edammala: `undefined == null`, what will it return?
It returns **`true`** because loose equality (`==`) treats `null` and `undefined` as equal.

```js
undefined == null // true
```

---

## 2. Allanki VV Manikanta Sai: What is an event in JS?
An **event** is an action in the browser like click, submit, hover, or key press.

---

## 3. Arpit Yadav: Types of scopes in JS
1. **Global Scope**  
2. **Function Scope**  
3. **Block Scope**

---

## 4. Boorle Sowmya Sri Lakshmi: `instanceof`
`instanceof` checks whether an object belongs to a particular constructor/class.

```js
[] instanceof Array // true
```

---

## 5. Injamuri Arun Kumar: What is JS?
**JavaScript** is a programming language used to make web pages interactive.

---

## 6. Kamparapu Lakshman: Difference between npm and nvm
- **npm** → Used to install packages  
- **nvm** → Used to manage Node.js versions

---

## 7. M Harivardhan Reddy: How to do import and export in JS?

### Export
```js
export const name = "John";
```

### Import
```js
import { name } from "./file.js";
```

---

## 8. Naman Sharma: Difference between `null` and `undefined`
- **null** → Intentionally empty value  
- **undefined** → Variable declared but not assigned

---

## 9. Nayunipatruni Harsha Vardhan: What is scope?
**Scope** defines where a variable can be accessed.

---

## 10. Parlapalli Sulochana: Primitive vs Non-Primitive Datatypes
- **Primitive** → String, Number, Boolean, Null, Undefined, Symbol, BigInt  
- **Non-Primitive** → Object, Array, Function

---

## 11. Rongala Vasu: Synchronous vs Asynchronous
- **Synchronous** → Runs line by line  
- **Asynchronous** → Does not wait for task completion

---

## 12. Rovinpal Udupi: What is `.filter()`?
`.filter()` returns a **new array** based on a condition.

```js
[1,2,3,4].filter(n => n % 2 === 0)
```

---

## 13. Tumma Haritha: What is lexical scope?
An inner function can access variables from its outer function.

---

## 14. Vikas Mehta: `Object.freeze()` vs `Object.seal()`
- **freeze()** → Cannot add, delete, or modify properties  
- **seal()** → Can modify existing properties only

---

## 15. Yash Nitin Raut: Why use JS with HTML & CSS?
- **HTML** → Structure  
- **CSS** → Styling  
- **JS** → Functionality/Interactivity
