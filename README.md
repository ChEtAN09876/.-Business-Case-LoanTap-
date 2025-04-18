
# Credit Line Approval Prediction - LoanTap

## 🧾 Problem Statement

Given a set of attributes for an individual, determine if a credit line should be extended to them. If yes, what should the repayment terms be from a business recommendation standpoint?

## 📦 Dataset

**Filename**: `LoanTapData.csv`

### 📚 Data Dictionary

| Column | Description |
|--------|-------------|
| loan_amnt | The listed loan amount applied by the borrower. |
| term | Loan term in months (36 or 60). |
| int_rate | Interest rate on the loan. |
| installment | Monthly loan installment. |
| grade | LoanTap assigned loan grade. |
| sub_grade | LoanTap assigned loan subgrade. |
| emp_title | Job title of the borrower. |
| emp_length | Employment length in years (0–10). |
| home_ownership | Home ownership status. |
| annual_inc | Self-reported annual income. |
| verification_status | Income verification status. |
| issue_d | Loan funding date. |
| loan_status | Target variable – current loan status. |
| purpose | Loan purpose category. |
| title | Title provided by borrower. |
| dti | Debt-to-Income ratio. |
| earliest_cr_line | Date of earliest credit line. |
| open_acc | Number of open credit lines. |
| pub_rec | Number of derogatory public records. |
| revol_bal | Total revolving balance. |
| revol_util | Credit utilization ratio. |
| total_acc | Total number of credit lines. |
| initial_list_status | Loan listing status. |
| application_type | Individual or joint application. |
| mort_acc | Number of mortgage accounts. |
| pub_rec_bankruptcies | Public record bankruptcies. |
| address | Address of the individual. |

## 🧪 Concepts Covered

- Exploratory Data Analysis (EDA)
- Feature Engineering
- Logistic Regression
- Precision vs Recall Tradeoff

## ✅ What "Good" Looks Like

### 1. EDA & Data Understanding
- Load the dataset and inspect structure (types, nulls, unique values)
- Use `countplots`, `boxplots`, and `heatmaps` to explore relationships with `loan_status`

### 2. Correlation Analysis
- Check correlation matrix to identify multicollinearity
- Visualize using Seaborn heatmaps

### 3. Feature Engineering
- Create binary flags:
  - `flag_pub_rec` → 1 if `pub_rec` > 1 else 0
  - `flag_mort_acc` → 1 if `mort_acc` > 1 else 0
  - `flag_pub_rec_bankruptcies` → 1 if `pub_rec_bankruptcies` > 1 else 0

### 4. Handling Missing Values & Outliers
- Impute missing values using appropriate techniques (mean, median, mode, KNN etc.)
- Detect and treat outliers in numerical columns

### 5. Scaling
- Apply `StandardScaler` or `MinMaxScaler` to scale features before modeling

### 6. Modeling: Logistic Regression
- Use Logistic Regression from `sklearn` or `statsmodels`
- Interpret coefficients and p-values (if using statsmodels)

## 📊 Model Evaluation

- Classification Report (Precision, Recall, F1-score)
- ROC AUC Curve
- Precision-Recall Curve

## 💡 Business Recommendations

- Clearly define repayment terms and risk cutoffs based on probability thresholds.
- Use model probabilities to create a tiered approval structure:
  - **High Approval Likelihood (>80%)** → Instant approval with lower interest
  - **Medium (60-80%)** → Review by analyst
  - **Low (<60%)** → Rejection or higher interest

## 🛠️ Libraries Used

- Pandas
- NumPy
- Matplotlib / Seaborn
- Scikit-learn
- Statsmodels

---

