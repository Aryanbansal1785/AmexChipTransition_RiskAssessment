# Enterprise Risk Management Analytics
## American Express — EMV Chip Transition Risk Assessment
### ALY6130 Risk Management Analytics | Northeastern University | Winter 2026

---

## Project Overview

This project presents a comprehensive Enterprise Risk Management (ERM) analysis of American Express during its EMV chip card technology transition in the United States. The EMV transition, which became effective in October 2015, was designed to reduce counterfeit card fraud by shifting liability from card-issuing banks to merchants who had not yet upgraded to chip-enabled terminals.

While the transition successfully reduced card-present fraud, it introduced a new set of competitive, financial, and legal risks for American Express. This project identifies, assesses, and develops risk response strategies for three priority risks using both qualitative and quantitative analytics techniques, including a Random Forest machine learning classifier and Monte Carlo simulation.

---

## Business Context

American Express operates a closed-loop payment network, meaning it controls both card issuance and the payment network itself. This structure made its EMV terminal certification process more complex and slower than the open-loop systems used by Visa and Mastercard. As a result, American Express faced unique risks during the transition including rising Card-Not-Present (CNP) fraud, merchant terminal certification delays, and growing merchant acceptance gaps relative to competitors.

---

## Repository Structure

```
enterprise-risk-project/
│
├── README.md
├── requirements.txt
│
├── data/
│   ├── raw/
│   │   └── RiskManagement.xlsx
│   └── processed/
│       └── RiskManagement_updated.xlsx
│
├── notebooks/
│   ├── eda.ipynb
│   ├── qualitative_analysis.ipynb
│   ├── quantitative_analysis.ipynb
│   └── monte_carlo.ipynb
│
└── report/
    └── final_report.pdf
```

---

## Notebooks

| Notebook | Description |
|----------|-------------|
| eda.ipynb | Exploratory data analysis of the risk register including distribution charts, scatter plots, and descriptive statistics |
| qualitative_analysis.ipynb | Qualitative risk assessment including the risk register, severity classification, Random Forest classifier, annotated heat map, and confusion matrix |
| quantitative_analysis.ipynb | Quantitative risk assessment including probability conversion, expected impact calculations, and OCI values for all 6 risks |
| monte_carlo.ipynb | Monte Carlo simulation with 10,000 runs for the 3 priority risks, producing distribution charts and worst case scenario analysis |

---

## Data

The risk register data was constructed based on the American Express EMV chip transition scenario using the risk calculation sheet provided in ALY6130. The dataset contains 6 identified risks across 5 risk categories with likelihood scores, impact scores, and risk scores calculated on a 1 to 81 scale.

| Risk # | Risk Type | Likelihood Score | Impact Score | Risk Score | Priority |
|--------|-----------|-----------------|--------------|------------|----------|
| R-001 | Financial | 7 | 8 | 56 | HIGH |
| R-002 | Operational | 7 | 6 | 42 | MEDIUM |
| R-003 | Competitive | 9 | 8 | 72 | HIGH |
| R-004 | Reputational | 5 | 8 | 40 | MEDIUM |
| R-005 | Legal/Compliance | 7 | 6 | 42 | MEDIUM |
| R-006 | Operational | 7 | 6 | 42 | MEDIUM |

---

## Key Findings

**Three Priority Risks Identified:**

1. R-003 Merchant Acceptance Loss (Competitive, Score 72 HIGH) — Visa and Mastercard deployed EMV terminals faster due to their open-loop networks, creating a widening acceptance gap for American Express cardholders.

2. R-001 Card-Not-Present Fraud (Financial, Score 56 HIGH) — As EMV secured in-store transactions, fraudsters shifted to online channels where chip technology provides no protection.

3. R-002 Terminal Certification Delays (Operational, Score 42 MEDIUM) — Amex closed-loop certification requirements slowed merchant terminal upgrades, leaving merchants exposed to fraud liability.

**Monte Carlo Simulation Results (10,000 runs):**

| Risk | Mean Score | Worst Case (95th Percentile) |
|------|-----------|------------------------------|
| R-003 Merchant Acceptance | 70.56 | 77.81 |
| R-001 CNP Fraud | 56.02 | 64.03 |
| R-002 Terminal Delays | 41.94 | 48.93 |

---

## Tools and Technologies

| Tool | Purpose |
|------|---------|
| Python 3 | Data analysis and modeling |
| pandas | Data manipulation |
| numpy | Numerical calculations |
| matplotlib | Data visualization |
| seaborn | Statistical visualizations |
| scikit-learn | Random Forest classifier and model validation |
| Microsoft Excel | Risk register, heat map, and KRI summary |
| Jupyter Notebook | Interactive analysis environment |

---

## How to Run

1. Clone the repository
2. Install the required libraries by running:
```
pip install -r requirements.txt
```
3. Open Jupyter Notebook and run the notebooks in this order:
   - eda.ipynb
   - qualitative_analysis.ipynb
   - quantitative_analysis.ipynb
   - monte_carlo.ipynb

---

## References

COSO. (2017). Enterprise risk management: Integrating with strategy and performance. Committee of Sponsoring Organizations of the Treadway Commission. https://www.coso.org/guidance-erm

EMV Connection. (n.d.). EMV migration driven by payment brand milestones. https://www.emv-connection.com/emv-migration-driven-by-payment-brand-milestones/

Fitzgerald, K. (2016). Why EMV failed to meet terminal makers' expectations. American Banker. https://www.americanbanker.com/payments/news/why-emv-failed-to-meet-terminal-makers-expectations

Jalilvand, A., & Moorthy, S. (2023). Triangulating risk profile and risk assessment: A case study of implementing enterprise risk management system. Journal of Risk and Financial Management, 16(11), 473. https://doi.org/10.3390/jrfm16110473

Pape, C. (2025). Visa, Mastercard settle merchant suit for nearly $200M. American Banker. https://www.americanbanker.com/payments/news/visa-mastercard-settle-merchant-suit-for-nearly-200m

---

## Course Information

Course: ALY6130 Risk Management Analytics
Institution: Northeastern University
Term: Winter 2026
