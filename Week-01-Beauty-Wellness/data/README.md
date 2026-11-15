# Data

No dataset is committed to this folder yet.

## Dataset selection requirements

Use only a public dataset with a clear licence or a dataset explicitly authorized by the organization. Before analysis, record:
- Dataset name and source URL
- Publisher and licence/terms of use
- Collection or publication date
- Time coverage and number of records
- Relevant fields and their definitions
- Known limitations and data-quality issues

## Proposed minimum fields

A transaction-level dataset should ideally contain an anonymized customer key, order identifier, order timestamp, product/category information, quantity, and transaction value. Discount or engagement fields are optional.

## Privacy and repository hygiene

Do not commit names, email addresses, phone numbers, postal addresses, payment details, credentials, or confidential customer records. Keep raw data out of Git unless the licence and organizational approval explicitly permit redistribution. For any permitted local dataset, document its source and provide reproducible loading instructions.

See the parent project README for the proposed data dictionary and target definition.
