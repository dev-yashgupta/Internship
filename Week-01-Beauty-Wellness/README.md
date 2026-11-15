# Week 1 — Data Science Orientation & Problem Definition

## Project Title
**Predicting Repeat Purchases in Online Skincare Retail**

**Internship:** Data Science with Python Analyst Internship  
**Domain:** Beauty & Wellness / E-commerce Analytics  
**Project stage:** Business problem definition and proposed analysis plan

## 1. Business Context

Online skincare retailers operate in a competitive market where customers can compare brands, ingredients, product claims, prices, and reviews across multiple channels. Customer retention is therefore an important business concern. A retailer may have transaction histories and customer engagement records, but those records are useful only when converted into reliable insights.

This project proposes analysing historical customer behaviour to estimate which customers are more likely to make another purchase within a defined future period. The output could help a business plan relevant retention campaigns, improve customer experience, and allocate marketing resources more effectively.

## 2. Problem Statement

An online skincare retailer needs a systematic way to understand repeat-purchase behaviour. The project will investigate whether customer transaction history, recency, order frequency, spending patterns, product-category preferences, discount usage, and engagement indicators can help predict whether a customer will make a subsequent purchase within a specified prediction window.

The prediction window, observation period, and definition of a repeat purchase must be fixed before modelling. The proposal does not assume that a model has already been trained or that a particular level of accuracy has been achieved.

## 3. Objectives

1. Understand the business context and customer-retention challenge in online skincare retail.
2. Identify suitable customer, order, product, and engagement variables.
3. Define a repeat-purchase target using a clear observation and prediction window.
4. Plan data cleaning, exploratory data analysis, and feature engineering.
5. Compare suitable classification algorithms if a fit-for-purpose dataset is obtained.
6. Evaluate model performance with metrics appropriate for potentially imbalanced classes.
7. Translate analytical findings into practical, ethical customer-retention recommendations.

## 4. Research Questions

- Which customer and transaction characteristics are associated with repeat purchasing?
- How do purchase recency, frequency, and monetary value relate to future buying behaviour?
- Do product category, basket size, or discount usage provide useful predictive information?
- Can a supervised classification model identify customers more likely to purchase again?
- Which evaluation measures provide the most useful view of model quality for a retention use case?

## 5. Initial Hypotheses

These are hypotheses to test, not findings:

- **H1:** Customers with shorter purchase recency are more likely to purchase again during the prediction window.
- **H2:** Higher historical purchase frequency is positively associated with repeat purchasing.
- **H3:** Customer spending and average order value may contribute predictive information, but their effects may vary by product category.
- **H4:** Discount usage may be associated with repeat purchasing, although the relationship may differ between customers and campaigns.
- **H5:** A model using multiple behavioural features may perform better than a simple baseline model.

## 6. Proposed Data and Variables

| Variable | Meaning | Potential role |
|---|---|---|
| customer_id | Pseudonymous customer identifier | Grouping only; normally excluded from model features |
| order_id | Unique transaction identifier | Deduplication and order counting |
| order_date | Date of transaction | Recency and time-window features |
| product_category | Skincare category purchased | Categorical feature |
| quantity | Units purchased | Behavioural feature |
| order_value | Transaction value | Monetary feature |
| discount_amount | Discount applied | Promotion feature |
| payment_type | Payment method, if authorized | Optional categorical feature |
| website_sessions | Number of sessions, if available | Engagement feature |
| days_since_last_order | Days from observation cutoff to last purchase | Recency feature |
| prior_order_count | Number of historical orders | Frequency feature |
| total_spend | Historical customer spend | Monetary feature |
| repeat_purchase | Purchase within the defined future window | Target label |

**Important:** The listed fields are a proposed schema. Their availability, definitions, collection permissions, and quality must be checked before use. Direct identifiers and sensitive personal information should not be used as model features.

## 7. Proposed Methodology

### Step 1 — Data acquisition and audit
Identify a public, licensed, or organization-authorized transactional dataset. Document its source, licence, time coverage, fields, limitations, and permitted use. Do not scrape or use personal customer data without authorization.

### Step 2 — Define the prediction task
Choose an observation cutoff and a future prediction window. Build the target label only from purchases occurring after the cutoff. Ensure that feature calculations use information available at or before the cutoff to prevent target leakage.

### Step 3 — Data quality checks
Check data types, missing values, duplicate orders, inconsistent category labels, invalid quantities, negative or impossible transaction values, and date ranges. Retain a record of cleaning decisions.

### Step 4 — Exploratory data analysis
Examine order volume over time, customer order frequency, purchase recency, order value distributions, product-category mix, discount usage, and cohort-level repeat-purchase rates. Use summary statistics and clear visualizations.

### Step 5 — Feature engineering
Construct customer-level recency, frequency, monetary value, average order value, category preference, basket-size, and promotion-use features. Consider temporal features only where justified by available data.

### Step 6 — Train, validation, and test design
Split observations by time where possible so that the test period represents future behaviour. Keep all records for a customer within the appropriate split to avoid cross-split leakage. Fit preprocessing steps on training data only.

### Step 7 — Baseline and model development
Start with a simple baseline and Logistic Regression. Compare with Decision Tree and Random Forest models. Use a reproducible pipeline for imputation, encoding, scaling where required, and model fitting. Tune hyperparameters using training/validation data only.

### Step 8 — Model evaluation
Report the confusion matrix, precision, recall, F1-score, ROC-AUC, and PR-AUC as appropriate. Compare against the baseline and explain the trade-off between identifying likely repeat buyers and incorrectly targeting customers. Select a decision threshold based on business costs rather than accuracy alone.

### Step 9 — Interpretation and business recommendations
Review feature importance or suitable model explanations, check subgroup performance where data permits, and convert findings into cautious, actionable recommendations. Predictions should support—not automatically determine—marketing decisions.

### Step 10 — Documentation and reproducibility
Record data provenance, assumptions, cleaning steps, feature definitions, split strategy, random seeds, model configuration, evaluation results, and limitations. Keep code, notebooks, and outputs organized.

## 8. Tools and Technologies

- **Python:** primary programming language
- **Pandas / NumPy:** data manipulation and numerical operations
- **Matplotlib / Seaborn:** exploratory visualizations
- **Scikit-learn:** preprocessing, classification, pipelines, and evaluation
- **Jupyter Notebook:** exploratory and analytical workflow
- **Git / GitHub:** version control and project documentation

## 9. Evaluation Strategy

Accuracy alone can be misleading when repeat and non-repeat classes are imbalanced. The analysis should report precision, recall, F1-score, ROC-AUC, and especially PR-AUC where the positive class is relatively rare. A baseline comparison and a clear decision threshold are required. Results must be calculated from a held-out test set and must not be invented in advance.

## 10. Risks, Ethics, and Limitations

- Dataset availability may limit the scope or representativeness of the analysis.
- Public or synthetic data may not reflect the behaviour of a real retailer's customers.
- Target leakage can produce misleadingly high evaluation scores.
- Customer behaviour and product demand can change over time.
- Personal data must be minimized, protected, and used only with proper authorization.
- Model predictions may reflect historical marketing or access biases.
- Recommendations should not imply medical or dermatological suitability of skincare products.

## 11. Proposed Work Plan (33 Hours)

| Activity | Estimated time |
|---|---:|
| Industry orientation and desk research | 5 hours |
| Business problem and research question definition | 4 hours |
| Dataset search and data dictionary planning | 4 hours |
| Data quality and EDA design | 5 hours |
| Feature engineering and modelling plan | 5 hours |
| Evaluation, risks, and ethical review | 4 hours |
| Documentation and final review | 6 hours |
| **Total** | **33 hours** |

## 12. Expected Deliverables

- A professional Week 1 Word report for internship submission.
- A documented problem statement, research questions, and hypotheses.
- A proposed data dictionary and analysis methodology.
- A structured repository ready for later notebooks, datasets (where permitted), and code.
- A clear list of assumptions, limitations, and next steps.

## 13. Next Steps

1. Confirm the dataset source and licence.
2. Inspect the available columns and establish the prediction window.
3. Create a reproducible exploratory notebook.
4. Validate the target-label construction and time-based split.
5. Implement and evaluate a baseline before comparing advanced models.

## Project Status

**Week 1 status:** Problem definition and analysis proposal documented.  
**Not yet completed:** Dataset validation, exploratory analysis, model training, and empirical evaluation. These activities should be recorded only after they have been performed.

See the `data/`, `notebooks/`, `report/`, and `references/` folders for supporting project notes.
