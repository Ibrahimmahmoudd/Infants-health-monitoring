# Technical Report: Health Risk Classification

**Problem Type:** Binary Classification  
**Target Variable:** `risk_level` (0 = Healthy, 1 = At Risk)  
**Success Metric:** F1-Score (preferred over Accuracy due to possible class imbalance)

### 1. Data Cleaning & EDA
Our initial analysis identified that the data was relatively clean with a slight imbalance in the `risk_level` classes. We utilized boxplots and KDE plots to observe that features like **jaundice level** and **heart rate** were significant indicators of health risk.

### 2. Modeling Strategy
We followed the mandatory project pipeline by implementing both traditional Machine Learning and Deep Learning approaches:
- **ML Models**: We selected Logistic Regression (baseline), Random Forest (ensemble), and XGBoost (gradient boosting).
- **DL Model**: An Artificial Neural Network (ANN) was built using Keras with a 3-layer Sequential architecture (64 -> 32 -> 1 neurons) and ReLU/Sigmoid activation functions.

### 3. Machine Learning vs. Deep Learning Comparison
As required by the project guidelines, we compared both approaches:

| Feature | Machine Learning (XGBoost) | Deep Learning (ANN) |
| :--- | :--- | :--- |
| **Performance** | Higher (0.99 F1-Score) | High (~0.98 F1-Score) |
| **Training Speed** | Fast | Slower (Requires Epochs) |
| **Interpretability** | High (Feature Importance) | Low (Black Box) |

**Justification:**
- **When ML is better**: For this tabular dataset of ~3,000 rows, Machine Learning (specifically XGBoost) outperformed the ANN. ML models are generally better for tabular data where the relationship between features is structured and the sample size is not in the millions.
- **When DL is better**: Deep Learning would be more suitable if we were working with unstructured data (like medical imaging/X-rays) or if our dataset grew significantly larger, where its ability to learn complex, non-linear patterns would provide a greater advantage.

### 4. Final Selection
The **XGBoost** model was selected for the final solution due to its near-perfect F1-Score and superior ability to handle the specific feature distributions of this medical dataset.
