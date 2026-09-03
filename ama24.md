content = """# AMA Q&A

---

### Adhikya Edammala — Global State Management
A centralized store that manages and shares data across an entire app, eliminating the need to pass props manually through intermediate components ("prop drilling").
* **Key examples:** Redux, Zustand, Pinia.

---

### Boorle Sowmya Sri Lakshmi — Common HTTP Codes
* **200 OK:** Request succeeded.
* **201 Created:** New resource created.
* **400 Bad Request:** Malformed client request.
* **401 Unauthorized:** Missing or invalid authentication.
* **403 Forbidden:** Authenticated, but lacking permissions.
* **404 Not Found:** Resource does not exist.
* **500 Internal Server Error:** Server-side failure.

---

### Nayunipatruni Harsha Vardhan — Context API vs. Redux
* **Context API:** Built into React; ideal for low-frequency updates (themes, auth state); causes all consuming components to re-render on change.
* **Redux:** Third-party library; ideal for large-scale, high-frequency state updates; optimized re-renders using selective subscriptions and supports middleware/DevTools.

---

### Rongala Vasu — Uses of Pydantic
* **Validation:** Enforces Python type hints at runtime and returns clear error messages.
* **Data Parsing:** Coerces input types (e.g., `"42"` to `42`) and serializes to/from JSON.
* **Configuration:** Manages `.env` files and settings in modern frameworks like FastAPI.

---

### Vikas Mehta — Response Model
A predefined schema (common in frameworks like FastAPI) that defines the structure of outgoing API data.
* **Security:** Filters out sensitive fields (e.g., passwords) before sending.
* **Consistency:** Enforces a strict data contract and auto-generates API docs (Swagger/OpenAPI).
"""

filename = "tech_qa_summary.md"
with open(filename, "w", encoding="utf-8") as f:
    f.write(content.strip() + "\n")

print(f"File created successfully: {filename}")
