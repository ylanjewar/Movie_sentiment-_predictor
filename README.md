# IMDB Movie Review Sentiment Analysis

## Overview

This project uses machine learning to classify movie reviews from the IMDB dataset as either **positive** or **negative**. The primary goal is to help businesses (like streaming platforms, production studios, and e-commerce platforms) **automatically detect public sentiment**, enabling faster response to customer feedback, smarter product decisions, and better user engagement.

---

## Business Objective

Businesses often deal with large volumes of user-generated content, such as reviews, feedback forms, or support tickets. Reading these manually is time-consuming. This project demonstrates how sentiment analysis using machine learning can:

- Detect trends in audience sentiment automatically
- Help identify top-performing or underperforming content
- Enable marketing teams to adjust messaging based on user reactions
- Support product teams in prioritizing improvements

This isn't just a technical challenge — it's a practical business use case that transforms unstructured data into actionable insights.

---

## Dataset

**Source**: IMDB Movie Review Dataset  
**File Used**: `imdb.csv`  
**Target Variable**: `sentiment` (either `positive` or `negative`)

---

## Feature Engineering

- **Text Vectorization**: TF-IDF (Term Frequency-Inverse Document Frequency)
- **N-grams**: Used unigrams and bigrams (e.g., “not good”) to capture better context
- **Feature Limiting**: Top 20,000 most important words/phrases retained

---

## Models Compared

| Model                | Technique Type     | Hyperparameter Tuning |
|----------------------|--------------------|------------------------|
| Logistic Regression  | Linear Classifier  |  GridSearchCV         |
| SGDClassifier (SVM)  | Linear SVM Approx. |  Manually Tuned       |
| Random Forest        | Ensemble           |  Tuned with depth     |

---

## Evaluation Metrics

Each model was evaluated using:
- **Accuracy**
- **Precision**
- **Recall**
- **F1 Score**
- **Confusion Matrix**

---

## Results Summary

| Model                | Accuracy | Precision | Recall | F1 Score |
|----------------------|----------|-----------|--------|----------|
| Logistic Regression  | 90.1%    | 91%       | 91%    | 91%      |
| SGDClassifier (SVM)  | 90.2%    | 91%       | 90%    | 90%      |
| Random Forest        | 86.4%    | 84%       | 88%    | 87%      |

---

## Real-World Inference Examples

To test model generalization on unseen data, we passed new reviews through all three models. Here's what we found:

###  Clear Positive Review
> **“Echoing its predecessor while upping the bloodsport and camp, Gladiator II is an action extravaganza that derives much of its strength and honor from Denzel Washington's scene-stealing performance.”**

- All models predicted **Positive** — as expected.

### Nuanced Language
> **“Delighting in razzle-dazzle over historical precision, Gladiator II rigorously entertains all the better for it.”**

- Logistic Regression: **Negative**  
- SGDClassifier: **Negative**  
- **Random Forest**:  **Positive** (the only model to correctly catch the subtle praise)

###  Analytical but Favorable
> **“Watching Gladiator II, it is hard not to be a little suspicious about exactly what we are longing for in our Roman fantasies.”**

- All models predicted **Positive**, likely detecting thoughtful but favorable sentiment.

### Interpretation

Even though Random Forest had lower accuracy overall, it correctly classified a more nuanced, positive review — showing how **accuracy doesn’t always capture a model’s ability to interpret complex phrasing**. That’s why combining model types can be useful depending on the domain and user language complexity.

---

## Final Takeaways for Stakeholders

- **Speed**: The SGDClassifier offers fast, scalable predictions suitable for real-time apps.
- **Interpretability**: Logistic Regression is easier to interpret but may miss nuance.
- **Flexibility**: Random Forest handles subtle sentiment better but can overfit.

These models can be deployed in content moderation systems, customer feedback monitoring dashboards, or even integrated into chatbot assistants to understand user emotion in real time.

---

## How to Run the Code

1. Clone this repository
2. Place `imdb.csv` in a folder called `data/`
3. Run the notebook or script top to bottom
4. Modify the `new_reviews` list at the end to try your own samples

---

## Author

This capstone project was developed by Yogesh as part of a machine learning coursework, showcasing practical use of classification models for real-world sentiment analysis.

