# AMA Questions & Answers

## Adhikya Edammala: What is `id()` function in Python?

`id()` returns the unique identity (memory address-like value) of an object.

```python
x = 5
print(id(x))
```

---

## Allanki VV Manikanta Sai: Difference between for and while loop

* `for` → used when number of iterations is known
* `while` → used when condition-based looping

```python
for i in range(3):
    print(i)

i = 0
while i < 3:
    print(i)
    i += 1
```

---

## Arpit Yadav: What is inode in Linux?

An inode is a data structure that stores file metadata (not filename), like size, permissions, and location.

---

## Boorle Sowmya Sri Lakshmi: Private and protected variables in Python

* `_var` → protected (convention)
* `__var` → private (name mangling)

```python
class A:
    def __init__(self):
        self._x = 10
        self.__y = 20
```

---

## Injamuri Arun Kumar: Is address of x = 5 and y = 5 same?

Yes, Python reuses memory for small integers.

```python
x = 5
y = 5
print(id(x) == id(y))  # True
```

---

## Kamparapu Lakshman: Shallow vs Deep copy

* Shallow copy → copies references of nested objects
* Deep copy → copies everything independently

```python
import copy

a = [[1, 2]]
b = copy.copy(a)
c = copy.deepcopy(a)
```

---

## M Harivardhan Reddy: Can we create object of abstract class?

No, abstract class cannot be instantiated directly.

```python
from abc import ABC, abstractmethod

class A(ABC):
    @abstractmethod
    def show(self):
        pass

# A() ❌ not allowed
```

---

## Naman Sharma: Primary key vs Composite key

* Primary key → single column unique ID
* Composite key → combination of columns

```sql
PRIMARY KEY (id)
PRIMARY KEY (id, email)
```

---

## Nayunipatruni Harsha Vardhan: Single line and multiline comments

* Single line: `# comment`
* Multiline: `''' comment '''` or `""" comment """`

```python
# single line

"""
multi
line
"""
```

---

## Parlapalli Sulochana: Exception type of missing dictionary key

`KeyError`

```python
d = {"a": 1}
print(d["b"])  # KeyError
```

---

## Rongala Vasu: Does Python support multiple inheritance?

Yes, Python supports multiple inheritance.

```python
class A: pass
class B: pass
class C(A, B): pass
```

---

## Rovinpal Udupi: pass in Python

`pass` is a placeholder statement used when no code is needed.

```python
if True:
    pass
```

---

## Tumma Haritha: Can dictionary keys be duplicated?

No, dictionary keys must be unique. Duplicate keys overwrite values.

```python
d = {"a": 1, "a": 2}
print(d)  # {'a': 2}
```

---

## Vikas Mehta: Methods vs Functions

* Function → independent block
* Method → function inside a class

```python
def fun():
    pass

class A:
    def method(self):
        pass
```

---

## Yash Nitin Raut: Convert string to int in Python

Use `int()` function.

```python
s = "123"
n = int(s)
print(n)
```
