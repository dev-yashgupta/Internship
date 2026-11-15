# Week 2 — Data

This folder contains data documentation and source-tracking templates. Raw third-party datasets should not be committed unless redistribution is explicitly allowed by their licence and the file size is suitable.

## Files

- `source_manifest.csv`: source provenance, licence, access date, file checksums and limitations.
- `data_dictionary.md`: expected source fields, derived feature definitions and target construction.

## Preferred dataset candidate

REES46 Cosmetics Shop behavioural events: https://rees46.com/en/datasets

Published scope: October 2019-February 2020. Confirm the exact downloaded files, event names, stable user identifier, category coverage, time span and current licence/terms before analysis.

## Data handling

Keep immutable raw files in a local `data/raw/` directory (ignored by Git). Store cleaned, derived tables separately. Do not upload personal data, API keys, credentials, or restricted datasets.
