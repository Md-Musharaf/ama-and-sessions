## 1. Adhikya Edammala — Command to create a Django project

```bash
django-admin startproject project_name
```

Example:

```bash
django-admin startproject config
```

This creates a new Django project named `config`.

You can also use:

```bash
python -m django startproject config
```

To run the project:

```bash
python manage.py runserver
```

---

## 2. Allanki V. V. Manikanta Sai — What is `import os`?

```python
import os
```

`os` is a built-in Python module used to interact with the operating system.

It can be used for:

- Reading environment variables
- Working with files and folders
- Creating or deleting directories
- Constructing file paths
- Getting the current working directory

Example:

```python
import os

secret_key = os.environ.get("SECRET_KEY")
```

In Django, it is commonly used to read sensitive values such as secret keys, database credentials, and API keys from environment variables.

---

## 3. Boorle Sowmya Sri Lakshmi — What are generic views?

Generic views are built-in Django class-based views that provide commonly required functionality.

Instead of writing the complete logic manually, we can use generic views for operations such as:

- Displaying a list of objects
- Displaying one object
- Creating an object
- Updating an object
- Deleting an object

Common generic views include:

```python
ListView
DetailView
CreateView
UpdateView
DeleteView
```

Example:

```python
from django.views.generic import ListView
from .models import Question


class QuestionListView(ListView):
    model = Question
    template_name = "questions/question_list.html"
    context_object_name = "questions"
```

`ListView` automatically gets all `Question` objects and sends them to the template.

Generic views reduce repeated code and follow Django’s standard conventions.

---

## 4. Naman Sharma — What is `PermissionDenied`?

`PermissionDenied` is a Django exception used when a user is not allowed to perform a particular action.

It is imported using:

```python
from django.core.exceptions import PermissionDenied
```

Example:

```python
def edit_question(request, question_id):
    question = Question.objects.get(id=question_id)

    if question.author != request.user:
        raise PermissionDenied

    # Continue with editing
```

In this example, only the author of the question can edit it.

When Django raises `PermissionDenied`, it normally returns an HTTP **403 Forbidden** response.

---

## 5. Nayunipatruni Harsha Vardhan — What are `select_related()` and `prefetch_related()`?

Both are Django ORM methods used to reduce the number of database queries.

### `select_related()`

`select_related()` is used for single-valued relationships:

- `ForeignKey`
- `OneToOneField`

It performs an SQL `JOIN` and retrieves related data in the same database query.

Example:

```python
questions = Question.objects.select_related("author")
```

Without `select_related()`:

```python
for question in questions:
    print(question.author.email)
```

Django may execute one query for the questions and additional queries for every author.

With `select_related()`, the question and author data are retrieved together.

### `prefetch_related()`

`prefetch_related()` is used for multi-valued relationships:

- `ManyToManyField`
- Reverse `ForeignKey`
- Nested related collections

Example:

```python
questions = Question.objects.prefetch_related("answers")
```

It executes separate queries for questions and answers, then combines the results in Python.

### Main difference

```text
select_related()   → ForeignKey and OneToOneField
prefetch_related() → ManyToMany and reverse ForeignKey
```

Example using both:

```python
questions = (
    Question.objects
    .select_related("author")
    .prefetch_related("answers", "topics")
)
```

---

## 6. Parlapalli Sulochana — When do we get 403 Forbidden?

A **403 Forbidden** response means that the server understood the request, but the user is not permitted to perform the requested action.

Common reasons include:

### Permission failure

```python
from django.core.exceptions import PermissionDenied

if request.user != question.author:
    raise PermissionDenied
```

### CSRF verification failure

A POST form without a valid CSRF token may return 403.

```html
<form method="POST">{% csrf_token %}</form>
```

### Insufficient user role

For example, a normal user attempts to access an administrator-only page.

### Custom authorization rules

A logged-in user may attempt to edit or delete another user’s content.

The difference between 401 and 403 is:

```text
401 Unauthorized → Authentication is missing or invalid.
403 Forbidden    → The user is recognized but does not have permission.
```

---

## 7. Rongala Vasu — What is the use of Pillow?

Pillow is a Python image-processing library.

In Django, Pillow is required when using `ImageField`.

Installation command:

```bash
pip install Pillow
```

Example model:

```python
from django.db import models


class Profile(models.Model):
    profile_picture = models.ImageField(
        upload_to="profile_pictures/",
        blank=True,
        null=True,
    )
```

Pillow can be used to:

- Upload images
- Open and save images
- Resize images
- Crop images
- Rotate images
- Convert image formats
- Compress images
- Validate image files

Example:

```python
from PIL import Image

image = Image.open("photo.jpg")
image = image.resize((300, 300))
image.save("resized_photo.jpg")
```

---

## 8. Rovinpal Udupi — What is Gunicorn?

Gunicorn stands for **Green Unicorn**.

It is a production-grade WSGI HTTP server used to run Python web applications such as Django applications.

Django’s development server:

```bash
python manage.py runserver
```

is meant only for development. It should normally not be used in production.

Gunicorn installation:

```bash
pip install gunicorn
```

Run a Django project using:

```bash
gunicorn config.wsgi:application
```

Here:

- `config` is the Django project folder.
- `wsgi` refers to `wsgi.py`.
- `application` is the WSGI application object.

In production, the request flow is commonly:

```text
User → Nginx → Gunicorn → Django application
```

Gunicorn manages worker processes and allows the Django application to handle multiple requests efficiently.

---

## 9. Vikas Mehta — What is a closure?

A closure is a nested function that remembers variables from its outer function even after the outer function has finished executing.

Example:

```python
def multiplier(number):
    def multiply(value):
        return number * value

    return multiply


double = multiplier(2)
print(double(5))
```

Output:

```text
10
```

Here, `multiply()` remembers the value of `number`, even after `multiplier()` has completed.

Another example:

```python
def greeting(message):
    def show_greeting(name):
        return f"{message}, {name}"

    return show_greeting


hello = greeting("Hello")
print(hello("Musharaf"))
```

Output:

```text
Hello, Musharaf
```

A closure generally requires:

1. A nested function
2. The nested function must use a variable from the outer function
3. The outer function must return the nested function

Closures are useful for:

- Creating function factories
- Maintaining private state
- Decorators
- Callbacks
- Customizing function behaviour
