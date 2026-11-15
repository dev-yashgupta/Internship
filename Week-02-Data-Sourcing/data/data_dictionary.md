# Proposed Data Dictionary — Repeat Purchase Analysis

**Preferred source candidate:** REES46 Cosmetics Shop behavioural events  
**Important:** Names below are semantic field names from the published dataset description. Verify exact spelling, type, missingness and meaning in the downloaded files before coding. This is not a verified inspection of the raw files.

| Expected field | Meaning | Analytical role | Checks |
|---|---|---|---|
| event_time | Time of user event (described as UTC) | Recency, time ordering, temporal split | Parse timezone, invalid/null dates, coverage |
| event_type | view, cart, remove_from_cart, purchase | Funnel metrics and purchase target | Allowed categories, case, nulls |
| user_id | User identifier | Customer-level grouping | Missingness, stable across sessions |
| user_session | Session identifier | Session and funnel analysis | Nulls, session reuse, boundaries |
| product_id | Product identifier | Product diversity and affinity | Missingness and type consistency |
| category_id / category_code | Product category | Category filtering and preference | Taxonomy and skincare mapping |
| brand | Brand where available | Brand preference | Missingness and alias normalization |
| price | Product/event price | Price distribution and spending proxy | Numeric parsing, currency, zero/negative/outliers |

## Derived analytical features

| Feature | Proposed definition | Leakage rule |
|---|---|---|
| prior_purchase_count | Count of qualifying purchases through cutoff T | Only events at or before T |
| days_since_last_purchase | T minus last qualifying purchase timestamp | Last purchase must be on/before T |
| distinct_product_count | Number of distinct products purchased before T | Only pre-cutoff purchases |
| category_share | Share of prior purchases by category | Use pre-cutoff history |
| session_count | Number of eligible sessions before T | Only pre-cutoff sessions |
| repeat_purchase | 1 if a qualifying purchase occurs in the future prediction window; otherwise 0 | Target only, never an input feature |

## Important feasibility checks

1. Confirm that `user_id` persists across sessions; a session ID alone is not enough for repeat-customer prediction.
2. Confirm that purchase events and event timestamps are present and interpretable.
3. Determine whether multiple purchase events in one session represent individual items or distinct orders.
4. Confirm whether discounts are recorded. If not, Week 1's discount hypothesis cannot be tested with this source.
5. Check whether product categories distinguish skincare from other cosmetics, accessories or beauty-adjacent products.
6. Establish a valid cutoff and future period with full follow-up coverage.
