# Django and JavaScript Short Questions and Answers

## 1. Adhikya Edammala: Difference between `AbstractUser` and `User`

- `User` is Django’s default ready-made user model.
- `AbstractUser` is used when creating a custom user model with extra or modified fields.

---

## 2. Allanki VV Manikanta Sai: Use of the Pillow library

Pillow is an image-processing library used by Django for `ImageField`, image validation, resizing, cropping, and format conversion.

```bash
pip install Pillow
```

---

## 3. Arpit Yadav: How do we log out a logged-in user in Django?

Use Django’s `logout()` function.

```python
from django.contrib.auth import logout
from django.shortcuts import redirect

def logout_view(request):
    logout(request)
    return redirect("login")
```

---

## 4. Boorle Sowmya Sri Lakshmi: Use of `{% csrf_token %}` in Django

`{% csrf_token %}` protects POST forms from Cross-Site Request Forgery attacks.

```html
<form method="POST">
    {% csrf_token %}
</form>
```

---

## 5. M Harivardhan Reddy: What is `models.PROTECT`?

`models.PROTECT` prevents a parent object from being deleted when related objects still depend on it.

```python
department = models.ForeignKey(
    Department,
    on_delete=models.PROTECT,
)
```

---

## 6. Naman Sharma: Why do we use the dotenv library?

The dotenv library loads environment variables from a `.env` file. It is used to keep secret keys, passwords, and API keys outside the source code.

```python
from dotenv import load_dotenv
load_dotenv()
```

---

## 7. Nayunipatruni Harsha Vardhan: What is `unique_together`?

`unique_together` prevents duplicate combinations of multiple model fields.

```python
class Meta:
    unique_together = ("student", "course")
```

The modern alternative is `UniqueConstraint`.

---

## 8. Parlapalli Sulochana: What are `MEDIA_ROOT` and `MEDIA_URL`?

- `MEDIA_ROOT` is the folder where uploaded files are stored.
- `MEDIA_URL` is the URL used to access uploaded files.

```python
MEDIA_ROOT = BASE_DIR / "media"
MEDIA_URL = "/media/"
```

---

## 9. Rongala Vasu: Use of the `dj-database-url` package

`dj-database-url` converts a database connection URL into Django’s `DATABASES` configuration.

```python
import dj_database_url

DATABASES = {
    "default": dj_database_url.config()
}
```

---

## 10. Rovinpal Udupi: What does `render_to_string()` do?

`render_to_string()` renders a Django template and returns the generated HTML as a Python string.

```python
from django.template.loader import render_to_string

html = render_to_string("email.html", {"name": "Musharaf"})
```

It is commonly used for HTML emails.

---

## 11. Vikas Mehta: What is event bubbling?

Event bubbling is when a JavaScript event starts on the clicked child element and then moves upward to its parent elements.

```javascript
event.stopPropagation();
```

`stopPropagation()` stops the event from bubbling.
