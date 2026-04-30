# Machine Learning and Survival Analysis
> Predicting customer churn using logistic regression, random forest classification, and survival analysis

**Author:** Patrick Lefler

**Published:** February 17, 2026

**Rendered:** https://patrick-lefler.github.io/rQuarto_machine_learning_survival_analysis_2026-02-17/

---

## Predicting Credit Card Customer Attrition

A data science framework for identifying, scoring, and acting on customer attrition risk within a consumer credit card division. Using over 10,000 anonymized account records, the analysis moves from behavioral pattern recognition to a ranked tactical outreach list — enabling retention teams to intervene before an account closes, not after.

---

## Overview

This project applies three complementary statistical methods to the problem of credit card attrition. Logistic regression isolates the behavioral and demographic factors that most strongly predict departure, expressed as interpretable Risk Multipliers. A Random Forest classifier then scores every active account on an individual churn probability, ranked for operational use. Finally, Kaplan-Meier survival analysis maps the customer lifecycle to identify the tenure milestones where attrition risk concentrates — in this case, a pronounced drop-off at the 36-month mark. The combined output shifts the retention function from reactive case management to proactive, data-driven intervention.

---

## Tech Stack

- **Language:** R
- **Framework:** [Quarto](https://quarto.org/)
- **Primary Libraries:** tidyverse, tidymodels, survival, survminer, ranger, vip, ggplot2, kableExtra, patchwork, plotly, formattable, readxl
- **Deployment / Output:** Self-contained HTML Document

---

## Repository Structure

```
├── data/               # Raw account data (bank_attrition_data.xlsm)
├── scripts/            # Helper R scripts
├── models/             # Saved model objects (.rds)
├── output/             # Rendered HTML file
├── _brand.yml          # Brand color and typography configuration
└── project.qmd         # Main Quarto entry point
```

---

## Key Findings

**Behavioral drift, not demographics, drives attrition.** The Random Forest model's top predictors are transaction velocity measures — total transaction count, total transaction amount, and quarter-over-quarter change in transaction volume. Demographic variables including age, gender, and income rank substantially lower in predictive importance. A customer who stops using their card is signaling departure months before they formally close the account.

**Age brackets amplify risk in the logistic model.** Customers aged 40–59 carry Risk Multipliers exceeding 13x relative to the baseline cohort — a finding that appears to conflict with the Random Forest's low importance score for age as a continuous variable. The discrepancy likely reflects a nonlinear, threshold effect that the logistic model captures through indicator variables but that the forest absorbs into other correlated features. Further investigation is warranted.

**The 36-month tenure mark is a structural risk event.** The Kaplan-Meier survival curve holds relatively flat through the first three years, then drops sharply. This pattern is consistent with promotional or introductory incentives expiring at the three-year anniversary. Automated lifecycle interventions timed to this window represent the clearest near-term retention opportunity.

---

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.

---

## Contact

Patrick Lefler — [LinkedIn](https://www.linkedin.com/in/patricklefler/) | [Portfolio](https://patrick-lefler.github.io) | [Substack](https://substack.com/@pflefler)
