# NLP Feature Extraction Methods

---

## 5 — TF-IDF (Term Frequency–Inverse Document Frequency)

### What is TF-IDF?

**TF-IDF** is a numerical statistic used in Natural Language Processing to evaluate the **importance of a word in a document** relative to a collection of documents (corpus).  

It is widely used in:
- Text classification  
- Information retrieval (search engines)  
- Document clustering  
- Recommendation systems  

---

### How it Works

1. **Document Collection**  
   Gather a set of documents to analyze.  

2. **Text Preprocessing**  
   - Lowercasing  
   - Removing punctuation/special characters  
   - Tokenization  

3. **Term Frequency (TF)**  
   Measures how often a word appears in a document.  
   \[
   TF(t,d) = \frac{\text{Number of times term } t \text{ appears in document } d}{\text{Total terms in document } d}
   \]

4. **Inverse Document Frequency (IDF)**  
   Measures how rare a word is across documents.  
   \[
   IDF(t) = \log \frac{\text{Total number of documents}}{1 + \text{Number of documents containing } t}
   \]

5. **TF-IDF Score**  
   Combines both TF and IDF:  
   \[
   TF\text{-}IDF(t,d) = TF(t,d) \times IDF(t)
   \]

- High **TF-IDF** → Word is frequent in the document but rare across corpus (important word).  
- Low **TF-IDF** → Word is common across documents (e.g., "is", "the", "also").  

