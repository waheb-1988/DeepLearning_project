# Regular Expressions (Regex) in Python

## Introduction
Regular Expressions (Regex) are sequences of characters that define search patterns in text.  
They are used in:
- **NLP** (tokenization, cleaning)
- **Web scraping**
- **Data validation**
- **Search engines**
- **Text manipulation**

Regex is supported across many programming languages, making it a **universal tool** for text processing.

---

## Basic Regex Characters

| Symbol | Meaning | Example | Matches |
|--------|---------|---------|---------|
| `.`    | Any character | `a.c` | `abc`, `axc` |
| `\d`   | Digit (0–9) | `\d\d` | `12`, `99` |
| `\D`   | Not a digit | `\D+` | `abc`, `!@` |
| `\w`   | Word char (A–Z, a–z, 0–9, _) | `\w+` | `hello_123` |
| `\W`   | Not a word char | `\W+` | `!!`, `@#` |
| `\s`   | Whitespace (space, tab, newline) | `\s+` | `" "` |
| `\S`   | Not whitespace | `\S+` | `hello` |
| `^`    | Start of string | `^Hello` | `"Hello world"` |
| `$`    | End of string | `world$` | `"Hello world"` |

---

## Groupings & Alternation
- **Character class**: `[aeiou]` → matches any vowel.  
- **Negated class**: `[^aeiou]` → matches any non-vowel.  
- **Alternation**: `(cat|dog)` → matches either `"cat"` or `"dog"`.  
- **Capturing groups**: `(abc)` → extracts `"abc"`.

---

## Quantifiers
- `*` → 0 or more  
- `+` → 1 or more  
- `?` → 0 or 1  
- `{n}` → exactly n times  
- `{n,m}` → between n and m times  

Example:  
- `\d{3}` → 3 digits  
- `a{2,4}` → `"aa"`, `"aaa"`, `"aaaa"`

---

## Real-World Examples

### 1. Splitting Names
```regex
(Mr|Ms|Miss|Mrs|Dr|Alhaji|Sis)\s+(\w+)\s+(\w+)
```

### 2. Phone Numbers
```regex
(\+\d+)\-(\d+)
```

### 3. Addresses
```regex
(\w+)\s+(\w+)\,\s+(\w+)
```


