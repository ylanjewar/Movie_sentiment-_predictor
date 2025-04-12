# IMDB Movie Review Sentiment Classification

## Project Overview

This project analyzes a dataset of IMDB movie reviews to predict the **sentiment** (positive or negative) expressed in each review. The dataset contains 50,000 movie reviews labeled for binary sentiment classification.

The primary objective is to apply natural language processing (NLP) techniques and machine learning models to build a predictive system capable of classifying unseen movie reviews based on their textual content.

---

## Business Objective

To automate sentiment classification of user-generated movie reviews for applications such as:

- Improving content recommendation systems
- Summarizing public opinion on films
- Enhancing moderation and feedback analytics on review platforms

A well-performing model can help platforms understand viewer reactions at scale and respond with better personalization or content strategy.

---

## Dataset

**Source**: IMDB Large Movie Review Dataset  
**File Used**: `imdb.csv`  
**Target Variable**: `sentiment` — either `positive` or `negative`

**Text Feature**:  
- `review`: Full text of each movie review

**Label**:  
- `sentiment`: Manually labeled as `positive` or `negative`

---

## Workflow Summary

### Data Preparation
- Removed punctuation and special characters
- Lowercased all review text
- Converted sentiment labels to binary format (1 = positive, 0 = negative)
- Visualized class balance and review length distribution

### Feature Engineering
- Applied TF-IDF vectorization (with bigrams) to transform text into numerical features
- Selected top 20,000 features by term frequency

### Modeling
- Trained two classification models:
  - Logistic Regression (`C=0.5`)
  - Support Vector Machine (SVM) with linear kernel (`C=0.5`)
- Saved both models and vectorizer for future inference

### Evaluation Metrics
- Accuracy
- Precision
- Recall
- F1 Score
- Confusion Matrix
- Classification Report

### Visualizations Included
- Sentiment distribution plot
- Histogram of review lengths
- Bar plot of top TF-IDF features
- Confusion matrix heatmaps for both models

---

## Key Findings

- The dataset was balanced, with a 50-50 split between positive and negative reviews.
- Logistic Regression achieved slightly better performance than SVM in accuracy, recall, and F1-score.
- TF-IDF with bigram features significantly improved model performance over unigrams alone.
- Simple linear models performed well, achieving close to 89% accuracy on the test set.
