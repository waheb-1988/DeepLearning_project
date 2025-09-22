# NLP Feature Extraction Methods

In Natural Language Processing (NLP), categorical variables such as text labels often need to be converted into numerical form before they can be used in machine learning models. One of the most basic techniques for this is **Label Encoding**.

---

## 1 — Label Encoding

### What is Label Encoding?

Label Encoding is a technique used to convert **categorical variables (texts)** into **numerical representations**.  
Each unique category is assigned a unique integer value.

✅ **Advantages:**
- Simple and fast to implement.
- Useful when categories are **ordinal** (have a natural order).

⚠️ **Limitations:**
- The encoder does not understand the relationship between categories.  
  For example, it cannot recognize that "nurse" and "doctor" are closer in meaning than "doctor" and "police".

