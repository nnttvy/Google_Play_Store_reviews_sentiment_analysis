# 🎮 Google Play Store Reviews — Sentiment Analysis

> An end-to-end **Natural Language Processing (NLP)** project for analyzing sentiment in Google Play Store game reviews using lexicon-based methods, traditional machine learning, recurrent neural networks, and BERT.

## 📌 Overview

User reviews contain valuable information about how players perceive and experience a game. This project analyzes real-world reviews from popular Google Play Store games and applies **sentiment analysis** to classify reviews as **positive, neutral, or negative**.

The project covers the complete NLP pipeline:

**Data Collection → Exploratory Data Analysis → Text Preprocessing → Sentiment Labeling → Machine Learning → Deep Learning → Model Evaluation**

The dataset contains **2,400 reviews across 12 popular, highly-rated video game applications** collected from Google Play Store rankings at the time of data collection.

---

## 🎯 Objectives

The main objectives of this project are to:

* Collect real-world user reviews from Google Play Store.
* Explore the characteristics and distribution of game reviews.
* Clean and preprocess natural language text.
* Generate sentiment labels using multiple lexicon-based approaches.
* Compare traditional machine learning and deep learning approaches.
* Evaluate sentiment classification performance using multiple metrics.
* Visualize sentiment patterns and model performance.
---

## 📁 Repository Structure

```text
Google_Play_Store_reviews_sentiment_analysis/
│
├── Data/
│   ├── all_reviews.csv
│   ├── train.csv
│   ├── test.csv
│   └── valid.csv
│
├── Figures/
│   └── EDA & model evaluation visualizations
│
├── Source_code/
│   └── Project source code
│
├── .gitattributes
│
└── README.md
```

The repository is organized into separate directories for **data, generated figures, and source code**, making the project easier to navigate and reproduce.

---

## 📊 Dataset

The repository contains 4 CSV files:

| File              | Description                                                |
| ----------------- | ---------------------------------------------------------- |
| `all_reviews.csv` | Complete scraped dataset containing all available features |
| `train.csv`       | Training dataset containing review text                    |
| `test.csv`        | Test dataset containing review text                        |
| `valid.csv`       | Validation dataset containing review text                  |

The repository includes the processed datasets so that the analysis and model training can be reproduced without having to scrape the Google Play Store again.

### Dataset Summary

* **2,400 reviews**
* **12 columns** in the complete dataset
* Reviews collected from **12 popular video game applications**
* Source: Google Play Store

---


## 🔄 Project Workflow

```text
Google Play Store
       │
       ▼
  Review Scraping
       │
       ▼
Data Cleaning & EDA
       │
       ▼
 Text Preprocessing
       │
       ├── Lowercasing
       ├── Punctuation Removal
       ├── Stopword Removal
       ├── Tokenization
       └── Lemmatization
       │
       ▼
 Sentiment Labeling
       │
       ├── TextBlob
       ├── VADER
       └── SentiWordNet
       │
       ▼
 Final Sentiment Labels
       │
       ├───────────────┬───────────────┐
       ▼               ▼               ▼
 Traditional ML    Deep Learning      BERT
       │               │               │
   ┌───┴───┐           │               │
   │       │         LSTM              │
   ▼       ▼                           │
 Random   SVM                          │
 Forest                                │
   │       │           │               │
   └───────┴───────────┴───────────────┘
                     │
                     ▼
              Model Evaluation
```

## 🕷️ 1. Data Collection

Reviews were collected from Google Play Store using the Python [`google-play-scraper`](https://pypi.org/project/google-play-scraper/) library.

The scraped data contains information associated with each review, which is subsequently prepared for exploratory analysis and NLP modeling.

---

## 🔎 2. Exploratory Data Analysis

The project performs exploratory analysis to understand the structure and characteristics of the collected reviews.

The analysis includes:

* Missing-value inspection
* Review and sentiment distributions
* Word-frequency analysis
* Word clouds
* Review characteristics
* Visualization of sentiment patterns

All generated visualizations are stored in the [`Figures`](Figures/) directory.

---

## 🧹 3. Text Preprocessing

Natural language preprocessing is performed to transform raw user reviews into a format suitable for sentiment analysis.

The preprocessing pipeline includes:

* Lowercasing
* Punctuation removal
* Stopword removal
* Tokenization
* Lemmatization

These steps reduce noise and normalize the text before it is passed to sentiment-analysis and machine-learning models.

---

## 🏷️ 4. Sentiment Labeling

Three lexicon-based sentiment-analysis approaches are used to generate sentiment labels:

* **TextBlob**
* **VADER**
* **SentiWordNet**

Each method independently evaluates the sentiment of a review.

### Label Selection Strategy

The final sentiment label is determined using an agreement-based approach:

1. If the three methods agree, their common sentiment is selected.
2. If there is no complete agreement, the result from the majority agreement is used.
3. If all three methods produce different results, **VADER** is selected as the final label.

The resulting labels are:

* 🟢 **Positive**
* 🟡 **Neutral**
* 🔴 **Negative**

This labeling strategy provides the target variable used in the subsequent classification experiments.

---

# 🤖 5. Sentiment Classification Models

The project compares several approaches to sentiment classification.

## Random Forest

A **Random Forest** classifier is used as a traditional machine-learning approach for sentiment classification.

Random Forest provides a useful baseline for evaluating how well conventional ensemble learning can handle the processed review data.

## Support Vector Machine

A **Support Vector Machine (SVM)** classifier is also trained for sentiment classification.

SVM is particularly useful for text-classification tasks because high-dimensional representations of text can often be effectively separated using hyperplane-based classification.

## RNN-LSTM

A **Recurrent Neural Network with Long Short-Term Memory (RNN-LSTM)** is used to model sequential relationships within review text.

LSTM networks are designed to capture dependencies between words across a sequence, making them suitable for natural-language tasks.

## BERT

The project also applies **BERT (Bidirectional Encoder Representations from Transformers)** for sentiment classification.

Unlike traditional bag-of-words approaches, BERT uses contextual representations to capture the meaning of words based on their surrounding text.

The inclusion of BERT allows the project to compare a transformer-based NLP approach against traditional machine learning and recurrent neural-network methods.

---

# 📏 6. Model Evaluation

The classification models are evaluated using multiple metrics:

* **Accuracy**
* **Macro-average Precision**
* **Macro-average Recall**
* **Macro-average F1-score**
* **Confusion Matrix**

Using macro-averaged metrics provides a more informative view of performance across the different sentiment classes, particularly when class distributions are not perfectly balanced.

---

## 📈 Results & Visualizations

Model evaluation results and exploratory-analysis figures are available in the [`Figures`](Figures/) directory.

The visualizations include:

* Sentiment distributions
* Word-frequency visualizations
* Word clouds
* Model evaluation plots
* Confusion matrices

> **Note:** Model performance values are intentionally not hard-coded into this README. This keeps the documentation synchronized with the latest experiment outputs in the repository.

---

## 🛠️ Technologies & Libraries

### Programming Language

* **Python**

### Data Collection

* `google-play-scraper`

### Data Processing & Analysis

* `pandas`
* `numpy`

### Natural Language Processing

* `NLTK`
* `TextBlob`
* `VADER`
* `SentiWordNet`

### Machine Learning

* `scikit-learn`

  * Random Forest
  * Support Vector Machine

### Deep Learning

* RNN
* LSTM
* BERT

### Visualization

* `Matplotlib`
* `Seaborn`
* WordCloud

---

## 🚀 Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/nnttvy/Google_Play_Store_reviews_sentiment_analysis.git
```

```bash
cd Google_Play_Store_reviews_sentiment_analysis
```

### 2. Install Dependencies

Install the required Python libraries according to the project's source code and environment.

For the core analysis components, for example:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn nltk textblob wordcloud google-play-scraper
```

Deep-learning experiments involving LSTM and BERT additionally require the appropriate deep-learning framework and transformer libraries.

### 3. Run the Project

Navigate to the `Source_code` directory and run the analysis scripts/notebooks according to the project workflow.

The provided CSV files allow you to reproduce the modeling workflow without performing the original review-scraping step.

---

## 💡 What This Project Demonstrates

This project demonstrates practical experience with an end-to-end NLP workflow, including:

* **Web data collection**
* **Data cleaning**
* **Exploratory data analysis**
* **Natural language preprocessing**
* **Lexicon-based sentiment analysis**
* **Feature preparation for NLP**
* **Traditional machine learning**
* **Deep learning**
* **Transformer-based NLP**
* **Model evaluation**
* **Data visualization**

More importantly, the project compares different generations of NLP approaches—from lexicon-based sentiment scoring and classical machine learning to **LSTM and BERT**.

---

## ⚠️ Limitations

Several considerations should be kept in mind when interpreting the results:

* The dataset contains reviews from only **12 game applications**.
* The dataset contains **2,400 reviews**, so conclusions may not generalize to all Google Play Store games.
* Sentiment labels are generated using lexicon-based methods rather than manually annotated ground-truth labels.
* Lexicon-based labeling can introduce noise and disagreement between labeling methods.
* User reviews may contain slang, abbreviations, sarcasm, emojis, and game-specific terminology that are difficult for general-purpose sentiment models to interpret.
* Model performance should therefore be interpreted within the context of this dataset and labeling methodology.

---

## 📚 Project Context

This repository was developed as a practical **NLP and sentiment-analysis project**, focusing on applying data science techniques to real-world user-generated text.

The project combines data collection, exploratory analysis, natural language processing, machine learning, and deep learning into a single workflow.

---

## 📌 Topics

`Python` · `NLP` · `Sentiment Analysis` · `Machine Learning` · `Deep Learning` · `BERT` · `LSTM` · `SVM` · `Random Forest` · `Google Play Store` · `Text Classification`

---

⭐ If you find this project useful, feel free to explore the source code and experiment with the models.
