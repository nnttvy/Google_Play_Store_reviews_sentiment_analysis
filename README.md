
# Sentiment Analysis on Google Play Store Reviews

## Introduction
This project scrapes real user reviews, performs exploratory data analysis (EDA), preprocesses the text, and trains multiple sentiment classification models including lexicon-based methods (TextBlob, VADER, SentiWordNet), machine learning and deep learning approaches (Random Forest, SVM, RNN-LSTM and BERT).



## Features
**Data Scaping:**

Scraped reviews from Google Play Store using google_play_scraper library. 

**EDA & Preprocessing:**

+ Missing data clear
+ Text normalization (lowercasing, punctuation removal, stopword removal)
+ Tokenization & lemmatization
+ Wordclouds, frequency plots, sentiment distributions

**Sentiment Labeling**

Using Python lexicon_based libraries to determine whether the review is positive, negative or neutral. Libraries used: TextBlob, VADER, SentiWordNet


The final sentiment selected based on the highest agreement among the three results; if all three are different, the result from VADER will be chosen.

**Machine learning & Deep Learning Models Training**
+ Random Forest
+ SVM
+ RNN-LSTM
+ BERT

**Visualizations**
All the figures generated during EDA and evaluation steps are available in 
the `Figures` folder, 

**Evaluation**
+ Accuracy
+ Macro avg precison
+ Macro avg recall
+ Macro avg F1 score
+ Confusion matrix


## Dataset

This project provides 4 csv files (all available in data folder):
| File              | Description                            |
| ----------------- | -------------------------------------- |
| `all_reviews.csv` | Full scraped dataset with all features |
| `train.csv`       | Training subset (text only)            |
| `test.csv`        | Test subset (text only)                |
| `valid.csv`       | Validation subset (text only)          |

These files allow reproducible training and evaluation without needing to rescrape data.

The dataset has 2400 rows, 12 columns. This is data from 12 popular, highly-rated video game apps from the Google Play rankings at the time the data was collected.

#### *Note: README under development. More details coming soon.*