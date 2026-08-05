# AMA Questions and Answers

## Adhikya Edammala — What is a Plugin in Claude?

A **plugin** in Claude is an integration that extends Claude's capabilities by allowing it to interact with external tools, services, or APIs. While Claude itself is a language model, plugins enable it to perform actions or retrieve information from outside its built-in knowledge.

### What plugins can do
- Search the web for up-to-date information
- Read and write files
- Access databases
- Connect to third-party APIs
- Automate workflows
- Integrate with development tools

### Benefits
- Access to real-time information
- Ability to perform actions beyond text generation
- Improved productivity through automation
- Integration with external applications and services

**Example:** A GitHub plugin could allow Claude to analyze repositories, review pull requests, or summarize code changes.

---

## Allanki VV Manikanta Sai — Difference Between `CLAUDE.md` and `skills.md`

Both files help Claude work more effectively, but they serve different purposes.

| Feature | `CLAUDE.md` | `skills.md` |
|----------|-------------|-------------|
| Purpose | Provides project-wide instructions | Defines reusable workflows or capabilities |
| Scope | Entire repository/project | Specific task or skill |
| Contains | Coding standards, architecture, conventions, project rules | Step-by-step instructions, tool usage, best practices |
| Usage | Automatically provides context for the project | Used when the related skill is required |
| Reusability | Usually project-specific | Can often be reused across projects |
| Goal | Tell Claude how to behave in the project | Teach Claude how to perform a task |

### Example

**CLAUDE.md**
```text
- Use TypeScript.
- Follow Clean Architecture.
- Write unit tests.
- Use ESLint formatting.
```

**skills.md**
```text
Skill: Create REST API

Steps:
1. Create controller.
2. Add service layer.
3. Add validation.
4. Write unit tests.
5. Update API documentation.
```

### Summary

- **`CLAUDE.md`** = Project instructions and coding guidelines.
- **`skills.md`** = Reusable instructions for performing a specific task.

---

## Boorle Sowmya Sri Lakshmi — What is a Session?

A **session** is a continuous conversation between a user and an AI assistant during which the AI remembers previous messages and uses them as context.

### During a session
- Previous questions and answers are remembered.
- The AI can refer back to earlier parts of the conversation.
- Context is maintained until the conversation ends or the context window is exceeded.

### Why sessions are useful
- More natural conversations
- No need to repeat information
- Better continuity across multiple questions
- Personalized responses based on earlier discussion

### Example

**User:**
> My name is Rahul.

**User (later):**
> What's my name?

**AI:**
> Your name is Rahul.

The AI can answer because the information is still available within the current session.

---

## Nayunipatruni Harsha Vardhan — What is a Context Window in AI Models?

A **context window** is the maximum amount of text (measured in **tokens**) that an AI model can process at one time. It includes everything the model considers before generating a response.

### The context window includes
- System instructions
- User prompts
- Previous conversation history
- The AI's previous responses

### Why it matters
A larger context window allows AI models to:
- Handle longer conversations
- Understand large documents
- Analyze lengthy codebases
- Maintain context across many interactions

### Example

Suppose an AI model has a **128K-token context window**.

It can process approximately:
- Hundreds of pages of text
- Large code repositories
- Long chat histories

If the total conversation exceeds the context window, the oldest information is removed to make room for new content.

### Benefits of larger context windows
- Better long-term memory within a conversation
- Improved document summarization
- Better code understanding
- Fewer repeated explanations

---

## Rongala Vasu — Difference Between Shallow Copy and Deep Copy

A **copy** creates a new object from an existing object. The difference lies in how nested objects are handled.

| Feature | Shallow Copy | Deep Copy |
|----------|--------------|-----------|
| Copies top-level properties | ✅ Yes | ✅ Yes |
| Copies nested objects | ❌ No (shares references) | ✅ Yes (creates new copies) |
| Nested changes affect original | ✅ Yes | ❌ No |
| Memory usage | Lower | Higher |
| Performance | Faster | Slower |
| Use case | Simple objects | Complex nested objects |

### Shallow Copy Example

```javascript
const original = {
  name: "John",
  address: {
    city: "Hyderabad"
  }
};

const shallow = { ...original };

shallow.address.city = "Bangalore";

console.log(original.address.city);
// Output: Bangalore
```

The nested object is shared, so changing it affects both objects.

### Deep Copy Example

```javascript
const original = {
  name: "John",
  address: {
    city: "Hyderabad"
  }
};

const deep = structuredClone(original);

deep.address.city = "Chennai";

console.log(original.address.city);
// Output: Hyderabad
```

The nested object is completely independent.

### When to use

**Use shallow copy when:**
- Objects are simple.
- No nested object modifications are required.

**Use deep copy when:**
- Objects contain nested structures.
- Independent copies are needed.

---

## Vikas Mehta — Why Does `useEffect()` Need a Cleanup Function?

In React, the **cleanup function** inside `useEffect()` is used to release resources and prevent unwanted side effects when a component re-renders or unmounts.

### Why cleanup is important

Without cleanup:
- Memory leaks can occur.
- Multiple event listeners may accumulate.
- Timers continue running.
- API requests may complete after the component is removed.
- WebSocket connections remain open.

### When React calls cleanup

React executes the cleanup function:
1. Before running the effect again (if dependencies change).
2. When the component is removed (unmounted).

### Syntax

```javascript
useEffect(() => {
  // Setup

  return () => {# AI & Programming Interview Questions and Answers

## Adhikya Edammala — What is a Plugin in Claude?

A **plugin** in Claude is an integration that extends Claude's capabilities by allowing it to interact with external tools, services, or APIs. While Claude itself is a language model, plugins enable it to perform actions or retrieve information from outside its built-in knowledge.

### What plugins can do
- Search the web for up-to-date information
- Read and write files
- Access databases
- Connect to third-party APIs
- Automate workflows
- Integrate with development tools

### Benefits
- Access to real-time information
- Ability to perform actions beyond text generation
- Improved productivity through automation
- Integration with external applications and services

**Example:** A GitHub plugin could allow Claude to analyze repositories, review pull requests, or summarize code changes.

---

## Allanki VV Manikanta Sai — Difference Between `CLAUDE.md` and `skills.md`

Both files help Claude work more effectively, but they serve different purposes.

| Feature | `CLAUDE.md` | `skills.md` |
|----------|-------------|-------------|
| Purpose | Provides project-wide instructions | Defines reusable workflows or capabilities |
| Scope | Entire repository/project | Specific task or skill |
| Contains | Coding standards, architecture, conventions, project rules | Step-by-step instructions, tool usage, best practices |
| Usage | Automatically provides context for the project | Used when the related skill is required |
| Reusability | Usually project-specific | Can often be reused across projects |
| Goal | Tell Claude how to behave in the project | Teach Claude how to perform a task |

### Example

**CLAUDE.md**
```text
- Use TypeScript.
- Follow Clean Architecture.
- Write unit tests.
- Use ESLint formatting.
```

**skills.md**
```text
Skill: Create REST API

Steps:
1. Create controller.
2. Add service layer.
3. Add validation.
4. Write unit tests.
5. Update API documentation.
```

### Summary

- **`CLAUDE.md`** = Project instructions and coding guidelines.
- **`skills.md`** = Reusable instructions for performing a specific task.

---

## Boorle Sowmya Sri Lakshmi — What is a Session?

A **session** is a continuous conversation between a user and an AI assistant during which the AI remembers previous messages and uses them as context.

### During a session
- Previous questions and answers are remembered.
- The AI can refer back to earlier parts of the conversation.
- Context is maintained until the conversation ends or the context window is exceeded.

### Why sessions are useful
- More natural conversations
- No need to repeat information
- Better continuity across multiple questions
- Personalized responses based on earlier discussion

### Example

**User:**
> My name is Rahul.

**User (later):**
> What's my name?

**AI:**
> Your name is Rahul.

The AI can answer because the information is still available within the current session.

---

## Nayunipatruni Harsha Vardhan — What is a Context Window in AI Models?

A **context window** is the maximum amount of text (measured in **tokens**) that an AI model can process at one time. It includes everything the model considers before generating a response.

### The context window includes
- System instructions
- User prompts
- Previous conversation history
- The AI's previous responses

### Why it matters
A larger context window allows AI models to:
- Handle longer conversations
- Understand large documents
- Analyze lengthy codebases
- Maintain context across many interactions

### Example

Suppose an AI model has a **128K-token context window**.

It can process approximately:
- Hundreds of pages of text
- Large code repositories
- Long chat histories

If the total conversation exceeds the context window, the oldest information is removed to make room for new content.

### Benefits of larger context windows
- Better long-term memory within a conversation
- Improved document summarization
- Better code understanding
- Fewer repeated explanations

---

## Rongala Vasu — Difference Between Shallow Copy and Deep Copy

A **copy** creates a new object from an existing object. The difference lies in how nested objects are handled.

| Feature | Shallow Copy | Deep Copy |
|----------|--------------|-----------|
| Copies top-level properties | ✅ Yes | ✅ Yes |
| Copies nested objects | ❌ No (shares references) | ✅ Yes (creates new copies) |
| Nested changes affect original | ✅ Yes | ❌ No |
| Memory usage | Lower | Higher |
| Performance | Faster | Slower |
| Use case | Simple objects | Complex nested objects |

### Shallow Copy Example

```javascript
const original = {
  name: "John",
  address: {
    city: "Hyderabad"
  }
};

const shallow = { ...original };

shallow.address.city = "Bangalore";

console.log(original.address.city);
// Output: Bangalore
```

The nested object is shared, so changing it affects both objects.

### Deep Copy Example

```javascript
const original = {
  name: "John",
  address: {
    city: "Hyderabad"
  }
};

const deep = structuredClone(original);

deep.address.city = "Chennai";

console.log(original.address.city);
// Output: Hyderabad
```

The nested object is completely independent.

### When to use

**Use shallow copy when:**
- Objects are simple.
- No nested object modifications are required.

**Use deep copy when:**
- Objects contain nested structures.
- Independent copies are needed.

---

## Vikas Mehta — Why Does `useEffect()` Need a Cleanup Function?

In React, the **cleanup function** inside `useEffect()` is used to release resources and prevent unwanted side effects when a component re-renders or unmounts.

### Why cleanup is important

Without cleanup:
- Memory leaks can occur.
- Multiple event listeners may accumulate.
- Timers continue running.
- API requests may complete after the component is removed.
- WebSocket connections remain open.

### When React calls cleanup

React executes the cleanup function:
1. Before running the effect again (if dependencies change).
2. When the component is removed (unmounted).

### Syntax

```javascript
useEffect(() => {
  // Setup

  return () => {
    // Cleanup
  };
}, []);
```

### Example 1: Clearing an Interval

```javascript
useEffect(() => {
  const interval = setInterval(() => {
    console.log("Running...");
  }, 1000);

  return () => {
    clearInterval(interval);
  };
}, []);
```

Without cleanup, the interval continues running even after the component is removed.

---

### Example 2: Removing an Event Listener

```javascript
useEffect(() => {
  function handleResize() {
    console.log(window.innerWidth);
  }

  window.addEventListener("resize", handleResize);

  return () => {
    window.removeEventListener("resize", handleResize);
  };
}, []);
```

Without cleanup, multiple event listeners may be added, causing duplicate executions.

---

### Example 3: Cancelling an API Request

```javascript
useEffect(() => {
  const controller = new AbortController();

  fetch("/api/users", {
    signal: controller.signal
  });

  return () => {
    controller.abort();
  };
}, []);
```

If the component unmounts before the request completes, the cleanup cancels the request to prevent unnecessary work.

### Common cleanup tasks

- Remove event listeners
- Clear timers (`setTimeout`, `setInterval`)
- Cancel API requests
- Close WebSocket connections
- Unsubscribe from subscriptions
- Disconnect observers

### Benefits of cleanup

- Prevents memory leaks
- Improves application performance
- Avoids duplicate side effects
- Ensures proper resource management
- Keeps React components predictable and efficient
    // Cleanup
  };
}, []);
```

### Example 1: Clearing an Interval

```javascript
useEffect(() => {
  const interval = setInterval(() => {
    console.log("Running...");
  }, 1000);

  return () => {
    clearInterval(interval);
  };
}, []);
```

Without cleanup, the interval continues running even after the component is removed.

---

### Example 2: Removing an Event Listener

```javascript
useEffect(() => {
  function handleResize() {
    console.log(window.innerWidth);
  }

  window.addEventListener("resize", handleResize);

  return () => {
    window.removeEventListener("resize", handleResize);
  };
}, []);
```

Without cleanup, multiple event listeners may be added, causing duplicate executions.

---

### Example 3: Cancelling an API Request

```javascript
useEffect(() => {
  const controller = new AbortController();

  fetch("/api/users", {
    signal: controller.signal
  });

  return () => {
    controller.abort();
  };
}, []);
```

If the component unmounts before the request completes, the cleanup cancels the request to prevent unnecessary work.

### Common cleanup tasks

- Remove event listeners
- Clear timers (`setTimeout`, `setInterval`)
- Cancel API requests
- Close WebSocket connections
- Unsubscribe from subscriptions
- Disconnect observers

### Benefits of cleanup

- Prevents memory leaks
- Improves application performance
- Avoids duplicate side effects
- Ensures proper resource management
- Keeps React components predictable and efficient
