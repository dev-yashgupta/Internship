# Week 2 — Source Log

Source review recorded: **15 November 2026**. Recheck pages, files, licences and access conditions at acquisition time.

| Source | Intended use | Important limitation | Link |
|---|---|---|---|
| REES46 free eCommerce datasets | Primary candidate for beauty/cosmetics customer event history | Historical fixed period; confirm schema, licence, user ID stability, category coverage | https://rees46.com/en/datasets |
| REES46 Cosmetics Shop Kaggle entry | Dataset-specific file discovery and schema context | Access and platform terms may apply; verify source/attribution | https://www.kaggle.com/datasets/mkechinov/ecommerce-events-history-in-cosmetics-shop |
| UCI Online Retail II | Fallback for transaction and repeat-purchase methodology | Giftware retailer, not beauty/skincare; old data; missing values | https://archive.ics.uci.edu/dataset/502/online+retail+ii |
| UCI Online Retail | Smaller fallback/example for transactional EDA | Giftware retailer, not beauty/skincare | https://archive.ics.uci.edu/dataset/352/online+retail |
| Google Trends | Aggregate search-interest context, e.g. sunscreen, cleanser, niacinamide | Normalized 0-100 sample index; not raw search counts or customer transactions | https://trends.google.com/trends/ |
| Google Trends export instructions | Export CSV and cite the source | UI export available; data must be correctly attributed | https://support.google.com/trends/answer/4365538 |
| Google Trends FAQ | Understand normalization and sampling limitations | Low-volume queries may show 0; sample and noise mean it is not a poll | https://support.google.com/trends/answer/4365533 |
| Google Trends API alpha | Possible programmatic access | Alpha access is limited; do not assume general availability | https://developers.google.com/search/apis/trends |
| Open Beauty Facts | Optional product/ingredient enrichment | Crowdsourced completeness varies; no customer purchase history | https://world.openbeautyfacts.org/data |
| Open Beauty Facts API docs | Determine possible product lookup/enrichment | Verify current endpoint, limits and licence before use | https://openbeautyfacts.github.io/openbeautyfacts-server/api/ |
| data.gov.in | Indian market/demographic/economic context if a relevant dataset is found | Not guaranteed to contain beauty-specific customer purchase data; API key may be required for eligible resources | https://www.data.gov.in/help |
| Reddit Data API / research pathway | Optional qualitative trend/sentiment research only | Access approval and terms apply; not a source of verified transactions | https://support.reddithelp.com/hc/en-us/articles/14945211791892-Developer-Platform-Accessing-Reddit-Data |
| Reddit Data API Terms | Compliance reference | Data use and retention restrictions; permissions may change | https://redditinc.com/policies/data-api-terms |

## Citations

- Chen, D. (2012). *Online Retail II* [Dataset]. UCI Machine Learning Repository. https://doi.org/10.24432/C5CG6D
- Chen, D. (2015). *Online Retail* [Dataset]. UCI Machine Learning Repository. https://doi.org/10.24432/C5BW33

## Verification discipline

The report documents publisher-page descriptions and current platform access notes. It does not claim the candidate data files have been downloaded or profiled. Record actual access date, licence, exact filenames, file size, checksum, columns, rows, date range and missingness after acquisition.
