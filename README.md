### 🧾 **README.md**

```markdown
# HW4 - NLP Processing Tasks

**Student Name:** Nandu Panakanti  
**Roll Number:** 700770346  

---

## 🧠 Q1: Text Preprocessing (Tokenization, Stopword Removal, Lemmatization, POS Filtering)

### **Steps Performed**
1. **Tokenization** – The input text is split into tokens using SpaCy.  
2. **Stopword Removal** – Common English stopwords are removed using SpaCy’s `STOP_WORDS`.  
3. **Lemmatization** – Each token is lemmatized (base form) instead of stemming.  
4. **POS Filtering** – Only *nouns* and *verbs* are retained using part-of-speech tags.  

### **Input Example**
```

John enjoys playing football while Mary loves reading books in the library.

```

### **Expected Output**
```

Filtered tokens: ['enjoy', 'play', 'football', 'love', 'read', 'book', 'library']

````

### **Python Script**
```python
import spacy
from spacy.lang.en.stop_words import STOP_WORDS

nlp = spacy.load("en_core_web_sm")
text = "John enjoys playing football while Mary loves reading books in the library."

doc = nlp(text)
filtered_tokens = [
    token.lemma_
    for token in doc
    if token.pos_ in ["NOUN", "VERB"] and token.text.lower() not in STOP_WORDS
]

print("Filtered tokens:", filtered_tokens)
````

---

## 🤖 Q2: Named Entity Recognition (NER) + Pronoun Ambiguity Detection

### **Steps Performed**

1. **Named Entity Recognition (NER)** – Detects people, organizations, locations, and products using SpaCy’s pre-trained model.
2. **Pronoun Ambiguity Check** – Warns if the sentence contains pronouns like *he*, *she*, *they*, etc.

### **Input Example**

```
Chris met Alex at Apple headquarters in California. He told him about the new iPhone launch.
```

### **Expected Output**

```
Named Entities:
Chris → PERSON
Alex → PERSON
Apple → ORG
California → GPE
iPhone → PRODUCT

Warning: Possible pronoun ambiguity detected!
```

### **Python Script**

```python
import spacy

nlp = spacy.load("en_core_web_sm")
text = "Chris met Alex at Apple headquarters in California. He told him about the new iPhone launch."

doc = nlp(text)

print("Named Entities:")
for ent in doc.ents:
    print(f"{ent.text} → {ent.label_}")

pronouns = {"he", "she", "they", "him", "her", "them"}
if any(token.text.lower() in pronouns for token in doc):
    print("\nWarning: Possible pronoun ambiguity detected!")
```

---

## ⚙️ Setup Instructions

### **Environment Setup (Recommended Method)**

```bash
# 1. Create virtual environment (Python 3.11)
py -3.11 -m venv spacyenv

# 2. Activate it
spacyenv\Scripts\activate

# 3. Install dependencies
pip install --upgrade pip setuptools wheel
pip install spacy
python -m spacy download en_core_web_sm
```

---

## ✅ Verification

Run:

```bash
python -m spacy validate
```

Expected result: `✔ OK` next to `en_core_web_sm`.

---

## 🧩 Output Verification

Both scripts will print the filtered tokens and entities directly in the console.
All outputs are deterministic — you should get the same results every time.

---

**Submitted by:**
📛 *Nandu Panakanti (700770346)*
📅 *Date:* November 2025
```

---

Do you want me to make it a downloadable `.md` file so you can place it directly into your assignment folder?
```
