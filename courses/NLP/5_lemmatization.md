# Lemmatization in NLP

## Introduction
Lemmatization is a more advanced and accurate form of **text normalization** compared to stemming.  
Instead of chopping off word endings, it considers the **meaning** and **part of speech (POS)** of the word to reduce it to its **base or root form (lemma)**.

Example:
- **Stemming:** "running" → "runn" (incorrect meaning)
- **Lemmatization:** "running" → "run" ✅

---

## Key Concepts
- **Lemma**: The base form of a word.
  - "better" → "good"
  - "was" → "be"
- **Part of Speech (POS)**: Determines the correct lemma.
  - "running" (verb) → "run"
  - "running" (noun) → "running"

---

## How Lemmatization Works
1. Looks up the correct base form in a lexical database (like **WordNet**).
2. Uses **POS tagging** to determine the role of each word.
3. Returns the correct lemma depending on context.

---
