# Enterprise Risk Analytics: American Express EMV Chip Transition

Research repository for qualitative and quantitative risk assessment of American Express’s U.S. EMV chip card transition—covering fraud displacement, merchant acceptance, terminal certification, and related competitive and legal exposure.

---

## Abstract

The EMV liability shift (effective October 2015 in the U.S.) reduced card-present counterfeit fraud but redistributed risk: Card-Not-Present (CNP) fraud rose, merchants faced certification friction, and closed-loop networks introduced distinct timing and acceptance dynamics versus open-loop schemes. This work builds a structured risk register, applies expected-value style scoring, trains a Random Forest model for risk-type classification, and runs Monte Carlo simulation on priority risks to characterize distributional outcomes and tail scenarios.

---

## Context

American Express operates a closed-loop network (issuer and network under one umbrella), which shaped EMV terminal certification paths and merchant onboarding relative to Visa and Mastercard. The analysis treats documented industry patterns—CNP migration post-EMV, terminal-maker constraints, and merchant-network litigation—as empirical anchors for likelihood and impact judgments encoded in the register.

---

## Repository layout

```
enterprise-risk-project/
├── requirement.txt
├── data/
│   ├── raw/
│   │   └── risk_inputs_raw.xlsx
│   └── processed/
│       ├── risk_register_updated.xlsx
│       └── probability_impact.xlsx
├── notebooks/
│   ├── eda.ipynb
│   ├── qualitative_risk_register.ipynb
│   ├── quantitative_risk_analysis.ipynb
│   └── monte_carlo_simulation.ipynb
└── report/
    ├── Risk_Mitigation_Summary.docx
    └── Integrated_Risk_Assessment.docx
```

---

## Notebooks

| Notebook | Focus |
|----------|--------|
| `eda.ipynb` | Exploratory views of the risk register |
| `qualitative_risk_register.ipynb` | Register construction, severity views, Random Forest classifier, confusion matrix |
| `quantitative_risk_analysis.ipynb` | Quantitative scoring and Monte Carlo framing |
| `monte_carlo_simulation.ipynb` | Simulation draws, distributions, stress-style summaries |

---

## Data

The register encodes six risks across financial, operational, competitive, reputational, and legal/compliance categories, with likelihood and impact scores combined into composite risk scores (1–81 scale). Workbooks live under `enterprise-risk-project/data/`.

| Risk ID | Type | Likelihood | Impact | Score | Priority |
|---------|------|------------|--------|-------|----------|
| R-001 | Financial | 7 | 8 | 56 | High |
| R-002 | Operational | 7 | 6 | 42 | Medium |
| R-003 | Competitive | 9 | 8 | 72 | High |
| R-004 | Reputational | 5 | 8 | 40 | Medium |
| R-005 | Legal/Compliance | 7 | 6 | 42 | Medium |
| R-006 | Operational | 7 | 6 | 42 | Medium |

---

## Selected results

**Priority risks (illustrative):**

1. **R-003 — Competitive / merchant acceptance** — Score 72 (high): acceptance gaps versus faster EMV rollouts on open-loop networks.  
2. **R-001 — Financial / CNP fraud** — Score 56 (high): fraud displacement to online channels post-EMV.  
3. **R-002 — Operational / terminal certification** — Score 42 (medium): certification friction under closed-loop constraints.

**Monte Carlo (10,000 runs, reported in notebook outputs):**

| Risk | Mean score | ~95th percentile |
|------|------------|------------------|
| R-003 | 70.56 | 77.81 |
| R-001 | 56.02 | 64.03 |
| R-002 | 41.94 | 48.93 |

---

## Environment

| Component | Role |
|-----------|------|
| Python 3 | Analysis runtime |
| pandas, numpy | Tabular data and numerics |
| matplotlib, seaborn | Visualization |
| scikit-learn | Random Forest and validation |
| Jupyter | Notebook workflow |

**Setup**

```bash
pip install -r enterprise-risk-project/requirement.txt
```

Run notebooks from `enterprise-risk-project/notebooks/` (adjust paths to `data/` as needed).

---

## References

COSO. (2017). *Enterprise risk management: Integrating with strategy and performance.* Committee of Sponsoring Organizations of the Treadway Commission. https://www.coso.org/guidance-erm

EMV Connection. (n.d.). EMV migration driven by payment brand milestones. https://www.emv-connection.com/emv-migration-driven-by-payment-brand-milestones/

Fitzgerald, K. (2016). Why EMV failed to meet terminal makers’ expectations. *American Banker.* https://www.americanbanker.com/payments/news/why-emv-failed-to-meet-terminal-makers-expectations

Jalilvand, A., & Moorthy, S. (2023). Triangulating risk profile and risk assessment: A case study of implementing enterprise risk management system. *Journal of Risk and Financial Management*, 16(11), 473. https://doi.org/10.3390/jrfm16110473

Pape, C. (2025). Visa, Mastercard settle merchant suit for nearly $200M. *American Banker.* https://www.americanbanker.com/payments/news/visa-mastercard-settle-merchant-suit-for-nearly-200m
