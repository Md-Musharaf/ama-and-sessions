# Technical Interview Questions and Answers

## 1. Docker vs Virtual Environment

A **virtual environment** isolates only Python packages and dependencies.

**Docker** isolates the complete application environment, including Python, system libraries, configuration, and services.

| Virtual Environment | Docker |
|---|---|
| Isolates Python packages | Isolates the whole application |
| Uses the host OS | Runs in a container |
| Mainly for development | Used for development and deployment |

---

## 2. Convert ASCII Value to Character in Python

Use `chr()`:

```python
print(chr(65))
```

Output:

```text
A
```

Use `ord()` to convert a character back to its numeric value:

```python
print(ord("A"))
```

---

## 3. Direct Exchange vs Topic Exchange

A **direct exchange** sends messages when the routing key exactly matches the binding key.

A **topic exchange** uses patterns.

- `*` matches one word.
- `#` matches zero or more words.

| Direct Exchange | Topic Exchange |
|---|---|
| Exact match | Pattern match |
| Simple routing | Flexible routing |

---

## 4. What is `serializer.save()`?

In Django REST Framework, `serializer.save()` creates or updates a model object after validation.

```python
serializer = UserSerializer(data=request.data)

if serializer.is_valid():
    serializer.save()
```

- Calls `create()` for a new object.
- Calls `update()` for an existing object.

---

## 5. Authentication vs Permission

**Authentication** checks who the user is.

**Permission** checks what the user is allowed to do.

| Authentication | Permission |
|---|---|
| Identifies the user | Checks access rights |
| Example: JWT validation | Example: `IsAuthenticated` |

---

## 6. Access Token vs Refresh Token

An **access token** is used to access protected APIs.

A **refresh token** is used to generate a new access token.

| Access Token | Refresh Token |
|---|---|
| Short lifespan | Longer lifespan |
| Sent with API requests | Sent to refresh endpoint |
| Accesses protected resources | Generates a new access token |

---

## 7. What is the Use of a Celery Worker?

A Celery worker executes background tasks outside the Django request-response cycle.

Common uses:

- Sending emails
- Sending notifications
- Processing files
- Updating Elasticsearch
- Running scheduled tasks

```python
send_email.delay(user.id)
```

---

## 8. What is a Message Broker?

A message broker transfers tasks between the application and Celery workers.

```text
Django → Broker → Celery Worker
```

Common brokers:

- Redis
- RabbitMQ
- Amazon SQS

The broker stores and delivers tasks. The worker executes them.

---

## 9. Shallow Copy vs Deep Copy

A **shallow copy** creates a new outer object but shares nested objects.

A **deep copy** creates independent copies of nested objects.

```python
import copy

shallow = copy.copy(original)
deep = copy.deepcopy(original)
```

| Shallow Copy | Deep Copy |
|---|---|
| Nested objects are shared | Nested objects are independent |
| Faster | Slower |
| Uses less memory | Uses more memory |
