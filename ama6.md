# Django Interview Questions (Short Answers)

## 1. What is `null=True` in Django ORM?

`null=True` allows a field to store **NULL** in the database.

```python
name = models.CharField(max_length=100, null=True)
```

> **Note:** `null=True` affects the database, while `blank=True` affects form validation.

---

## 2. How to install `python-dotenv`?

```bash
pip install python-dotenv
```

Usage:

```python
from dotenv import load_dotenv
import os

load_dotenv()
SECRET_KEY = os.getenv("SECRET_KEY")
```

---

## 3. How do we replace the template title?

In `base.html`:

```html
<title>{% block title %}Default{% endblock %}</title>
```

In child template:

```html
{% block title %}
Home Page
{% endblock %}
```

---

## 4. What is the use of a Slug?

A **Slug** is a URL-friendly string used to create readable and SEO-friendly URLs.

Example:

```
/posts/learn-django/
```

```python
slug = models.SlugField(unique=True)
```

---

## 5. What is WSGI?

**WSGI (Web Server Gateway Interface)** connects a web server (like Gunicorn) with your Django application.

Django creates a `wsgi.py` file automatically for deployment.

---

## 6. Difference between `CASCADE` and `PROTECT`

### `models.CASCADE`

Deleting the parent also deletes all related child objects.

### `models.PROTECT`

Prevents deleting the parent if related child objects exist.

---

## 7. What does `create_user()` do?

Creates a Django user and **automatically hashes the password**.

```python
User.objects.create_user(
    username="john",
    password="password123"
)
```

---

## 8. How does Django provide security?

Django includes built-in protection against:

- CSRF
- XSS
- SQL Injection
- Clickjacking
- Password Hashing
- Authentication & Authorization

---

## 9. What is the use of the `name` attribute in a form?

The `name` attribute identifies the input field when submitting a form.

```html
<input type="text" name="username">
```

```python
username = request.POST.get("username")
```

---

## 10. What is `form.is_valid()`?

Checks whether submitted form data passes all validations.

```python
if form.is_valid():
    form.save()
```

Returns:

- `True` → Valid
- `False` → Invalid

---

## 11. Difference between `{{ }}` and `{% %}`

### `{{ }}`

Used to display variables.

```html
{{ user.username }}
```

### `{% %}`

Used for template logic.

```html
{% for post in posts %}
{% endfor %}
```
