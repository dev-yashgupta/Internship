# Week 2 — Notebooks

This folder is reserved for the first executable dataset profiling work. The task deliverable is a sourcing plan, so notebooks are planned but not represented as completed analysis.

## Planned notebook

`01_source_profile_and_quality_audit.ipynb`

Suggested sequence:
1. Load the approved dataset from local `data/raw/`.
2. Print dataset shape, columns, dtypes, sample rows and date coverage.
3. Check null counts and null percentages.
4. Summarize event types and unique users, sessions and products.
5. Check duplicates and basic value validity.
6. Plot event counts over time and event-type distribution.
7. Export a source profile and quality issue log into local `outputs/`.

Do not commit raw data or notebook output containing personal information. Preserve raw files and document source version/licence before analysis. All actual row counts and quality metrics should be generated from the downloaded data, not filled in from estimates.
