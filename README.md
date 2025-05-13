# Deutsche Bank Customer Churn Prediction: End-to-End Analysis and Modeling

This project investigates how factors such as customer demographics, account activity, and financial behaviors influence churn risk at **Deutsche Bank**, a leading global financial institution. By analyzing relationships between these variables and churn outcomes, I built predictive models including Naive Bayes, Decision Trees, Random Forests, and XGBoost to forecast customer attrition and uncover retention opportunities. The objective is to deliver data-driven insights that optimize customer retention strategies and reduce financial losses. The project uses Python libraries like pandas, scikit-learn, XGBoost, and Matplotlib for data analysis, modeling, and visualization.

---

## **Project Overview**

The **Deutsche Bank Customer Churn Prediction** project aims to:

- **Identify Key Churn Drivers**: Determine how customer age, account balance, credit score, and engagement affect churn likelihood  
- **Assess Data Patterns & Risk Factors**: Detect trends, outliers, and attributes associated with high churn risk  
- **Build Predictive Models**: Develop classification models (Naive Bayes, Decision Tree, Random Forest, and XGBoost) to forecast customer churn  
- **Support Proactive Retention Strategies**: Recommend targeted interventions based on model insights to enhance customer loyalty  
- **Ensure Ethical & Reliable AI**: Remove sensitive features (e.g., gender) to prevent bias and ensure fair modeling  

---

## **Dataset Structure**

The dataset contains **10,000 customer records** from **Deutsche Bank**, each representing a unique customer and their banking details. Key features include:

- **Exited**: Indicates whether the customer churned (binary: 1 = churned, 0 = stayed)  
- **CreditScore**: Customer’s credit score (continuous integer)  
- **Geography**: Customer’s country (France, Spain, Germany)  
- **Age**: Customer’s age in years (continuous integer)  
- **Tenure**: Number of years as a bank customer (continuous integer)  
- **Balance**: Account balance in euros (continuous float)  
- **NumOfProducts**: Number of bank products used (discrete integer)  
- **HasCrCard**: Whether the customer has a credit card (binary: 1 = yes, 0 = no)  
- **IsActiveMember**: Whether the customer is an active member (binary: 1 = yes, 0 = no)  
- **EstimatedSalary**: Estimated annual salary in euros (continuous float)  

This dataset provides a comprehensive view of customer behavior and financial profiles, serving as a solid foundation for analyzing churn patterns and building predictive models to identify high-risk customers for **Deutsche Bank**.

---

## **Data Processing and Analysis Steps**

### **Data Cleaning**

- Confirmed **no missing values** or duplicates  
- Removed **irrelevant columns** (`RowNumber`, `CustomerId`, `Surname`)  
- Dropped **gender** to prevent bias in model predictions  
- Encoded categorical variables (`Geography`) via one-hot encoding  

### **Exploratory Data Analysis (EDA)**

- **Churn Distribution**: 20% of customers churned, indicating moderate class imbalance  
- **Key Predictor Insights**:  
  - **Age**: Customers **>42.5 years old** had significantly higher churn rates  
  - **Balance**: Customers with **higher balances** showed varied churn tendencies  
  - **Active Membership**: Inactive customers were **3x more likely to churn**  
- **Engineered Feature**: Created **Loyalty** (`Tenure/Age`) to measure engagement over time  

### **Statistical Insights**

- **CreditScore Impact**: Customers with **lower scores** showed higher churn susceptibility  
- **Product Usage**: Customers with **>1 product** were more likely to stay  
- **Geography**: German customers had slightly higher churn rates than French/Spanish  

---

## **Machine Learning Modeling**

#### **Baseline Naive Bayes Performance**

- Served as an initial benchmark  
- **Accuracy**: 80.6%  
- **Precision**: 54.4%  
- **Recall**: 30.3%  
- **F1-Score**: 38.9%  
- Highlighted limitations in handling mixed feature types  

#### **Model Development Approach**

Four models were developed progressively for comparison:

- **Naive Bayes** (baseline)  
- **Decision Tree**  
- **Random Forest**  
- **XGBoost**  

Hyperparameter tuning via **GridSearchCV** with a stratified 75/25 train-test split ensured robust evaluation.

#### **Decision Tree Performance**

- **Accuracy**: 79.0%  
- **F1-Score**: 56.1%  
- Provided interpretable splits but risked overfitting  

#### **Random Forest Performance**

- **Accuracy**: 81.2%  
- **F1-Score**: 58.0%  
- Balanced predictive power and feature importance interpretability  

#### **XGBoost Performance**

- **Accuracy**: 81.8%  
- **F1-Score**: 59.7%  
- Emerged as the **champion model** due to:  
  - Highest predictive accuracy  
  - Strong handling of class imbalance  
  - Clear feature importance rankings  

---

## **Key Modeling Insights**

- **Ensemble models (XGBoost, Random Forest) outperformed Naive Bayes by 20–21% in F1-score**  
- **Feature Importance** (XGBoost top predictors):  
  1. **EstimatedSalary**  
  2. **Balance**  
  3. **CreditScore**  
  4. **Age**  
- Customers **>42.5 years old** with **low activity** were highest risk  
- **Engineered Loyalty feature** improved model performance  

---

## **Key Workflow Decisions**

- Removed sensitive variables (`Gender`) to prevent bias  
- Applied **stratified sampling** to preserve class distribution  
- Used **F1-score** as the primary metric to balance precision/recall  
- Conducted **cross-validation** to ensure model reliability  

---

## **Key Insights**

### **Exploratory Data Analysis (EDA)**

- **Age** and **activity status** were the strongest churn predictors  
- **High-balance customers** showed varied churn patterns, requiring targeted analysis  
- **German customers** had slightly higher churn rates than other regions  

### **Model Performance**

| Model               | Accuracy | F1-Score |  
|---------------------|----------|----------|  
| Naive Bayes         | 80.6%    | 38.9%    |  
| Decision Tree       | 79.0%    | 56.1%    |  
| Random Forest       | 81.2%    | 58.0%    |  
| **XGBoost**         | **81.8%**| **59.7%**|  

**XGBoost was selected as the champion model** due to its superior predictive power and ability to handle class imbalance.

---

## **Project Highlights**

- **End-to-End Churn Analysis**: Identified key factors driving customer attrition  
- **High-Performance Predictive Modeling**: Achieved **59.7% F1-score** with XGBoost  
- **Actionable Business Insights**:  
  - Target retention efforts for **older, inactive customers**  
  - Monitor **high-balance customers** for early churn signals  
  - Leverage **Loyalty feature** to identify at-risk long-term clients  
- **Ethical AI Practice**:  
  - Excluded gender to prevent bias  
  - Ensured transparent, interpretable modeling  

---

## **Future Work**

- Integrate churn predictions into **CRM systems for real-time alerts**  
- Test **personalized retention offers** (e.g., fee waivers, loyalty bonuses)  
- Expand feature engineering with **transaction frequency** and **service usage data**  
- Conduct **demographic fairness audits** to ensure unbiased predictions  

---

### **Tools & Technologies**

- **Python**: pandas, NumPy, scikit-learn, XGBoost  
- **Visualization**: Matplotlib, Seaborn  
- **Model Evaluation**: Precision-Recall, Confusion Matrices, Feature Importance  

This solution equips **Deutsche Bank** with strategic, data-driven insights to proactively reduce customer churn, enhance retention strategies, and protect long-term revenue in a competitive banking landscape.
