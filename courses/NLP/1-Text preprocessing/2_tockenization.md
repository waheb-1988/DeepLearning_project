# Tokenization — A Complete Guide

**Author:** Utkarsh Kant  
**Summary by Phd Abdelouaheb**

---

## What is Tokenization?

Tokenization is the process of splitting a text sequence into smaller units called **tokens**.

Tokens can be:
- Characters
- Words
- Subwords
- Sentences
- Punctuations
- Special tokens (e.g., `<PAD>`, `<EOS>`)

---

## Why Tokenize?

- **Preprocessing** happens at token level (stopword removal, stemming, lemmatization).
- **Modeling** requires tokens (RNNs, Transformers process them).
- Makes text structured and machine-understandable.

---

## Types of Tokenization

1. **Word Tokenization** → splitting into words.  
2. **Sentence Tokenization** → splitting into sentences.  
3. **Character Tokenization** → splitting into characters.  

---

## A Quick Word on Linguistics

- **Prefix** → Characters at the beginning (e.g., `$10`).  
- **Suffix** → Characters at the end (e.g., `status.`).  
- **Infix** → Characters in between (e.g., `U.S.`).  
- **Exceptions** → Tokens requiring intelligence (e.g., `Dr.`, `let’s`).

---

## Tokenization Methods in Python

### 1. Using `split()`
- Simple splitting by whitespace or punctuation.
- Limitation: cannot handle edge cases (`U.S.`, `@user`, URLs).

### 2. Using **NLTK**
- `word_tokenize()` → words with punctuation.  
- `TreebankWordTokenizer` → handles contractions.  
- `WordPunctTokenizer` → separates punctuation from words.  
- `sent_tokenize()` → sentence splitting (supports multiple languages).

### 3. Using **spaCy**
- Word and sentence tokenization in 1 line (`doc = nlp(text)`).
- Handles prefixes, suffixes, infixes, and exceptions.  
- Tokens are **immutable**.  
- Supports **visualization** with `displacy`.

---

## spaCy Tokenization Workflow (under the hood)

1. Split on whitespace.  
2. Handle prefixes.  
3. Handle suffixes.  
4. Handle exceptions.  

---

## In Conclusion

- Tokenization is the **first step in NLP pipelines**.  
- **`split()`** → simple, but weak.  
- **NLTK** → stronger, but some shortcomings.  
- **spaCy** → most robust, accurate, and industry-standard.  

🏆 **Recommendation:** Use **spaCy** for production NLP tasks.

---

**Keywords:** Tokenization, NLP, NLTK, spaCy, Python, Preprocessing






https://medium.com/@utkarsh.kant/tokenization-a-complete-guide-3f2dd56c0682