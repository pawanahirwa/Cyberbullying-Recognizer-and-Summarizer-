# 🛡️ Cyberbullying Recognizer & Text Summarizer

A Python CLI application that detects hate speech / offensive language in text using an NLP model trained on Twitter data, and summarizes long text inputs using an extractive summarization algorithm powered by SpaCy.

---

## 📋 Table of Contents
- [Overview](#overview)
- [Features](#features)
- [Dataset](#dataset)
- [Project Workflow](#project-workflow)
- [Model & Results](#model--results)
- [Tech Stack](#tech-stack)
- [How to Run](#how-to-run)
- [Project Structure](#project-structure)
- [Screenshots](#screenshots)

---

## 📌 Overview

Cyberbullying is a growing digital threat — it can cause anxiety, depression, and lasting psychological harm. This project builds a tool that:

1. **Detects** whether a given text contains hate speech, offensive language, or is clean
2. **Summarizes** long text by extracting the most important sentences using word-frequency scoring

The core idea: if users receive a warning before sending an offensive message, there is a high probability they may reconsider — directly helping reduce cyberbullying incidents.

---

## ✨ Features

| Feature | Description |
|---|---|
| 🔍 Cyberbullying Detector | Classifies text as Hate Speech / Offensive Language / No Offense |
| 📝 Text Summarizer | Extracts top 30% sentences by word-frequency importance score |
| 🧹 Text Preprocessing | Cleans URLs, punctuation, digits, and stopwords |
| 🖥️ CLI Interface | Simple numbered choice menu for both features |

---

## 📂 Dataset

- **Source:** Twitter data (publicly available)
- **Size:** ~24,000 labeled tweets
- **Classes:**
  - `0` → Hate Speech Detected
  - `1` → Offensive Language Detected
  - `2` → No Hate / Offensive Speech

---

## 🔄 Project Workflow

**Cyberbullying Detection:**
1. Load and label Twitter CSV data
2. Clean tweets — lowercase, remove URLs, punctuation, digits, stopwords
3. Feature extraction using **CountVectorizer**
4. Train/test split (67% / 33%)
5. Train **Decision Tree Classifier**
6. Predict sentiment/offensiveness on user input

**Text Summarization:**
1. Tokenize input text using SpaCy (`en_core_web_sm`)
2. Build word frequency dictionary (excluding stopwords and punctuation)
3. Normalize word frequencies by maximum frequency
4. Score each sentence by summing frequencies of its words
5. Extract top 30% highest-scoring sentences as the summary

---

## 📊 Model & Results

| Component | Detail |
|---|---|
| Model | Decision Tree Classifier |
| Vectorizer | Count Vectorizer |
| Train/Test Split | 67% / 33% |
| Training Data | ~16,000 tweets |
| Accuracy | **89%** |
| NLP Library | SpaCy (`en_core_web_sm`) |

---

## 🛠️ Tech Stack

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![SpaCy](https://img.shields.io/badge/SpaCy-09A3D5?style=flat&logo=spacy&logoColor=white)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-F7931E?style=flat&logo=scikit-learn&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=flat&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=flat&logo=numpy&logoColor=white)

**Key Libraries:**
- `spacy` — NLP tokenization, stopword handling, sentence segmentation
- `sklearn` — CountVectorizer, DecisionTreeClassifier, train_test_split
- `pandas` / `numpy` — data handling
- `heapq` — extracting top N sentences for summarization
- `re` — regex-based text cleaning

---

## ▶️ How to Run

### 1. Clone the repository
```bash
git clone https://github.com/pawanahirwa/Cyberbullying-Recognizer-and-Summarizer.git
cd Cyberbullying-Recognizer-and-Summarizer
```

### 2. Install dependencies
```bash
pip install -r requirements.txt
python -m spacy download en_core_web_sm
```

### 3. Run the application
```bash
python app.py
```

### 4. Use the menu
```
1 → Enter text to get a summary
2 → Enter text to check if it's offensive / hate speech
```

---

## 📁 Project Structure

```
Cyberbullying-Recognizer-and-Summarizer/
│
├── app.py                # Main application — model training, prediction & summarization
├── definations.py        # Helper functions — clean(), word_freq_counter(), sentence_score()
├── twitter_data.csv      # Labelled Twitter dataset (hate speech / offensive / clean)
├── requirements.txt      # Python dependencies
└── README.md
```

---

## 📸 Screenshots

### Choice Menu
![Choice Menu](https://user-images.githubusercontent.com/86300718/218245622-348575cb-9036-4121-ab08-791d465a74e9.png)

### Text Summarizer
![Summarizer](https://user-images.githubusercontent.com/86300718/218245629-14ebf7b1-cc55-4a63-9ce3-b342ddd5b2c3.png)

### Offensive Meter & Analyzer
![Analyzer](https://user-images.githubusercontent.com/86300718/218245638-3e0484f5-a409-45b7-ae76-5fe5664dc557.png)

---

## 👤 Author

**Pawan Singh Ahirwar**
- GitHub: [@pawanahirwa](https://github.com/pawanahirwa)
- Affiliation: IRCC, IIT Bombay
