#  Customer App Behaviour Analysis

## 📌 Project Overview

This project analyzes customer behaviour in a mobile application to understand why some users subscribe to a paid product while others do not.

The analysis combines **exploratory data analysis, feature engineering, customer behaviour analysis, and logistic regression classification** to identify users who are more or less likely to subscribe.

The project is designed from a practical business perspective: once a user's early in-app behaviour is available, the company can use a predictive model to prioritize marketing and retention efforts.

---

## 💼 Business Problem

A mobile application receives a large number of new users, but only a proportion eventually subscribe to the paid product.

The key questions addressed in this project are:

- What characteristics and behaviours are associated with subscription?
- Can early user activity be used to predict subscription likelihood?
- Can the model identify users who may require additional marketing attention?
- How can these predictions be translated into a targeted marketing strategy?

---

## 🎯 Objectives

- Explore demographic and behavioural characteristics of app users.
- Analyze early engagement with different app screens and features.
- Engineer useful behavioural features from the raw data.
- Build a classification model to predict subscription.
- Evaluate the model using classification metrics.
- Validate model performance using cross-validation.
- Translate predictions into actionable marketing recommendations.

---

## 📊 Dataset

The project uses the following input files:

- `appdata10.csv` — Original app-user dataset.
- `top_screens.csv` — List of important/high-frequency screens.
- `new_appdata10.csv` — Processed dataset used for the final modelling stage.

### Target Variable

`enrolled` — Indicates whether the user subscribed to the paid product.

### Main Feature Categories

The dataset contains variables related to:

- User demographics
- App usage
- Screen activity
- Gaming activity
- Premium-feature usage
- User engagement
- Time-related behaviour

> **Note:** The dataset files must be present in the working directory for the notebook to run from start to finish.

---

## 🔬 Methodology

### 1. Exploratory Data Analysis

The project initially examines:

- Data structure and variable types
- Missing values
- Distribution of numerical variables
- User behaviour
- Correlations between variables
- Relationship between engagement and subscription

Visualizations include:

- Histograms
- Correlation plots
- Correlation matrices
- Behavioural comparisons

---

### 2. Feature Engineering

The `screen_list` variable contains information about screens visited by each user.

The project:

- Formats the screen-list information.
- Identifies frequently used screens.
- Creates indicator variables for important screens.
- Removes redundant fields after feature extraction.
- Removes variables that are not appropriate for prediction.

This converts raw app-navigation behaviour into meaningful **model-ready numerical features**.

---

### 3. Data Preprocessing

The target variable is separated from the predictors.

The dataset is divided into:

- **80% Training Data**
- **20% Testing Data**

The user identifier is removed from the predictive features.

Numerical features are standardized using `StandardScaler`.

---

## 🤖 Classification Model

The final classification model is:

### Logistic Regression with L1 Regularization

L1 regularization is useful because it can shrink less-important coefficients toward zero, providing a degree of feature selection while maintaining the interpretability of logistic regression.

The model predicts the probability that a user will subscribe to the paid product.

---

## 📈 Model Evaluation

The model is evaluated using:

- Accuracy
- Precision
- Recall
- F1 Score
- Confusion Matrix
- 10-fold Cross-Validation

### Test Performance

| Metric | Performance |
|---|---:|
| Accuracy | ~76.8% |

The Logistic Regression model achieves approximately **76.8% accuracy on the test set**.

However, accuracy alone is not sufficient for evaluating a marketing-focused classification problem. Precision, recall, F1-score, and business-level conversion impact should also be considered.

---

## 🔄 Model Validation

The notebook uses **10-fold cross-validation** to assess whether model performance remains reasonably stable across different training subsets.

For production use, the model should additionally be evaluated on future cohorts of new users because:

- User behaviour can change over time.
- App features may change.
- Marketing strategies can influence conversion.
- Customer preferences may shift.

Therefore, ongoing monitoring on future user cohorts would be important.

---

## 💡 Key Business Insights

The model can be used to divide new users into groups such as:

- **Likely to subscribe**
- **Unlikely to subscribe**

This enables targeted marketing rather than treating every user identically.

### Potential Marketing Strategies

**Users likely to subscribe**

These users may require relatively light promotional communication because their existing behaviour indicates a higher probability of conversion.

**Users unlikely to subscribe**

These users can receive more targeted onboarding or engagement campaigns.

Possible interventions include:

- Personalized messages
- Additional product information
- Free trials
- Discounts
- Feature recommendations
- Targeted onboarding

The effectiveness of these strategies should ultimately be measured using **incremental subscription rates and revenue**, rather than model accuracy alone.

---

## 📊 Business Application

The predicted subscription probability can be used to prioritize marketing resources.

For example:

```text
New User
    ↓
Collect Early App Behaviour
    ↓
Predict Subscription Probability
    ↓
┌───────────────────────┐
│ High Probability      │
│ Light Promotion       │
└───────────────────────┘
            │
            OR
            │
┌───────────────────────┐
│ Low Probability       │
│ Targeted Intervention │
└───────────────────────┘
```

This creates a data-driven approach to **customer acquisition, onboarding, and retention**.

---

## 🛠️ Tech Stack

- **Python**
- **Pandas**
- **NumPy**
- **Matplotlib**
- **Seaborn**
- **Scikit-learn**




## 📝 Conclusion

This project demonstrates how customer behaviour data can be converted into actionable subscription predictions.

A **Logistic Regression model with L1 regularization** achieved approximately **76.8% test accuracy**, while **10-fold cross-validation** was used to assess the stability of the model.

The most important practical takeaway is not simply predicting who will subscribe, but using those predictions to **allocate marketing effort more efficiently and improve conversion**.

Overall, the project demonstrates how **exploratory analysis, behavioural feature engineering, classification modelling, model validation, and business interpretation** can be combined to solve a practical customer analytics problem.
