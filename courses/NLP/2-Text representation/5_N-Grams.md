# NLP Feature Extraction Methods

---

## 4 — N-grams

### What are N-grams?

**N-grams** are contiguous sequences of **n items** (usually words) from a given text.  
- **Unigrams (1-grams):** single words (e.g., `"cat"`, `"dog"`).  
- **Bigrams (2-grams):** consecutive word pairs (e.g., `"natural language"`, `"deep learning"`).  
- **Trigrams (3-grams):** consecutive triplets (e.g., `"machine learning model"`).  
- **4-grams, 5-grams, ...:** longer word sequences.  

Depending on the value of `n`, we capture different levels of context.

---

### Why are N-grams Important?

1. **Capture context & semantics** – unlike Bag of Words, N-grams retain local word order.  
2. **Improve language models** – widely used in statistical language models, machine translation, and speech recognition.  
3. **Enhance predictive text** – used in autocomplete and next-word prediction.  
4. **Feature extraction** – help in text classification, sentiment analysis, and information retrieval.  
5. **Search & retrieval** – used by search engines to improve relevance ranking.  


