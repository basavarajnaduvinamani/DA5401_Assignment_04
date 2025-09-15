# Fraud Detection with GMM-based Synthetic Data  
**Author:** Basavaraj A Naduvinamani (DA25C005)

## Overview
This project investigates the effectiveness of **Gaussian Mixture Model (GMM) synthetic oversampling** and **Clustering-Based Undersampling (CBU)** for handling extreme class imbalance in fraud detection datasets.

## Models Compared
1. **Baseline:** Logistic Regression on original imbalanced data  
2. **GMM-only:** Logistic Regression with GMM-synthetic minority samples  
3. **GMM + CBU:** Logistic Regression with GMM oversampling + CBU undersampling  

## Performance Summary
| Metric     | Baseline | GMM-only | GMM + CBU |
|-----------|----------|----------|------------|
| Precision | 0.8505   | 0.0815   | 0.0710     |
| Recall    | 0.6149   | 0.8581   | 0.8716     |
| F1-score  | 0.7137   | 0.1489   | 0.1314     |

- **Baseline:** High precision, low recall → misses fraud cases.  
- **GMM-only:** High recall, very low precision → many false positives.  
- **GMM + CBU:** Highest recall, lowest precision → best for detecting nearly all fraud cases.  

## Key Insights
- **Recall improves from 61% → 87%** with GMM + CBU.  
- Precision drops, but this is acceptable in fraud detection where **false negatives are costlier than false positives**.  
- GMM + CBU balances the dataset, preventing overfitting on synthetic data.  

## Recommendation
- **For small datasets:** Use **GMM + CBU** to maximize minority detection.  
- **For large-scale fraud detection:** Use **GMM + CBU** with probability threshold tuning and business rule filters to manage false positives.  

## Conclusion
**GMM + CBU** is the most effective strategy for extreme class imbalance in fraud detection.  
It yields the highest recall, ensuring fraud cases are detected, while false positives can be mitigated with post-processing.
