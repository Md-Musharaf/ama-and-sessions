
# Character Encoding

## What is Character Encoding?

**Character encoding** is the system that tells a computer **how to represent text as numbers** so it can store, process, and display characters.

A computer only understands **binary (0 and 1)**. It does **not understand letters** like `A`, `B`, or `न`.

So when you type text, the computer converts it into numbers and then into binary.

Example:

You type:

```text
A
```

The computer stores:

```text
65
```

And internally in binary:

```text
01000001
```

Later, when displaying text, it converts the number back to the character.

This conversion system is called **character encoding**.

## Why Character Encoding Exists

Computers only understand:

```text
0 and 1
```

Humans understand:

```text
A, B, C
नमस्ते
你好
😊
```

There must be a **translation layer** between human text and computer memory.

Character encoding solves this problem.

Think of it like a secret codebook:

```text
A = 65
B = 66
C = 67
```

Without this mapping, computers would not know:

- What number means `A`
- What number means `@`
- What number means `₹`
- What number means `😊`

## The Core Idea

Character encoding works in **three steps**:

### 1. Character
Human-readable symbol.

Example:

```text
M
```

### 2. Numerical Representation
Assign a number.

```text
M → 77
```

### 3. Binary Storage
Store as bits.

```text
77 → 01001101
```

That binary goes into RAM, disk, databases, or networks.

## ASCII

ASCII stands for **American Standard Code for Information Interchange**.

It uses **7 bits**, meaning:

```text
2⁷ = 128 characters
```

Examples:

```text
A → 65
B → 66
a → 97
0 → 48
@ → 64
```

ASCII supports:

- English letters
- Numbers
- Symbols
- Control characters

### Limitation

ASCII cannot represent:

```text
नमस्ते
中文
العربية
😊
```

## The Encoding Chaos

Different countries created their own encodings:

- Shift-JIS (Japan)
- KOI8-R (Russia)
- ISO-8859 (Europe)
- Windows-1252

Problem:

The same number could mean different characters.

This caused unreadable or garbled text called **mojibake**.

Example:

```text
café
```

becomes:

```text
cafÃ©
```

Or:

```text
नमस्ते
```

becomes:

```text
à¤¨à¤®à¤¸à¥à¤¤à¥
```

## Unicode: The Universal Solution

Unicode was created to support **all languages and symbols**.
Unicode is a universal character standard that allows computers to represent text from almost every language and symbol consistently.

Each character gets a unique **code point**.

Examples:

```text
A → U+0041
₹ → U+20B9
न → U+0928
😊 → U+1F60A
```

Unicode supports:

- English
- Hindi
- Arabic
- Chinese
- Japanese
- Emojis
- Mathematical symbols

### Important

**Unicode is not an encoding.**

Unicode is a **character standard**.

Storage formats include:

- UTF-8
- UTF-16
- UTF-32

## UTF-8 Explained

UTF stands for **Unicode Transformation Format**.

UTF-8 stores characters efficiently.

| Character Type | Bytes |
|---|---:|
| English | 1 byte |
| European symbols | 2 bytes |
| Asian scripts | 3 bytes |
| Emojis | 4 bytes |

Examples:

```text
A → 1 byte
₹ → 3 bytes
न → 3 bytes
😊 → 4 bytes
```

### Why UTF-8 is Popular

1. **Backward compatible with ASCII**
2. **Efficient for English**
3. **Supports all languages**
4. **Internet standard**

HTML pages often use:

```html
<meta charset="UTF-8">
```

## How Encoding Works Internally

Example: `A`

Unicode code point:

```text
U+0041
```

UTF-8 encoding:

```text
01000001
```

Example: `😊`

Unicode:

```text
U+1F60A
```

UTF-8 bytes:

```text
11110000
10011111
10011000
10001010
```

## Character Set vs Encoding

### Character Set
Defines available characters.

Example:

```text
A, B, C, ₹, 😊
```

Unicode is a character set.

### Encoding
Defines how characters are stored as bytes.

Examples:

- UTF-8
- UTF-16
- UTF-32

## UTF-8 vs UTF-16 vs UTF-32

| Feature | UTF-8 | UTF-16 | UTF-32 |
|---|---:|---:|---:|
| Variable Length | Yes | Yes | No |
| English Efficiency | Best | Medium | Poor |
| Emoji Support | Yes | Yes | Yes |
| Storage Size | Small | Medium | Large |

## Mental Model

```text
Character
     ↓
Unicode Code Point
     ↓
Encoding (UTF-8)
     ↓
Binary Storage
     ↓
Decoding
     ↓
Character Again
```
