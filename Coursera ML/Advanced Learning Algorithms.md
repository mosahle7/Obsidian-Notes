
#### **Neural Networks**:

Tensorflow Implementation
AI: **ANI( Weak AI), AGI (Strong AI)**

**AF**: Linear, Sigmoid, ReLu, Softmax

**Softmax Regression**:
LF: **Sparse Categorical Cross Entropy**

**Multi-Label Classification**

**CNN**

**Testing**:
Regression: J_train and J_test
Classification: J_train and J_test, No. of correct

**Model Selection**: Split into 3: Train, Cross-Validation and Test

**Bias and Variance**:

- More Training Data: V
- More Features:         B
- Less Features:           V
- More Polynomial Features: B
- Increase Lambda:      V
- Decrease Lambda:     B

**Addition of Data**:
Data Augmentation
Data Synthesis

**Transfer Learning:**
Supervised Pretraining
Fine tuning

Recall, Precision and F1 Score

#### **Decision Trees**:

Supervised machine learning algorithm that splits data into branches based on feature values, forming a tree-like structure to make predictions.
##### **Learning**:

1. Choose Feature to split which maximizes purity
2. Stop Splitting when:
     - Node is 100% one class
     - Splitting results in exceeding a max depth
     - Improvements are below a threshold
     - No. of examples in a node is below a threshold

**Entropy**
**Information Gain**

**Continuous Valued Features**

**Regression Decision Trees**: Variance instead of entropy.

**Tree Ensembles**:

**Random Forest**:

**Bagging** (Bootstrap Aggregating): Train multiple models on different random subsets with replacement of training data

**Bagged Decision Trees**: Train DTs using bagging and final output is avg or majority vote.

Train trees in parallel.
Final prediction: majority vote / avg.

**Random Feature Selection:** Random subset of k < n  features . **k= sqrt(n)**

RF = BDTs + Random Feature Selection
more diverse and less correlated

**No. of trees (B)**: 64-128, 100

**Random Forest** is an ensemble method that builds multiple decision trees using random subsets of data and features, then combines their results to improve accuracy and reduce overfitting.

**Boosted Trees**:
Sequential Training of DTs and each new tree focuses on correcting errors by giving more weight on misclassified examples

Train trees sequentially.
Final prediction: weighted sum of all trees.

**AdaBoost, Gradient Boosting and XGBoost** are examples.

**XGBoost**:

Regularization, Fast Parallel Processing, Handling of missing values, Good choice of def splitting and stop splitting criteria.



