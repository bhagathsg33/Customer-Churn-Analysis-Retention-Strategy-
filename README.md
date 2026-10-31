# 📊 Customer Churn Prediction & Revenue Risk Analysis | Python & Machine Learning

## 📌 Project Overview

Customer churn is a major challenge for businesses operating in subscription-based industries. Understanding why customers discontinue services and identifying customers who are likely to leave can help organizations improve customer retention and protect recurring revenue.

This project focuses on analyzing customer behavior, identifying churn patterns, developing predictive machine learning models, and estimating potential revenue loss.

Using Python and machine learning techniques, the project transforms customer data into actionable business insights and develops a customer prioritization framework to support targeted retention strategies.

## 🎯 Project Objectives

- Analyze customer churn patterns and behavioral characteristics.
- Identify factors associated with customer attrition.
- Examine relationships between contract types, tenure, payment methods, and churn.
- Perform statistical hypothesis testing to validate customer behavior patterns.
- Develop machine learning models to predict customer churn.
- Estimate customer churn probability and potential revenue at risk.
- Identify high-value customers with high churn probability.
- Generate targeted customer retention strategies.

## 🛠️ Tools & Technologies

| Technology | Application |
|---|---|
| Python | Data analysis and model development |
| Pandas | Data manipulation and preprocessing |
| NumPy | Numerical operations |
| Matplotlib | Data visualization |
| Seaborn | Statistical visualization |
| SciPy | Statistical hypothesis testing |
| Scikit-learn | Machine learning and model evaluation |
| Jupyter Notebook | Development and analytical workflow |

## 📂 Dataset

**Dataset:** Telco Customer Churn Dataset

The dataset contains customer-level information relating to telecommunications services, billing, customer tenure, contract arrangements, and churn status.

Key variables include:

- CustomerID
- Gender
- SeniorCitizen
- Partner
- Dependents
- Tenure
- InternetService
- Contract
- PaymentMethod
- MonthlyCharges
- TotalCharges
- Churn

The target variable is **Churn**, which indicates whether a customer has discontinued the service.

## 🔄 Project Workflow

### 1. Data Loading & Cleaning

- Imported the customer dataset using Pandas.
- Examined data structure, variable types, missing values, and unique observations.
- Converted `TotalCharges` into a numerical format.
- Handled missing observations.
- Encoded the target variable `Churn` into binary values (0 and 1).

### 2. Exploratory Data Analysis (EDA)

Analyzed customer churn patterns across different business dimensions:

- Overall customer churn distribution.
- Churn rate across contract types.
- Customer tenure and churn behavior.
- Churn patterns by internet service.
- Payment method and customer attrition.
- Relationship between monthly charges and churn.
- Relationship between customer tenure and churn.

### 3. Statistical Hypothesis Testing

Applied statistical techniques to investigate relationships between customer characteristics and churn.

**Chi-Square Test**

- Examined the association between contract type and customer churn.
- Evaluated statistical significance using the p-value.

**Independent Samples T-Test**

- Compared monthly charges between churned and retained customers.
- Used Welch's t-test to account for potentially unequal variances.

### 4. Feature Engineering

Created additional analytical variables to improve customer segmentation and business interpretation.

- **ServiceCount:** Number of additional services subscribed to by a customer.
- **CustomerValue:** Estimated customer value proxy calculated using monthly charges multiplied by tenure.
- **AnnualValue:** Annualized customer charges calculated using monthly charges multiplied by 12.

### 5. Machine Learning Model Development

Developed and evaluated two classification models.

**Logistic Regression**
- Implemented a classification pipeline.
- Applied numerical standardization.
- Used One-Hot Encoding for categorical variables.
- Evaluated customer churn predictions.

**Random Forest Classifier**
- Developed an ensemble-based classification model.
- Used 300 decision trees.
- Applied class balancing to address the unequal distribution of churn classes.
- Generated churn probabilities for customer risk assessment.

The dataset was divided into 80% training data and 20% testing data using stratified sampling.

### 6. Model Evaluation & Comparison

Evaluated both models using:

- Accuracy
- Precision
- Recall
- F1-Score
- ROC-AUC
- Confusion Matrix

**Model Performance**

| Evaluation Metric | Logistic Regression | Random Forest |
|---|---:|---:|
| Accuracy | 80.38% | 76.33% |
| Precision | 64.85% | 54.39% |
| Recall | 57.22% | 67.91% |
| F1-Score | 60.80% | 60.40% |
| ROC-AUC | 83.58% | 82.35% |

*Note: These are the results obtained from the notebook's 20% test split.*

Logistic Regression achieved higher accuracy, precision, F1-score, and ROC-AUC, while Random Forest achieved higher recall.

Random Forest was subsequently used for customer churn probability estimation and risk segmentation.

### 7. Customer Churn Risk Segmentation

Classified customers into three risk categories based on predicted churn probabilities.

| Risk Category | Churn Probability |
|---|---|
| Low Risk | Below 40% |
| Medium Risk | 40%–69.99% |
| High Risk | 70% and above |

This segmentation helps businesses identify customers who may require immediate retention attention.

### 8. Revenue at Risk Analysis

Estimated annual revenue exposure using the following formula:

**Revenue at Risk = Monthly Charges × 12 × Churn Probability**

Calculated the estimated annual revenue at risk across the customer base to understand the potential financial implications of customer attrition.

### 9. High-Value Customer Identification

Created customer value segments using quantile-based classification:

- Low Value
- Medium Value
- High Value

Combined customer value segments with churn risk categories to identify high-value customers who also have a high probability of leaving.

This approach helps prioritize retention efforts based on both customer value and churn risk.

### 10. Retention Strategy Generation

Developed a rule-based retention strategy generator to recommend actions based on customer risk and value segments.

| Customer Segment | Suggested Retention Strategy |
|---|---|
| High Risk – High Value | Personalized retention offer + priority support |
| High Risk – Medium Value | Discount + service upgrade |
| High Risk – Low Value | Automated retention campaign |
| Medium Risk | Engagement campaign + service education |
| Low Risk | Loyalty & cross-sell campaign |

Finally, exported the analyzed customer dataset and high-priority customer list into CSV files for further analysis and business use.

## 📈 Key Analytical Findings

The analysis generated the following results:

- **26.58% overall churn rate** in the cleaned dataset.
- Contract type showed a statistically significant association with customer churn (Chi-square p-value: 7.33 × 10⁻²⁵⁷).
- Monthly charges differed significantly between churned and retained customers (Welch's t-test p-value: 2.66 × 10⁻⁷²).
- Logistic Regression achieved an ROC-AUC of 83.58%.
- Random Forest achieved a churn recall of 67.91%.
- 332 customers were classified as both high-value and high-risk.
- Estimated annual revenue at risk was approximately **$2.16 million**, based on the project's probability-weighted revenue estimation.

*These findings are based on the dataset and analytical methodology implemented in this project. Revenue at risk represents an estimate, not confirmed future revenue loss.*

## 💼 Business Recommendations

Based on the analysis, the following business actions can be considered:

1. Prioritize high-value customers with high predicted churn probabilities for personalized retention initiatives.
2. Investigate contract-related churn patterns and encourage suitable longer-term subscription plans.
3. Develop targeted engagement campaigns for customers in medium-risk categories.
4. Monitor customers with high monthly charges and evaluate their service experience.
5. Use predictive churn probabilities to support proactive customer retention planning.
6. Monitor potential revenue exposure to help allocate retention resources more effectively.

## 📁 Project Structure

```text
Customer-Churn-Analysis/
│
├── Projectchurn.ipynb
│
├── WA_Fn-UseC_-Telco-Customer-Churn.csv
│
├── customer_churn_analysis_final.csv
│
├── high_priority_customers.csv
│
└── README.md
```

*The exported CSV files are generated when the notebook is executed. Include them in the repository if you want to share the outputs.*

## 🚀 How to Run the Project

### Prerequisites

- Python 3.x
- Jupyter Notebook

### Step 1: Clone the Repository

```bash
git clone YOUR_GITHUB_REPOSITORY_URL
cd Customer-Churn-Analysis
```

### Step 2: Install Required Libraries

```bash
pip install pandas numpy matplotlib seaborn scipy scikit-learn jupyter
```

### Step 3: Load the Dataset

Place `WA_Fn-UseC_-Telco-Customer-Churn.csv` in the same directory as the notebook.

### Step 4: Run the Notebook

```bash
jupyter notebook Projectchurn.ipynb
```

Execute the notebook cells sequentially to reproduce the analysis, statistical tests, machine learning models, customer segmentation, and revenue risk estimation.

## 📚 Skills Demonstrated

- Data Cleaning & Preprocessing
- Exploratory Data Analysis
- Statistical Hypothesis Testing
- Feature Engineering
- Logistic Regression
- Random Forest Classification
- Machine Learning Model Evaluation
- Customer Churn Prediction
- Customer Segmentation
- Revenue Risk Estimation
- Retention Strategy Development
- Business Analytics & Decision Support

## 👨‍💻 Author

**Bhagath S G**

M.Sc. Business Analytics

Aspiring Business Analyst | Data Analyst | Analytics Professional

Interested in transforming business data into actionable insights through analytical thinking, statistical techniques, and predictive modeling.


## ⭐ Conclusion

This project demonstrates an end-to-end approach to customer churn analytics, combining exploratory data analysis, statistical validation, predictive modeling, and business-oriented customer segmentation.

By connecting machine learning predictions with revenue risk estimation and targeted retention strategies, the project illustrates how analytics can support customer relationship management and data-driven business decisions.
