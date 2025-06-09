# Fake News Detection System

A state-of-the-art machine learning system for detecting fake news articles using natural language processing and ensemble learning techniques. The system features a Flask REST API backend and a React frontend for real-time predictions.

## Project Overview

This project implements an advanced fake news detection system that achieves **96.8% accuracy** using an ensemble of machine learning models. The system analyzes news articles based on textual content, linguistic patterns, and structural features to determine authenticity.

### Key Features

- **High Accuracy**: 96.8% accuracy with 0.995 AUC-ROC score
- **Real-time Predictions**: Instant analysis through web interface
- **Ensemble Learning**: Combines Logistic Regression, Random Forest, and XGBoost
- **Comprehensive Feature Engineering**: Text analysis, sentiment analysis, and linguistic patterns
- **RESTful API**: Flask backend for scalable deployment
- **Modern Frontend**: React-based user interface
- **Robust Validation**: Cross-validated with 63,121+ samples

## Model Performance

| Metric | Score |
|--------|-------|
| **Accuracy** | 96.82% |
| **Precision** | 96.05% |
| **Recall** | 96.89% |
| **F1-Score** | 96.47% |
| **AUC-ROC** | 0.9953 |

### Dataset Statistics
- **Total Samples**: 63,121
- **Training Set**: 50,496 (80%)
- **Test Set**: 12,625 (20%)
- **Features**: 8,010 (8,000 TF-IDF + 10 numerical)




### Data Preprocessing
- Text cleaning and normalization
- Special character handling
- URL and number tokenization
- Stop word removal

### Feature Engineering
- **TF-IDF Vectorization**: 8,000 features with 1-2 n-grams
- **Numerical Features**: 10 engineered features including:
  - Text length and word count
  - Punctuation patterns
  - Sentiment analysis (VADER)
  - Fake news keywords detection
  - Capitalization ratio

### Model Architecture
- **Ensemble Method**: Voting Classifier
- **Base Models**:
  - Logistic Regression (C=1.0, balanced class weights)
  - Random Forest (100 estimators, max_depth=15)
  - XGBoost (100 estimators, max_depth=6)

### Model Validation
- 3-fold cross-validation
- Stratified train-test split
- Comprehensive performance evaluation on holdout set

### Fake News Indicators
The model identifies several key patterns characteristic of fake news:

- **Sensational Language**: Excessive punctuation and capitalization
- **Emotional Manipulation**: Strong positive or negative sentiment scores
- **Clickbait Keywords**: Terms like "BREAKING", "SHOCKING", "EXPOSED"
- **Structural Anomalies**: Unusual text length and formatting patterns
- **Linguistic Patterns**: Frequency of questions and exclamations

### Preprocessing Pipeline
- Text normalization to lowercase
- Special character and URL handling
- Tokenization with stop word removal
- Linguistic feature extraction
- Numerical feature normalization

## Model Interpretability

The system provides detailed confidence metrics:

- **High Confidence (>0.8)**: Very reliable prediction
- **Medium Confidence (0.6-0.8)**: Reliable prediction with good certainty
- **Low Confidence (<0.6)**: Uncertain prediction requiring manual review

## Performance Analysis

### Confusion Matrix Results
```
                 Predicted
Actual     Fake      Real
Fake      6733      226
Real       176     5490
```

### Cross-Validation Results
- **Accuracy**: 96.53% ± 0.19%
- **AUC-ROC**: 99.45% ± 0.05%
- **F1-Score**: 96.16% ± 0.21%

## License

This project is licensed under the MIT License.
