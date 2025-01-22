# Customer Churn Prediction Using Neural Networks

This repository showcases a project on **Customer Churn Prediction** using a simple neural network. The aim was to predict whether a bank customer would churn (leave the bank) or stay, based on their historical and demographic data.

---

## Dataset
The dataset used in this project was sourced from Kaggle: [Bank Customer Churn Dataset](https://www.kaggle.com/datasets/barelydedicated/bank-customer-churn-modeling). It contains various customer attributes such as age, credit score, balance, etc., along with a target label indicating whether the customer churned (`1`) or not (`0`).

---

## Workflow
### 1. **Data Preprocessing**
- Cleaned the dataset and handled missing values (if any).
- Scaled numerical features for better neural network performance.
- Applied **one-hot encoding** to categorical variables.

### 2. **Feature Engineering**
- Identified and extracted meaningful features to enhance model performance.

### 3. **Model Development**
- Built a simple feedforward neural network with:
  - **2 hidden layers**
  - ReLU activation in hidden layers and Sigmoid activation in the output layer.
  - Binary Cross-Entropy as the loss function.
- Trained the model for **250 epochs** with a batch size of 32.

---

## Results (Initial Model)
- **Accuracy**: The model achieved good accuracy overall.
- **F1 Score**:
  - For the `0` label (customer will not churn): **Great F1 score.**
  - For the `1` label (customer will churn): **Poor F1 score.**
- The **imbalance in the dataset** (significantly more `0` labels than `1` labels) caused poor performance for the minority class.

### Addressing Imbalance
#### Techniques Tried:
1. **Simple Oversampling**: Increased the number of `1` label data by duplicating existing examples.  
2. **Undersampling**: Reduced the number of `0` label data to balance the classes.  
3. **SMOTE (Synthetic Minority Oversampling Technique)**: Generated synthetic samples for the `1` label.  

#### Best Solution: SMOTE
- Using SMOTE to oversample the minority class significantly improved performance.
- Achieved **similar F1 scores for both `0` and `1` labels**, resulting in a more balanced and effective model.

---

## Key Learnings
1. Imbalanced datasets can greatly affect performance for minority classes in binary classification.
2. **SMOTE** outperformed simple oversampling and undersampling techniques for this problem.
3. A simple neural network can perform well, but data preprocessing and balancing play a crucial role in achieving fair results.

---
