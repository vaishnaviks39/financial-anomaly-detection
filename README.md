# Transaction Anomaly Detection using Machine Learning

## Project Overview

This project focuses on identifying anomalous financial transactions using machine learning techniques. Since fraudulent or abnormal transactions are rare and often lack reliable labels, the problem is addressed using anomaly detection rather than traditional supervised classification.

The project compares two primary anomaly detection models, Isolation Forest and Autoencoder, to determine which approach performs better on transaction data.

---

## Dataset Description

The dataset contains transaction level numeric features such as transaction amount, average transaction amount, and transaction frequency.  
A proxy anomaly label is generated using statistical methods and is used strictly for evaluation purposes.

---

## Models Implemented

Isolation Forest  
An unsupervised anomaly detection algorithm that isolates abnormal observations using random feature partitioning. It is efficient, scalable, and well suited for tabular financial data.

Autoencoder  
A neural network trained to reconstruct normal transaction behavior. Transactions with high reconstruction error are identified as anomalies, allowing the model to capture nonlinear relationships.

Random Forest  
A supervised baseline model used to analyze feature importance and provide interpretability rather than primary anomaly detection.

---

## Evaluation Methodology

Model performance is evaluated using ROC AUC and Precision Recall analysis.  
Continuous anomaly scores are used instead of binary predictions to ensure correct ranking based evaluation.

Isolation Forest is evaluated using its decision function scores.  
The Autoencoder is evaluated using reconstruction error computed on unseen test data.

---

## Results and Model Comparison

Isolation Forest  
ROC AUC: 1.00  

Autoencoder  
ROC AUC: 0.99  

Isolation Forest achieved perfect separation between normal and anomalous transactions on the test set, while the Autoencoder also demonstrated strong performance by capturing nonlinear transaction patterns.

---

## Classification Performance

At a fixed anomaly threshold, Isolation Forest predictions achieved perfect precision, recall, and F1 score for both normal and anomalous classes on the test set. This indicates accurate identification of anomalous transactions without false positives or false negatives in this dataset.

---

## Key Observations

Isolation Forest provides excellent performance with minimal tuning and high scalability.  
The Autoencoder performs competitively but requires careful preprocessing and architectural choices.  
Given similar performance, Isolation Forest is preferred due to its simplicity and efficiency.

---

## Technologies Used

Python  
Pandas and NumPy  
Scikit learn  
TensorFlow Keras  
Matplotlib and Plotly  

---

## Conclusion

This project demonstrates how anomaly detection techniques such as Isolation Forest and Autoencoders can be applied to financial transaction data where labeled fraud examples are limited. Based on ROC AUC and classification performance, Isolation Forest was selected as the most effective and practical model for this dataset.
