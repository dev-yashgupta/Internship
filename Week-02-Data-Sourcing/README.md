# Week 2 — Data Identification, Sourcing Strategy & Initial Analysis Planning

**Project continuity:** Predicting Repeat Purchases in Online Skincare Retail  
**Stage:** Dataset discovery, source evaluation, acquisition planning and EDA design

## Objective

Identify suitable public datasets and APIs for customer repeat-purchase analysis in beauty and wellness. Evaluate domain fit, identifiers, event/transaction fields, historical coverage, access conditions, licensing, reliability and limitations.

## Main findings

- **Preferred candidate:** [REES46 Cosmetics Shop behavioural events](https://rees46.com/en/datasets), covering a published five-month period (October 2019-February 2020). Its published description lists user/session identifiers, timestamps, product/category, brand, price and event types including view, cart, remove-from-cart and purchase. Confirm the exact downloadable schema, stable user ID, time coverage and licence before using it.
- **Methodological fallback:** [UCI Online Retail II](https://archive.ics.uci.edu/dataset/502/online+retail+ii), a large transaction dataset for a UK giftware retailer. It supports transaction analytics but is not beauty/skincare data.
- **Supplementary context:** Google Trends for aggregated consumer search interest; Open Beauty Facts for product attributes; data.gov.in for Indian macro context where relevant datasets exist.
- **Not a core source:** Reddit discussion data, due to access approvals, policy restrictions, selection bias and lack of verified transaction labels.

## Deliverables

- `report/Week_2_Data_Sourcing_Strategy_Beauty_Wellness.docx` — detailed sourcing and EDA plan
- `data/source_manifest.csv` — source tracking template
- `data/data_dictionary.md` — proposed variable definitions
- `references/source_log.md` — verified source links and limitations
- `notebooks/README.md` — planned first profiling notebook

## Important status note

This is a planning task. No dataset has yet been downloaded and inspected at row level, and no EDA results or model performance are claimed. The next step is to acquire the preferred dataset under its terms and complete the initial quality audit.

## Target construction (planned)

For each eligible customer, calculate features only from data on or before an observation cutoff. Set the target to 1 when at least one qualifying purchase occurs during a subsequent fixed prediction window. Confirm a persistent user identifier and enough post-cutoff data before proceeding. Exclude all post-cutoff information from model features to prevent leakage.
