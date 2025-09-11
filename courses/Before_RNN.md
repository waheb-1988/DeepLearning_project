# 1. Traditional Language Models (Before RNNs)

These models tried to predict the probability of the next word in a sequence, but they did so with **fixed rules and statistics**, not neural networks.

---

## a) Unigram Model

- Each word is treated **independently**, without looking at context.  
- Probability of a sentence is just the product of word probabilities.  

**Example (English):**  
Corpus: `"I like apples. I like bananas."`  
- Probability of "like" = 2/6 = 0.33  
- Sentence probability:   P("I like apples") = P(I) × P(like) × P(apples)

**Example (Arabic):**  
Corpus: `"أنا أحب التفاح. أنا أحب الموز."`  
- Probability(أحب) = 2/6 ≈ 0.33  
- Sentence probability:  P("أنا أحب التفاح") = P(أنا) × P(أحب) × P(التفاح)

⚠️ **Problem:** No context. The word "like" (أحب) always has the same probability, even if it doesn’t fit grammatically.  

---

## b) Bigram Model

- Looks at **pairs of words** (each word depends on the **previous one**).  

**Example (English):**  
Corpus: `"I like apples. I like bananas."`  
- P(apples | like) = 0.5  
- P(bananas | like) = 0.5  
- Sentence probability:  P("I like apples") = P(I | <start>) × P(like | I) × P(apples | like)


**Example (Arabic):**  
Corpus: `"أنا أحب التفاح. أنا أحب الموز."`  
- P(التفاح | أحب) = 0.5  
- P(الموز | أحب) = 0.5  
- Sentence probability:  P("أنا أحب التفاح") = P(أنا | <start>) × P(أحب | أنا) × P(التفاح | أحب)


---

## c) Trigram Model (and higher n-grams)

- Uses **two or more previous words** to predict the next one.  
- Provides more context, but needs much more data.  

**Example (English):**  
Sentence: `"I want to eat ..."`  
- If corpus has:  
- `"I want to eat pizza"` (10 times)  
- `"I want to eat apples"` (5 times)  
- Then:  P(pizza | I want to eat) = 10 / 15


**Example (Arabic):**  
Sentence: `"أريد أن آكل ..."`  
- If corpus has:  
- `"أريد أن آكل بيتزا"` (10 مرات)  
- `"أريد أن آكل تفاح"` (5 مرات)  
- Then:  P(بيتزا | أريد أن آكل) = 10 / 15


⚠️ **Problem:** **Data sparsity** → If a phrase never appeared in training, probability becomes zero.  

---

# 2. Limitations Before RNNs

- **Fixed window**: Only looks at a short history (n words).  
- **Data sparsity**: Many possible word combinations don’t exist in training.  
- **Memory problem**: Can’t remember long context like a whole sentence or paragraph.  

---

# 3. Why RNNs Were a Big Step Forward

RNNs could:  
- ✅ Remember **longer context** (not just 2–3 words).  
- ✅ Learn **representations automatically** instead of manually counting.  
- ✅ Handle **richer, more complex dependencies** in language.  







