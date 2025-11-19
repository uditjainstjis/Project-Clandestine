# Analysis Summary: Why a Fundamentally Weaker Baseline Model Showed Comparable F1 Performance

## 1. Overview

During experimentation with the LIAR dataset, an unexpected pattern emerged: A simplified baseline model—despite lacking essential preprocessing steps and being theoretically inferior—produced an F1 score similar to, or slightly better than, a more advanced pipeline. This document explains why this happens and the underlying mechanisms that lead to misleading performance metrics.

## 2. Key Observation

The weaker baseline model:
- Removed stopwords
- Used only unigram TF-IDF
- Included no lemmatization, bigrams, or trigrams
- Utilized no class balancing
- Used a small vocabulary and raw text

Despite this, it achieved an overall F1 score around 0.58–0.61, which is comparable to the more robust model. However, its classification behavior was significantly worse, particularly in recall for the "Fake" class.

## 3. Root Cause: Dataset Imbalance and Overlapping Language

The LIAR dataset is:
- Class-imbalanced (Real > Fake)
- Highly stylistically homogeneous, regardless of truthfulness
- Filled with politically structured text where "true" and "false" statements often look linguistically similar

This allows simplistic models to exploit statistical biases in the data rather than learning meaningful distinctions.

## 4. Bias Toward Predicting the Majority Class

The simplified baseline systematically defaulted to predicting Real (the majority class). This caused:

**Real Class (Positive)**
- High recall
- High precision
- Inflated F1

**Fake Class (Negative)**
- Very low recall
- Weak ability to detect false statements

Despite poor performance on Fake claims, the high Real-class performance compensated numerically, making the macro F1 appear acceptable.

## 5. Why F1 Score Can Be Misleading

The F1 metric:
- Balances precision and recall, but does not penalize majority-class bias
- Does not reflect semantic understanding of text
- Can be inflated by simply choosing the majority class whenever uncertain
- Does not expose asymmetric class performance unless examined per label

Thus, a model that performs poorly in real-world detection can still achieve a deceptively acceptable F1 score.

## 6. Comparison to the Stronger Model

The better-engineered pipeline used:
- Lemmatization
- TF-IDF with n-grams (1–3)
- Balanced class weights
- Stopwords preserved
- Regularization tuning

This model:
- Showed balanced recall across both classes
- Exhibited higher discriminatory ability
- Reflected genuine text pattern understanding

Even if its numerical F1 score was similar, its behavior was fundamentally superior.

## 7. Key Takeaway

**A higher or comparable F1 score does not guarantee a better model.**

The improved preprocessing pipeline produces a model that:
- Generalizes better
- Detects Fake claims more reliably
- Minimizes dataset biases
- Demonstrates meaningful linguistic learning

while the baseline achieves its F1 through bias exploitation rather than genuine understanding.

## 8. Conclusion

The unexpected performance of the simplified baseline is a direct result of:
- Dataset imbalance
- Semantic overlap between true and false statements
- Metric sensitivity
- Lack of interpretability in superficial token patterns

**Effective evaluation requires not just metrics, but analysis of model behavior, confusion matrices, recall balance, and real-world applicability.**
