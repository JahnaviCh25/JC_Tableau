# Financial Transaction Fraud Detection Analysis  

## Introduction  
Financial fraud has evolved into a sophisticated challenge in the digital era, with fraudsters exploiting transaction types, amounts, and timing patterns. This project focuses on analyzing a synthetic dataset of financial transactions to identify fraudulent activity patterns. Through data analysis and visualization, we aim to highlight key fraud indicators, such as transaction amount anomalies, specific transaction types, and suspicious timing patterns.  

The project integrates **Python** for data analysis and **Tableau** for interactive visualizations to gain deeper insights into how fraudulent transactions differ from legitimate ones.  

---

## Dataset  
The dataset used in this project is the **PaySim synthetic financial dataset** from Kaggle. It simulates mobile money transactions based on real-world data patterns. The dataset provides one month of transaction records, allowing us to analyze legitimate and fraudulent activities.  

**Dataset Source:** [Kaggle - PaySim Dataset](https://www.kaggle.com/datasets/ealaxi/paysim1)  

### Attributes  
The dataset contains **11 attributes**, describing various transaction details:  

- **step**: Represents the hour of the transaction (ranges from 1 to 744, representing 30 days)  
- **type**: Type of transaction (*TRANSFER, CASH_OUT, DEBIT, PAYMENT, CASH_IN*)  
- **amount**: Transaction amount  
- **nameOrig**: Account initiating the transaction  
- **oldbalanceOrg**: Balance of the origin account before the transaction  
- **newbalanceOrig**: Balance of the origin account after the transaction  
- **nameDest**: Recipient account of the transaction  
- **oldbalanceDest**: Balance of the destination account before the transaction  
- **newbalanceDest**: Balance of the destination account after the transaction  
- **isFraud**: Binary indicator (1 = fraud, 0 = legitimate)  
- **isFlaggedFraud**: Flag set by the system for suspicious transactions  

---

## Tools & Technologies  
The following tools were used for data analysis and visualization:  

### **Python**  
- **pandas** – Data manipulation and preprocessing  
- **matplotlib & seaborn** – Data visualization  
- **numpy** – Numerical operations  

### **Tableau**  
- Used for **interactive** visualizations to identify fraud patterns  

---

## Data Cleaning & Preparation  
To ensure data consistency, the following preprocessing steps were performed:  

✔ Replaced missing latitude and longitude attributes with city coordinates  
✔ Created new derived features:  
   - **hour**: Extracted from the *step* attribute for temporal analysis  
   - **balance_diff**: Calculated balance variations before and after transactions  
✔ Standardized transaction type values  
✔ Removed duplicate records and verified data integrity  

---

## Exploratory Data Analysis (EDA)  
Initial data exploration helped uncover key patterns and trends:  

1. **Dataset Overview**  
   - Contains **6.3 million** transactions  
   - Includes **5 transaction types**  
   - Over **2.7 million unique destination accounts**  

2. **Transaction Amount Distribution**  
   - Fraudulent transactions generally involve **higher amounts**  
   - Most transactions fall within lower amounts, forming a **right-skewed** distribution  

3. **Fraud Frequency Analysis**  
   - Fraud occurs in **0.129%** of transactions  
   - **TRANSFER and CASH_OUT transactions** show the highest fraud rates  

### **Hypotheses for Fraudulent Transactions**  
Based on initial exploration, the following hypotheses were formulated:  

- **H1**: Fraudulent transactions involve **higher amounts** than legitimate ones.  
- **H2**: Fraud is **concentrated** in specific transaction types (*TRANSFER* and *CASH_OUT*).  
- **H3**: Fraudulent transactions are **more common during early morning hours**.  

---

## **Key Findings & Visualizations**  

### **1. Transaction Amounts by Fraud Status (H1)**
**Visualization:** Box plot comparing fraud vs. legitimate transaction amounts.  

✔ Fraudulent transactions **typically involve larger amounts**  
✔ Significant separation in the distribution of fraud and non-fraud transactions  

---

### **2. Fraud Rate by Transaction Type (H2)**  
**Visualization:** Fraud rate across different transaction types.  

✔ **TRANSFER transactions** have the **highest fraud rate (0.8%)**  
✔ **CASH_OUT transactions** also show notable fraud occurrence (0.2%)  
✔ Other transaction types (**PAYMENT, DEBIT, CASH_IN**) have **minimal fraud risk**  

---

### **3. Temporal Fraud Patterns (H3)**  
**Visualization:** Fraud occurrence by hour of the day.  

✔ Fraudulent transactions peak between **2-5 AM**, with **maximum activity around 3-4 AM**  
✔ Legitimate transactions are more evenly distributed throughout the day  
✔ **Business hours show minimal fraud activity**  

---

### **4. Account Balance Analysis**  
**Visualization:** Box plot of account balances before fraudulent vs. non-fraudulent transactions.  

✔ Fraudulent transactions originate from **higher balance accounts**  
✔ Destination accounts in fraudulent transactions tend to have **lower balances**  
✔ Fraudulent transactions show **greater balance variations** compared to legitimate ones  

---

## **Key Takeaways from Analysis**  

📌 **Transaction Amount Patterns:**  
✔ Fraudulent transactions involve **higher amounts**  
✔ Significant **variance** in fraudulent transaction amounts  

📌 **Transaction Type Insights:**  
✔ Fraud is concentrated in **TRANSFER and CASH_OUT transactions**  
✔ Other transaction types pose **low fraud risk**  

📌 **Temporal Fraud Patterns:**  
✔ **Peak fraud activity occurs between 2-5 AM**  
✔ **Low fraud activity during business hours**  

📌 **Account Balance Trends:**  
✔ Fraud originates from **high-balance accounts**  
✔ Destination accounts in fraud cases have **low balances**  

---

## **Fraud Detection Strategies**  

🔹 **Time-Based Monitoring**: Implement stricter fraud checks during **high-risk hours (2-5 AM)**  
🔹 **Transaction Amount Thresholds**: Flag transactions above certain amount limits  
🔹 **Transaction Type Risk Scoring**: Assign risk scores based on transaction type  
🔹 **Account Balance Pattern Analysis**: Monitor for unusual balance movements  

---

## **Conclusion**  
This project successfully identified key fraud patterns in financial transactions:  

✅ **Time-based fraud risks** – Fraudulent transactions are more likely **between 2-5 AM**  
✅ **Transaction type vulnerabilities** – Most fraud occurs in **TRANSFER and CASH_OUT transactions**  
✅ **Amount & balance patterns** – Fraudulent transactions tend to involve **higher amounts** and originate from **high-balance accounts**  

These insights provide a foundation for **fraud detection models**, allowing financial institutions to improve monitoring strategies and mitigate risks.  

---

## **References**  
1. Lopez-Rojas, E., & Axelsson, S. (2016). PaySim: A financial mobile money simulator for fraud detection. *28th European Modeling and Simulation Symposium (EMSS)*, Larnaca, Cyprus.  
2. PaySim Dataset (2017). *Synthetic Financial Datasets for Fraud Detection* [Dataset]. Kaggle. [Link](https://www.kaggle.com/datasets/ealaxi/paysim1)  

---

## **How to Use This Project**  
1. Clone this repository:  
   ```sh
   git clone https://github.com/your-repo-name.git
   cd your-repo-name
   ```
2. Install dependencies:  
   ```sh
   pip install pandas numpy matplotlib seaborn
   ```
3. Run the Python analysis:  
   ```sh
   python fraud_detection_analysis.py
   ```
4. Open Tableau dashboard for interactive visualizations.  

---
