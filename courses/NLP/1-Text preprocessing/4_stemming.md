# NLP: A Quick Guide to Stemming

## Introduction
**Stemming** is the process of removing suffixes from words to reduce them to their root or base form.  
It is one of the most important steps in **text pre-processing** for Natural Language Processing (NLP).

### Example
- Word: `Flying`  
- Suffix: `ing`  
- Root word: `Fly`

We use suffixes to create new words from the original stem word, but in NLP, reducing them to the base form helps simplify analysis.

---

## Word Inflections
The stem of a verb is the common part of all its inflected forms:

- wait (infinitive)  
- wait (imperative)  
- waits (present, 3rd person singular)  
- waited (past tense)  
- waiting (progressive)  

### Spelling changes in inflections
Sometimes the spelling also changes:
- `beauty` → `beautiful` (-y → -i)  
- `heavy` → `heaviness` (-y → -i)  
- `possible` → `possibility` (-le → -il)  
- `permit` → `permission` (-t → -ss)  

---

## Why Stemming in NLP?
The goal of stemming is to **reduce inflectional forms of words** into a common base.  

This helps:
- Reduce dimensionality of text data.  
- Normalize words for search engines, text classification, and topic modeling.  

---

## Errors in Stemming Algorithms
### 1. Over-stemming (False Positive)
When two unrelated words are reduced to the same stem.  
Example:
- universal  
- university  
- universe  

All reduced to `univers`, which is misleading.

### 2. Under-stemming (False Negative)
When two related words are **not** reduced to the same root.  
Example:
- alumnus  
- alumni  
- alumnae  

---

## Stemming Algorithms

### 1. Porter Stemmer
- One of the most common and oldest stemmers.  
- Fast but **not very precise**.  
- Example: `was` → `wa` (loss of meaning).  

### 2. Snowball Stemmer (Porter2)
- Improvement over the original Porter Stemmer.  
- Handles suffixes more gracefully.  
- Adds **stop word exclusion feature** (e.g., does not stem certain common words).  
- Supports multiple languages.  

### 3. Lancaster Stemmer
- Very aggressive algorithm.  
- Strongly trims down words, sometimes too much.  
- Example: `Caring` → `car` (different word altogether).  

---

## When to Apply Stemming?
- **Before stop word removal** if your dataset includes stop words with suffixes.  
- **After stop word removal** if stop words appear without inflections.  

👉 The order depends on your dataset and task.

---

## Conclusion
- Stemming is essential for reducing words to their root form in NLP.  
- **Porter** is simple and fast.  
- **Snowball** is more accurate and widely preferred.  
- **Lancaster** is aggressive and should be used carefully.  
- Always choose the stemming approach based on **your dataset and application**.  
