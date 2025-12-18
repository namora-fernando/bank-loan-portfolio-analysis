# Bank Loan Portfolio Analysis - Key Insights

This document summarizes the key insights obtained from the analysis of a retail bank loan portfolio dataset sourced from Kaggle. <br>
The dataset is used as a representative example of consumer lending data to simulate real-world portfolio risk analysis. <br>
The analysis combines exploratory data analysis (EDA) using Python and interactive dashboards built in Tableau to examine loan performance, borrower risk characteristics, and segment-level credit risk patterns.

---

## 1. Portfolio Overview - Loan Outcome Distribution

**Analytical Question**

What is the overall distribution of loan outcomes in the portfolio?

**Key Findings**

Out of 54,596 loans analyzed: <br>
- 76.81 percent are classified as Fully Paid
- 23.19 percent are classified as Charged Off

This indicates that while most borrowers are able to repay their loans successfully, a meaningful portion of the portfolio results in defaults.

**Interpretation**

The proportion of charged-off loans suggests that credit risk exposure is not negligible. Although the portfolio is not dominated by high-risk loans, the charge-off rate is large enough to justify careful risk monitoring, borrower screening, and segment-aware credit policies.

These results are consistent with the initial Python EDA, where loan status percentages were calculated directly from the raw dataset.

---

## 2. Risk Profile Analysis – Borrower Characteristics vs Loan Status

**Analytical Question**

How do borrower financial and credit characteristics differ between Fully Paid and Charged Off loans?

This section focuses on comparing the distributions of key borrower attributes across the two loan outcome groups.

---

**Credit Score Distribution**

Borrowers with Fully Paid loans tend to have slightly higher median credit scores compared to those with Charged Off loans. Charged Off loans show a wider spread toward lower credit score values, particularly in the lower quartile.

Interpretation: <br>
Credit score appears to be a strong indicator of loan performance. However, the overlap between the two distributions shows that credit score alone does not fully explain loan outcomes.

---

**Annual Income (Log-Transformed)**

After applying a logarithmic transformation, the income distributions for Fully Paid and Charged Off loans appear relatively similar, with Fully Paid loans showing a marginally higher median.

Interpretation: <br>
Income differences exist but are not large enough to act as a standalone predictor of default. Income is likely more informative when combined with other financial variables.

---

**Monthly Debt (Log-Transformed)**

Charged Off loans exhibit slightly higher dispersion and heavier upper tails in monthly debt compared to Fully Paid loans.

Interpretation: <br>
Higher and more volatile debt levels are associated with increased default risk, highlighting the importance of repayment capacity in credit risk assessment.

---

**Credit Problem History Distribution**

This visualization compares the proportion of borrowers with and without prior credit problems across loan outcomes.

Both Fully Paid and Charged Off loans include borrowers with prior credit problems. However, the presence of past credit issues is more prevalent among Charged Off loans.

Interpretation: <br>
Past credit problems increase default risk but do not deterministically lead to charge-offs. This supports the use of multi-factor risk assessment rather than reliance on a single variable.

---

**Page 2 Summary**

Overall, loan outcomes appear to be driven by a combination of creditworthiness, repayment capacity, and historical credit behavior rather than a single dominant factor. The findings closely align with the patterns observed during Python-based exploratory analysis.

---

## 3. Customer and Segment Risk Profile – Segment-Level Risk Drivers

**Analytical Question**

Which borrower segments exhibit higher charge-off risk, and how does prior credit history amplify risk within those segments?

---

**Charge-Off Rate by Loan Purpose**

Certain loan purposes exhibit significantly higher charge-off rates. Small Business, Moving, and Business Loan categories show elevated risk, while purposes such as Buy a Car, Educational Expenses, and Renewable Energy demonstrate lower charge-off rates.

Interpretation: <br>
Loan purpose is a strong segmentation variable and reflects differences in borrower intent, financial uncertainty, and risk exposure.

---

**Charge-Off Rate by Home Ownership**

Borrowers who rent their homes show the highest charge-off rates, while borrowers with mortgages or owned homes tend to have lower default rates.

Interpretation: <br>
Home ownership status likely serves as a proxy for financial stability and long-term financial commitment.

---

**Loan Purpose and Credit Problem Interaction (Heatmap View)**

This heatmap is designed to answer a different question than the purpose-level bar chart:

For the same loan purpose, does having a prior credit problem increase the likelihood of default?

Each cell in the heatmap represents the percentage of loans that are charged off within a specific combination of loan purpose and credit problem history.

Example: <br>
For Small Business loans:

- Borrowers without prior credit problems have a charge-off rate of approximately 43 percent
- Borrowers with prior credit problems have a charge-off rate of approximately 50 percent

Interpretation: <br>
For the same loan purpose, borrowers with prior credit problems consistently show higher charge-off rates. This indicates that prior credit issues act as a risk amplifier rather than an isolated driver of default.

It is important to note that values in the heatmap do not sum to 100 percent. Each value represents an independent conditional charge-off rate within its respective subgroup.

---

**Page 3 Summary**

Charge-off risk varies substantially across customer segments. Certain loan purposes carry inherently higher risk, and this risk is further amplified when combined with a history of credit problems. These findings highlight the importance of segment-aware underwriting and interaction-based risk assessment.

---

**Final Takeaways**

- The loan portfolio exhibits moderate but meaningful credit risk exposure
- Credit score is the strongest individual predictor, but it is insufficient on its own
- Loan purpose and borrower segmentation reveal non-uniform risk patterns
- Prior credit problems amplify risk rather than solely determining outcomes
- Insights derived from Python EDA are consistently validated through Tableau visual analysis
