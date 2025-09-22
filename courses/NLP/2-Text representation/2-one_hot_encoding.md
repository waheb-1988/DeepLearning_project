# NLP Feature Extraction Methods

---

## 2 — One Hot Encoding

### What is One Hot Encoding?

**One Hot Encoding** is a technique used to convert **categorical variables** into **binary vectors**.  
Each category is represented by a vector where only **one element is “hot” (1)** and the others are **“cold” (0)**.

✅ **Advantages:**
- Preserves categorical meaning without implying any ordinal relationship.
- Works well when the number of categories is relatively small.

⚠️ **Limitations:**
- If the number of categories is large, it generates many columns, leading to:
  - Data expansion.
  - Increased computational cost and processing time.

