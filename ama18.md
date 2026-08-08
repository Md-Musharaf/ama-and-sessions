# AMA

## 1. Adhikya Edammala — What is Prompt Caching?

**Prompt caching** means temporarily storing a frequently reused part of a prompt so the model does not have to process that same content from scratch for every request.

For example, if every request contains a large system prompt, documentation, or context, we can cache that repeated content and reuse it. This can **reduce latency and input-token costs**.

**Simple example:**  
Instead of sending and processing 10,000 tokens of common instructions every time, the common portion can be cached and reused.

---

## 2. Allanki VV Manikanta Sai — What is Chain of Thought?

**Chain of Thought (CoT)** refers to the model's step-by-step reasoning process used to arrive at an answer.

For example, instead of directly answering a math problem, the model may internally reason through:

`Step 1 → Step 2 → Step 3 → Final answer`

In applications, we generally ask the model for a **concise explanation or answer rather than exposing private internal reasoning verbatim**.

---

## 3. Boorle Sowmya Sri Lakshmi — Different Types of Testing

Common types of software testing include:

- **Unit Testing** — Tests individual functions/components.
- **Integration Testing** — Tests whether multiple components work together.
- **System Testing** — Tests the complete application.
- **Functional Testing** — Verifies that features behave according to requirements.
- **Regression Testing** — Ensures new changes haven't broken existing functionality.
- **Performance Testing** — Measures speed, scalability, and resource usage.
- **Security Testing** — Identifies security vulnerabilities.
- **User Acceptance Testing (UAT)** — Validates whether the application meets business/user needs.

### GenAI/LLM Testing

For GenAI/LLM applications, additional testing can include:

- Prompt testing
- Hallucination testing
- Safety testing
- Factuality evaluation
- Output quality evaluation
- Latency testing
- Cost/token usage evaluation

---

## 4. Nayunipatruni Harsha Vardhan — Difference Between Few-Shot and Zero-Shot

| Zero-Shot | Few-Shot |
|---|---|
| No examples are provided | A few examples are provided |
| Model relies only on instructions | Model learns the expected pattern from examples |
| Simpler prompt | Larger prompt |
| Useful for straightforward tasks | Useful when the desired output format/style is specific |

### Zero-Shot Example

> Classify this review as Positive or Negative: "The product is excellent."

### Few-Shot Example

> "I love this product." → Positive  
> "The product is terrible." → Negative  
> "The product is excellent." → ?

**In short:**

- **Zero-shot = instruction only**
- **Few-shot = instruction + examples**

---

## 5. Rongala Vasu — Parameters in the Request When We Hit Claude API

When calling the **Claude API**, common request parameters include:

- **`model`** — Which Claude model to use.
- **`max_tokens`** — Maximum number of tokens Claude can generate.
- **`messages`** — The conversation/input messages.
- **`system`** — System-level instructions.
- **`temperature`** — Controls randomness/variation in the response.
- **`top_p`** — Controls token sampling based on cumulative probability.
- **`stream`** — Whether the response should be streamed incrementally.
- **`tools`** — Tools/functions that Claude can use, when applicable.
- **`tool_choice`** — Controls tool selection behavior.

> **Note:** The exact available parameters can vary by Claude API/model version, so the current Anthropic API documentation should be checked when implementing it.

---

## 6. Vikas Mehta — Why Does Every Other Message Request Consume More Tokens?

In a conversational API, the application often sends the **conversation history along with the new message**.

### Example

**Request 1:**

> User: Explain prompt caching.

**Request 2:**

> User: Explain prompt caching.  
> Assistant: [previous answer]  
> User: Give me an example.

**Request 3:**

> User: Explain prompt caching.  
> Assistant: [previous answer]  
> User: Give me an example.  
> Assistant: [previous answer]  
> User: What are its benefits?

As the conversation grows, **more previous messages are included in each request**, so the input-token count increases.
