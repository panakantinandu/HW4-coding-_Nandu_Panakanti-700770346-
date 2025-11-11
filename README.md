```markdown
# HW4 - NLP Processing Tasks

**Student Name:** Nandu Panakanti  
**Roll No:** 700770346  

---

## 📘 Project Overview
This project demonstrates basic Natural Language Processing (NLP) operations using Python and SpaCy (and optionally NLTK).  
It includes:
1. Tokenization, stopword removal, lemmatization, and POS filtering.  
2. Named Entity Recognition (NER) and pronoun ambiguity detection.

---

## 🧠 Task Details

### **Q1: Text Preprocessing**
Steps performed:
- Tokenize the input sentence  
- Remove stopwords  
- Apply **lemmatization** (not stemming)  
- Keep only **nouns and verbs** based on POS tags  

**Input Example:**
```

"John enjoys playing football while Mary loves reading books in the library."

```

**Expected Output:**
```

['enjoy', 'play', 'football', 'love', 'read', 'book', 'library']

```

---

### **Q2: Named Entity Recognition + Pronoun Ambiguity**
- Performs **NER** using SpaCy.
- Checks for pronouns (“he”, “she”, “they”) to detect ambiguity.

**Input Example:**
```

"Chris met Alex at Apple headquarters in California. He told him about the new iPhone launch."

```

**Expected Output:**
```

Named Entities:
Chris → PERSON
Alex → PERSON
Apple → ORG
California → GPE
iPhone → PRODUCT

Warning: Possible pronoun ambiguity detected!

````

---

## ⚙️ Environment Setup

### **1️⃣ Create a Virtual Environment (Python 3.11 Recommended)**
```bash
py -3.11 -m venv spacyenv
spacyenv\Scripts\activate
````

### **2️⃣ Install Dependencies**

```bash
pip install --upgrade pip setuptools wheel
pip install spacy
python -m spacy download en_core_web_sm
```

> 💡 If SpaCy fails on your system, you can use the NLTK fallback code included.

---

## 🚀 How to Run

Save the following scripts in your project directory:

* `Q1_preprocessing.py`
* `Q2_ner_ambiguity.py`

Then execute:

```bash
python Q1_preprocessing.py
python Q2_ner_ambiguity.py
```

---

## 🧩 Dependencies

* Python 3.11
* SpaCy 3.8+
* `en_core_web_sm` language model
* (Optional) NLTK for fallback processing

---

## 📄 Output

Both scripts print results to the console.
You can redirect output to files if needed:

```bash
python Q1_preprocessing.py > output_q1.txt
python Q2_ner_ambiguity.py > output_q2.txt
```

---

## 👨‍💻 Author

**Nandu Panakanti**
Roll No: **700770346**
Department of Computer Science

```

