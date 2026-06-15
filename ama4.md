# JavaScript Interview Questions & Concepts

## 1. Can we use `const` in a `for` loop?

Yes, but it depends on the loop type.

### Works with `for...of` / `for...in`

```js
for (const item of [1, 2, 3]) {
  console.log(item);
}
```

Why?
A **new binding** is created for every iteration.

### Does NOT work with normal `for` loop

```js
for (const i = 0; i < 5; i++) {
  console.log(i);
}
```

Error because `const` cannot be reassigned (`i++`).

Correct way:

```js
for (let i = 0; i < 5; i++) {
  console.log(i);
}
```

---

## 2. What does `Object.fromEntries()` do?

Converts an array of key-value pairs into an object.

```js
const arr = [
  ["name", "Musharaf"],
  ["age", 24]
];

const obj = Object.fromEntries(arr);

console.log(obj);
```

### Output

```js
{
  name: "Musharaf",
  age: 24
}
```

It is the opposite of:

```js
Object.entries(obj)
```

---

## 3. Are strings mutable or immutable in JavaScript?

Strings are **immutable**.

You cannot modify characters directly.

```js
let str = "hello";

str[0] = "H";

console.log(str);
```

### Output

```js
hello
```

Correct way:

```js
str = "H" + str.slice(1);
```

---

## 4. Difference between `slice()` and `splice()`

| `slice()`                      | `splice()`              |
| ------------------------------ | ----------------------- |
| Does not modify original array | Modifies original array |
| Returns a copy                 | Adds/removes elements   |
| Non-mutating                   | Mutating                |

### `slice()`

```js
const arr = [1, 2, 3, 4];

console.log(arr.slice(1, 3));
```

### Output

```js
[2, 3]
```

### `splice()`

```js
const arr = [1, 2, 3, 4];

arr.splice(1, 2);

console.log(arr);
```

### Output

```js
[1, 4]
```

---

## 5. Does `setTimeout()` come with JavaScript by default?

No.

`setTimeout()` is provided by the **runtime environment**:

* Browser → Web APIs
* Node.js → Runtime APIs

It is **not part of ECMAScript (JavaScript core)**.

---

## 6. What is Event Capturing?

Event travels from **top → bottom**.

Example structure:

```html
<div>
  <button>Click</button>
</div>
```

### Event Flow

```text
document → div → button
```

Enable capturing:

```js
element.addEventListener("click", fn, true);
```

`true` enables capturing mode.

---

## 7. What is Event Delegation?

Attach a single event listener to a parent element instead of multiple child elements.

```js
document.querySelector("ul")
.addEventListener("click", (e) => {
  console.log(e.target.innerText);
});
```

### Benefits

* Better performance
* Works for dynamically added elements

---

## 8. What is HashMap in JavaScript?

JavaScript does not have a `HashMap` like Java.

Alternatives:

* Object `{}`
* `Map()`

Preferred:

```js
const map = new Map();

map.set("name", "Musharaf");

console.log(map.get("name"));
```

---

## 9. Difference between `slice()` and `substring()`

### `slice()`

Works on **strings and arrays**.

```js
"hello".slice(1, 4);
```

### Output

```js
"ell"
```

### `substring()`

Works only on **strings**.

```js
"hello".substring(1, 4);
```

### Output

```js
"ell"
```

### Key Difference

```js
str.slice(-2);
```

Works with negative index.

```js
str.substring(-2);
```

Negative values become `0`.

---

## 10. Difference between `Object.freeze()` and `Object.seal()`

### `Object.freeze()`

Cannot:

* Modify
* Add
* Remove properties

```js
const obj = { name: "Musharaf" };

Object.freeze(obj);

obj.name = "John";

console.log(obj.name);
```

### Output

```js
Musharaf
```

### `Object.seal()`

Can modify existing values but cannot add/remove properties.

```js
const obj = { name: "Musharaf" };

Object.seal(obj);

obj.name = "John";

console.log(obj.name);
```

### Output

```js
John
```

---

## 11. `.flat()` Method in Arrays

Flattens nested arrays.

```js
const arr = [1, [2, 3], [4]];

console.log(arr.flat());
```

### Output

```js
[1, 2, 3, 4]
```

Specify depth:

```js
arr.flat(2);
```

---

## 12. Difference between `let`, `var`, `const`

| Feature   | `var`    | `let`     | `const`   |
| --------- | -------- | --------- | --------- |
| Reassign  | Yes      | Yes       | No        |
| Redeclare | Yes      | No        | No        |
| Scope     | Function | Block     | Block     |
| Hoisting  | Yes      | Yes (TDZ) | Yes (TDZ) |

---

## 13. What is Variable Shadowing?

When an inner variable hides the outer variable.

```js
let a = 10;

function test() {
  let a = 20;
  console.log(a);
}

test();
console.log(a);
```

### Output

```js
20
10
```

---

## 14. `event.target` vs `event.currentTarget`

### `event.target`

The actual element clicked.

### `event.currentTarget`

The element where the event listener is attached.

```js
div.addEventListener("click", (event) => {
  console.log(event.target);
  console.log(event.currentTarget);
});
```

---

## 15. Is `const` block scope or function scope?

`const` is **block scoped**.

```js
{
  const x = 10;
}

console.log(x);
```

### Output

```js
ReferenceError: x is not defined
```

Same for `let`.

Only `var` is **function scoped**.
