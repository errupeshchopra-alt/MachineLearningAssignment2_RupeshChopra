# MachineLearningAssignment2_RupeshChopra
Implement multiple classification models: 1. Logistic Regression 2. Decision Tree Classifier 3. K-Nearest Neighbor Classifier 4. Naive Bayes Classifier - Gaussian or Multinomial 5. Ensemble Model - Random Forest 6. Ensemble Model - XGBoost

- UCI Machine Learning Repository:  
https://archive.ics.uci.edu/ml/datasets/Breast+Cancer+Wisconsin+%28Diagnostic%29

---

### Attribute Information

1. **ID Number**
2. **Diagnosis**  
 - `M` = Malignant  
 - `B` = Benign
3. **Attributes 3–32**: Computed features

#### Ten Real-Valued Features (per nucleus)

- **Radius** – Mean distance from center to perimeter points  
- **Texture** – Standard deviation of gray-scale values  
- **Perimeter**
- **Area**
- **Smoothness** – Local variation in radius lengths  
- **Compactness** – (Perimeter² / Area) − 1.0  
- **Concavity** – Severity of concave portions of the contour  
- **Concave Points** – Number of concave portions  
- **Symmetry**
- **Fractal Dimension** – "Coastline approximation" − 1

For each feature, the following were computed:
- **Mean**
- **Standard Error**
- **Worst (Largest Mean of Three Values)**

This results in **30 total features** per image.  
Example:
- Field 3 → Mean Radius  
- Field 13 → Radius Standard Error  
- Field 23 → Worst Radius  

---

## c) Models Used

- Logistic Regression.ipynb  
- Decision Tree Classifier.ipynb  
- K-Nearest Neighbor Classifier.ipynb  
- Naive Bayes Classifier – Gaussian.ipynb  
- Ensemble Model – Random Forest.ipynb  
- Ensemble Model – XGBoost.ipynb  

---

## d) Model Comparison Table

| ML Model Name | Accuracy | AUC | Precision | Recall | F1 Score | MCC |
|--------------|----------|-----|-----------|--------|----------|-----|
| Logistic Regression | 0.9737 | 0.9954 | 0.9756 | 0.9524 | 0.9639 | 0.9433 |
| Decision Tree | 0.9035 | 0.8889 | 0.8974 | 0.8333 | 0.8642 | 0.7908 |
| K-Nearest Neighbor | 0.9561 | 0.9825 | 0.9744 | 0.9048 | 0.9383 | 0.9058 |
| Naive Bayes (Gaussian) | 0.9211 | 0.9891 | 0.9231 | 0.8571 | 0.8889 | 0.8292 |
| Random Forest | 0.9649 | 0.9970 | 1.0000 | 0.9048 | 0.9500 | 0.9258 |
| XGBoost | 0.9737 | 0.9944 | 1.0000 | 0.9286 | 0.9630 | 0.9442 |

---

## e) Observations on Model Performance

### Logistic Regression
- Excellent overall performance with very high **Accuracy (0.9737)** and **AUC (0.9954)**.
- Balanced **Precision (0.9756)** and **Recall (0.9524)**.
- High **MCC (0.9433)** indicates robustness under class imbalance.

**Observation:**  
A strong linear baseline that generalizes extremely well on this dataset.

---

### Decision Tree
- Lowest performance across almost all metrics.
- Lower **Accuracy (0.9035)** and **AUC (0.8889)**.
- Weak **Recall (0.8333)**, leading to missed malignant cases.

**Observation:**  
Likely affected by overfitting or limited depth control; not ideal as a standalone model.

---

### K-Nearest Neighbor
- Strong **Accuracy (0.9561)** and **AUC (0.9825)**.
- High **Precision (0.9744)** with slightly reduced **Recall (0.9048)**.

**Observation:**  
Performs well but is conservative in predicting positives; sensitive to feature scaling and choice of *k*.

---

### Naive Bayes Classifier (Gaussian)
- Moderate **Accuracy (0.9211)** with surprisingly high **AUC (0.9891)**.
- Balanced Precision and Recall, but below top performers.

**Observation:**  
Good class separation, but Gaussian assumptions limit classification accuracy.

---

### Ensemble Model – Random Forest
- Very strong performance with high **Accuracy (0.9649)** and **AUC (0.9970)**.
- **Perfect Precision (1.000)** with slightly lower **Recall (0.9048)**.
- High **MCC (0.9258)** confirms stability.

**Observation:**  
Excellent at reducing false positives; a robust and reliable ensemble method.

---

### Ensemble Model – XGBoost
- **Top-performing model overall**.
- Highest **Accuracy (0.9737)** and near-perfect **AUC (0.9944)**.
- **Perfect Precision (1.000)** and best **MCC (0.9442)**.

**Observation:**  
Best bias–variance trade-off; effectively captures complex patterns in the data.

---

## Overall Summary

- **Best Models:**  
XGBoost ≈ Logistic Regression > Random Forest
- **Weakest Model:**  
Decision Tree
- **Key Insight:**  
Ensemble methods significantly outperform single models, while Logistic Regression remains a surprisingly strong baseline.
