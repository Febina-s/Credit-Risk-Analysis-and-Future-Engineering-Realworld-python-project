# Credit-Risk-Analysis-and-Future-Engineering-Realworld-python-project
![cra image](https://github.com/Febina-s/Credit-Risk-Analysis-and-Future-Engineering-Realworld-python-project
/blob/main/cra image.jfif)
## 📌 Project Summary
In banking and financial institutions, raw loan data cannot be used directly 
for risk modeling or lending decisions.This project demonstrates a **real-world loan data preprocessing pipeline** built using **Python and NumPy**, similar to workflows used in **banks, NBFCs, and financial institutions** before building credit risk or default prediction models.

The project focuses on:
- Cleaning raw loan application data
- Handling missing values using **risk-aware financial logic**
- Transforming categorical variables into **model-ready numeric features**
- Performing **currency normalization (USD → EUR)**
- Producing a **final, analysis-ready dataset** suitable for credit risk modeling

---

## 🎯 Business Objective
Financial institutions rely on **high-quality, standardized data** to assess borrower risk and estimate probability of default (PD).

The objectives of this project are to:

- Prepare loan data for **credit risk analysis**
- Reduce noise and bias from raw categorical variables
- Apply **conservative financial assumptions** while handling missing data
- Enable downstream use cases such as:
  - Default prediction models
  - Loan portfolio risk analysis
  - Regulatory and reporting analytics

---

## 📂 Dataset Overview
- **Records**: 10,000 loan applications  
- **Data Type**: Structured tabular data  
- **Domains Covered**:
  - Loan amounts & repayments
  - Interest rates & installments
  - Borrower verification status
  - Loan performance (default / non-default)
  - Geographic location (U.S. states)
- **Currency**: USD (converted to EUR during preprocessing)


The raw dataset contains:
- Missing values
- Categorical text fields
- Mixed numeric formats
- Currency inconsistencies

---

## 🧱 Project Workflow (End-to-End)

### 1️⃣ Dataset Splitting
The original dataset was split into:
- **Numeric dataset** (loan amounts, interest rate, payments, etc.)
- **String dataset** (loan status, verification status, state, issue date)

This separation allows **cleaner, domain-specific preprocessing**.

---

### 2️⃣ String Column Processing & Feature Engineering

#### 🔹 Loan Status Transformation
Loan status values were grouped into **Good vs Bad credit outcomes**:

| Category | Encoding |
|--------|----------|
| Fully Paid, Current, Issued, Grace Period | 1 (Good) |
| Charged Off, Default, Long Delinquency, Missing | 0 (Bad) |

✔ Reflects **credit risk modeling logic**  
✔ Missing values treated conservatively  

---

#### 🔹 Verification Status Encoding
Verification status was simplified into a binary indicator:

| Status | Encoding |
|------|----------|
| Verified, Source Verified | 1 |
| Not Verified, Missing | 0 |

✔ Mirrors underwriting confidence  
✔ Reduces categorical complexity  

---

#### 🔹 Geographic (State) Processing
- 50 U.S. states + missing values observed
- Low-frequency states can distort model coefficients
- States grouped into **4 geographic regions**:
  - West
  - South
  - Midwest
  - East
- Missing states assigned to a neutral baseline

✔ Prevents overfitting  
✔ Improves statistical stability  

---

### 3️⃣ Numeric Data Cleaning & Missing Value Treatment
Missing numeric values were previously filled with placeholders.  
These were replaced using **financially meaningful logic**:

| Variable | Replacement Strategy |
|--------|----------------------|
| Funded Amount | Minimum observed value |
| Loan Amount, Installments, Payments | Maximum observed value |
| Interest Rate | Retained after validation |

✔ Aligns with **risk-averse financial assumptions**  
✔ Uses stored dataset statistics (min / mean / max)

---

### 4️⃣ Currency Conversion (USD → EUR)
Since the analysis is positioned for a **European finance context**:

- Imported **monthly EUR-USD exchange rates**
- Assigned rates based on loan issue month
- Used annual average rate for missing dates
- Converted all USD monetary columns to EUR
- Retained both USD & EUR values for traceability

✔ Real-world international banking practice  
✔ Prevents currency-based misinterpretation  

---

### 5️⃣ Interest Rate Normalization
- Interest rates converted from percentages to decimals
- Standardized format improves:
  - Mathematical modeling
  - Interest calculations
  - Interpretability

---

### 6️⃣ Dataset Consolidation & Finalization
- Cleaned numeric and string datasets merged
- Records sorted by **Loan ID**
- Headers added and aligned
- Final dataset exported as CSV
- Checkpoints created for reproducibility

✔ Fully model-ready dataset  
✔ Zero missing values  

---

## 📊 Key Insights
- Raw loan data hides **significant risk signals** in text fields
- Missing values often imply **higher credit risk**
- Geographic grouping reduces noise from sparse categories
- Currency normalization is essential in global finance
- Proper preprocessing improves **model accuracy & trust**

---

## 🏦 Real-World Financial Relevance
This preprocessing pipeline reflects workflows used in:
- Retail & Corporate Banking
- Credit Risk & Underwriting Teams
- NBFCs & FinTech Lending Platforms
- Regulatory & Compliance Analytics

The final dataset is suitable for:
- Probability of Default (PD) modeling
- Loan approval risk scoring
- Portfolio stress testing

---

## 🛠 Tools & Technologies
- **Python**
- **NumPy**
- **Jupyter Notebook**
- **CSV / NPZ file handling**
- **Vectorized numerical operations**

---

## 🧪 Techniques Applied
- Data Cleaning
- Feature Engineering
- Missing Value Imputation
- Risk-Based Encoding
- Currency Conversion
- Dataset Validation
- Checkpointing for Reproducibility

---

## 📁 Final Output
- `loan_data_preprocessed.csv`
- Fully cleaned, standardized loan dataset
- Ready for:
  - Machine Learning
  - Financial Analysis
  - Visualization & Reporting

---

## 🚀 Future Scope
- Credit default prediction models
- Exploratory data analysis (EDA)
- Visualization dashboards
- Multi-year exchange rate integration

---

## 👤 Author
**[Your Name]**  
Aspiring Data Analyst | Finance & Credit Risk Analytics  

---

⭐ *If you found this project useful, feel free to star the repository!*
