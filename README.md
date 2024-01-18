# CS412 Group Project: Estimating Grades Based on ChatGPT History

## Introduction
This repository contains the work of our CS412 project focused on estimating student grades using their ChatGPT conversation history. Our approach analyzes various textual features and employs machine learning techniques to predict grades.

## Data Preprocessing

### Grade Interval Analysis
- We focused on the main grade intervals: (70,80], (80,90], and (90,100].
- Records with grades outside these intervals were dropped to maintain consistency and avoid anomalies in our modeling.

### Prompt and Question Matching
- Each prompt from the preprocessed dataset was matched with predefined questions.
- We used the TF-IDF vectorizer to transform both prompts and questions into vector space for similarity comparison.
- Based on these comparisons, we incremented the `Qi` count for each user, indicating the frequency of prompts related to each question.

## Model Implementation

### Decision Tree Regressor
- We implemented a Decision Tree Regressor to predict grades.
- Hyperparameters were optimized using GridSearchCV.

### Model Performance
- The model yielded the following results:
  - Test Mean Squared Error: 54.85537291322563
  - Training Mean Squared Error: 10.098111263736264
- These results show a significant improvement, halving the MSE from the initial codebase.

## Challenges and Limitations
Despite our efforts to minimize the MSE, certain challenges limited the accuracy of our predictions:
- Some HTML files contained a low number of prompts or questions that were not highly relevant.
- The similarity in prompts across different users posed a challenge in making precise predictions.
- The inherent complexity of the problem, coupled with the limitations of our dataset, impacted our model's performance.

## Conclusion
This project demonstrates the potential and challenges of using ChatGPT history as a predictor for academic performance. Future work could explore more sophisticated models or larger, more diverse datasets to enhance prediction accuracy.
