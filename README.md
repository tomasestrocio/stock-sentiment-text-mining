# Stock Sentiment from Tweets (NLP / Text Mining)

This repository contains a **Text Mining / NLP project** developed at **NOVA IMS (Master in Data Science and Advanced Analytics)** for **stock sentiment classification** using tweets.

The goal is to classify stock-related tweets into **three sentiment classes**:

- **0 = Bearish**
- **1 = Neutral**
- **2 = Bullish**

The project compares **7 different NLP pipelines**, from classical text mining methods to deep learning and transformer-based models.

---

## Project Summary

This project explores how different preprocessing strategies, feature representations, and model families affect sentiment classification performance in financial text.

### Pipelines tested
1. **BoW + KNN**
2. **TF-IDF + Gaussian Naive Bayes**
3. **TF-IDF + Logistic Regression**
4. **T5 embeddings + Logistic Regression**
5. **Word2Vec + Bi-LSTM**
6. **DistilBERT (fine-tuned)**
7. **RoBERTa (fine-tuned)** ✅ best performer

---

## Dataset

- **Training set size:** ~9,543 tweets
- **Classes:** bearish, neutral, bullish
- The class distribution is **moderately imbalanced** (bullish is the largest class).

Tweets are short and include:
- stock tickers
- finance jargon
- URLs
- occasional emojis/emoticons

---

## Workflow

### 1) Data Exploration
- Label distribution
- Tweet length distribution
- Frequent words
- Word clouds
- Emoji/emoticon inspection

### 2) Preprocessing Experiments
Tested combinations of:
- lowercasing
- URL removal
- emoji/emoticon handling (remove vs convert to tokens)
- punctuation removal
- tokenization
- stopword removal
- lemmatization
- stemming (tested but excluded from final pipeline due to poorer performance)

### 3) Feature Engineering
- **Bag-of-Words (BoW)**
- **TF-IDF**
- **Word2Vec**
- **T5 contextual embeddings**
- Transformer tokenization (DistilBERT / RoBERTa)

### 4) Modeling and Evaluation
Models were compared using:
- Accuracy
- Macro F1
- Precision
- Recall

---

## Best Results

**Best model: RoBERTa**

### Validation performance (RoBERTa)
- **Accuracy:** 0.897
- **Macro F1:** 0.872
- **Precision:** 0.862
- **Recall:** 0.883

RoBERTa achieved the best overall performance, showing stronger ability to capture contextual and nuanced sentiment in financial tweets compared to classical baselines.

---

## Repository Contents

- `notebooks/tm_tests_09.ipynb` — full experimentation notebook (EDA, preprocessing, multiple models, comparisons)
- `notebooks/tm_final_09.ipynb` — final notebook focused on the best model (RoBERTa)
- `data/train.csv` — training dataset
- `data/test.csv` — test dataset
- `report/report_09.pdf` — project report with methodology and results summary

---

## How to Run

### 1. Clone the repository
```bash
git clone https://github.com/YOUR_USERNAME/stock-sentiment-text-mining.git
cd stock-sentiment-text-mining
