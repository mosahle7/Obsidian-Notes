
#### **Linear Regression**:

CF: **Mean Squared Error**
Gradient Descent

**Feature Scaling**:
1) **Normalization (Min-Max Scaling):** (0-1), more sensitive to outliers.
2) **Standardization (Z-score Scaling):** less sensitive to outliers.

#### **Logistic Regression**:

**Sigmoid/Logistic Function**

**Underfit:** High Bias
**Overfit**: High Variance

**Addressing Overfitting:**

More Training Egs
Feature Selection
**Regularization**: L1 (Lasso) &  L2 (Ridge)

**Lasso:**
**Penalty:** Sum of absolute values of weights.
Shrink some weights to exactly 0 (feature selection).
Useful when only few features are important.

**Ridge:**
**Penalty:** Sum of squares of weights.
Shrink weights toward 0, but never 0, reduces their effect.
Useful when features are correlated.

Over, over!!!, Let's dive into [[Advanced Learning Algorithms]]