# Understanding Word Embeddings by Building, Not Memorizing

When I first encountered **word embeddings**, I got lost in cosine similarities, vector algebra, and high-dimensional spaces. Everyone kept saying, *“Words become vectors!”* but no one explained why that mattered — or how to use it effectively.

Then I discovered the real secret:

> **You don't need to master linear algebra to use embeddings — you just need to build something with them.**

So I stopped trying to read every academic paper and instead trained a small model that generated text using word embeddings. Suddenly, everything made more sense.

---

## 💡 What Are Word Embeddings?

Think of embeddings as **compressed knowledge** about words. They are numerical vectors that capture semantic meaning.

For example:

- “king” - “man” + “woman” ≈ “queen”
- “fast” and “quick” → vectors close together
- “Paris” - “France” + “Italy” ≈ “Rome”

Instead of treating words like arbitrary IDs, embeddings **place them in space** where meaning and relationships emerge.

---

## 🧪 Why Not One-Hot Encoding?

A one-hot vector for “neural” might look like this:

```python
[0, 0, 0, ..., 1, ..., 0]
