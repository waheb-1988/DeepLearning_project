# Text Pre-processing: Stop Words Removal using Different Libraries

## Introduction
Most human communication is in the form of text: messages, posts, calls, etc.  
To use this data in machine learning, we need **text pre-processing**. One of the most common steps is **removing stop words**.

---

## What are Stop Words?
- Words filtered out before processing natural language.
- Common words like: `the`, `a`, `an`, `so`, `what`.
- They don’t add much information.

---

## Why Remove Stop Words?
- Reduce dataset size → faster training.
- Keep only important information.

⚠️ But, stop words are not always useless. Example:

**Movie review:**  
`The movie was not good at all.`  

**After stop word removal:**  
`movie good`  

The meaning changes!  
👉 So, removal depends on the task.

---

