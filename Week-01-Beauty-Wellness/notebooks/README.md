# Notebooks

This folder is reserved for reproducible Jupyter notebooks.

Suggested sequence:
1. `01_data_audit.ipynb` — inspect the dataset, schema, missingness, duplicates, and time coverage.
2. `02_exploratory_analysis.ipynb` — customer, order, category, recency, frequency, and monetary analysis.
3. `03_feature_engineering.ipynb` — define the observation cutoff and build leakage-safe customer features and target labels.
4. `04_model_baseline.ipynb` — establish a baseline and train initial classification models.
5. `05_model_evaluation.ipynb` — evaluate the held-out test set and document business trade-offs.

Use fixed random seeds where applicable, keep preprocessing inside fitted pipelines, and avoid committing private data or notebook outputs containing personal information.
