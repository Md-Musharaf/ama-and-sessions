# AMA

## Adhikya Edammala — What is a plugin in Claude?
A **plugin** is a packaged extension that adds reusable capabilities to Claude. It can bundle tools, skills, commands, and configuration so they can be installed and shared across projects instead of being recreated each time.

## Allanki VV Manikanta Sai — Difference between `CLAUDE.md` and `SKILLS.md`
- **`CLAUDE.md`**: Provides project-wide instructions and context that are loaded into every Claude Code session.
- **`SKILLS.md`**: Defines a reusable workflow or capability that Claude can invoke when needed. It is meant for specific tasks, not general project rules.

## Boorle Sowmya Sri Lakshmi — What is a session?
A **session** is a single interaction period between the user and the AI. It starts when you begin chatting and ends when you leave or start a new conversation. The model uses the conversation history within that session as context.

## Nayunipatruni Harsha Vardhan — What is a context window in AI models?
The **context window** is the maximum amount of text (measured in tokens) an AI model can consider at one time. It includes the system prompt, conversation history, uploaded content, and the current user message.

## Rongala Vasu — Difference between shallow copy and deep copy
- **Shallow copy**: Copies the outer object, but nested objects are still shared between the original and the copy.
- **Deep copy**: Creates completely independent copies, including all nested objects, so changes in one do not affect the other.

## Vikas Mehta — Why does `useEffect()` need a cleanup function?
A cleanup function prevents memory leaks and unwanted side effects. It runs before the effect executes again and when the component unmounts, making it useful for removing event listeners, clearing timers, canceling API requests, or unsubscribing from subscriptions.
