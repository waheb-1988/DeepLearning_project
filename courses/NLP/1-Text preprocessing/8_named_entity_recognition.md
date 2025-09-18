# Named Entity Recognition (NER) — A Practical Guide
**Author:** Phd Abdelouaheb  
**Audience:** Data scientists & NLP practitioners  
**Last updated:** 2025-09-18

---

## 1) What is NER?
**Named Entity Recognition (NER)** locates and classifies spans of text into predefined categories such as **PERSON, ORG, LOC, GPE, DATE, MONEY, PRODUCT**, etc.

Example:  
> “Apple acquired Beats for $3 billion in 2014.”  
Entities → `[Apple/ORG, Beats/ORG, $3 billion/MONEY, 2014/DATE]`

**Why it matters**
- Structure unstructured text for **search**, **analytics**, **KYC/AML**, **document understanding**, and **information extraction**.
- Downstream signals for **relation extraction**, **entity linking**, and **knowledge graphs**.

---

## 2) Common Label Sets
Typical English labels in off‑the‑shelf models (vary by library):
- **PERSON** – people, including fictional
- **ORG** – organizations: companies, agencies, institutions
- **GPE** – countries, cities, states (Geo‑Political Entity)
- **LOC** – non‑GPE locations (mountains, bodies of water)
- **PRODUCT** – vehicles, devices, etc.
- **DATE / TIME** – absolute/relative (e.g., “yesterday”, “Q3 2025”)
- **MONEY / QUANTITY / PERCENT** – amounts, measurements
- **NORP** – nationalities/religions/political groups (spaCy)
- **EVENT / WORK_OF_ART / LAW / LANGUAGE** (varies)

For multilingual/UD‑style resources see **WikiAnn**, **CoNLL**, **OntoNotes**, **MASAKHANE** datasets.

---

## 3) Approaches
1. **Rule‑based / Gazetteer**: pattern or dictionary lookup (e.g., drug names, product catalogs). Great in domains with stable vocabularies.
2. **Statistical sequence labeling**: CRF / HMM / MaxEnt; uses features like word shape, affixes, orthography.
3. **Neural**: BiLSTM‑CRF with char + word embeddings.
4. **Transformers**: BERT/RoBERTa/XLM‑R fine‑tuned as token classifiers (SOTA for many languages).
5. **Hybrid**: rules + ML; post‑processing with business constraints.

---

## 4) Data & Annotation
- **BIO/BILOU schemes**: IOB2 (`B-ORG`, `I-ORG`, `O`) or BIOES/BILOU.
- Annotation tools: **Prodigy**, **Label Studio**, **Docanno**, **spaCy’s** annotation recipes.
- Quality tips: clear **label definitions**, adjudication, and **inter‑annotator agreement**.

---

## 5) Evaluation
- **Span‑level** precision, recall, F1 (exact span + label must match).
- Report per‑label and macro/micro averages.
- Beware of **partial‑span** errors (off‑by‑one token) and **label confusion** (ORG vs PRODUCT).

---

## 6) Challenges
- **Ambiguity**: “Apple” (ORG vs PRODUCT) depending on context.
- **Domain shift**: clinical, legal, financial jargon; noisy social text.
- **Nested entities**: “University of California, Berkeley” (ORG inside GPE).
- **Low‑resource languages**: limited datasets; rely on transfer learning and weak supervision.
- **Drift**: new company names/products over time.

---

## 7) Tooling
- **spaCy**: production pipelines, `EntityRuler`, training CLI; easy deployment.
- **Hugging Face Transformers**: rich model zoo, token classification pipelines, fine‑tuning.
- **Stanza / Flair**: strong multilingual performance and embeddings.
- **Regex + Gazetteers**: great for bootstraping and precision‑critical cases.

---

## 8) Practical Recipes
### A) Quick baseline
- Use a **pretrained** NER (spaCy or HF pipeline) to tag your corpus; measure span‑level F1.

### B) Domain adaptation
- Add **EntityRuler** patterns or **gazetteers** for coverage.
- Fine‑tune a transformer on your labeled samples.

### C) Post‑processing
- Enforce constraints (e.g., money must be followed by currency).
- Merge adjacent spans; normalize (e.g., “U.S.” → “United States”).

### D) Weak supervision
- Pattern rules, dictionary matches, and distant supervision to create initial labels; then **human correction**.

---

## 9) Datasets (starter)
- **CoNLL‑2003 (EN)** — PER/ORG/LOC/MISC
- **OntoNotes 5.0** — broader label set
- **WikiAnn (PAN‑X)** — multilingual silver‑standard NER
- **WNUT** — emerging + noisy entities (social media)

---

## 10) What’s Next?
- Build a small **evaluation set** for your domain.
- Try **Entity Linking** to canonical IDs (e.g., Wikidata).
- Instrument **monitoring** to catch drift.

