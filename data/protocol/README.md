# Protocol Files

- `coding_guide.md`: column guide for `../raw/taxonomy_mapping.csv`.
- `exclusion_log.csv`: excluded records with raw quality signals preserved (`h5_index`, `quartile`).
- `secondary_studies.csv`: the 10 retained secondary studies that informed survey positioning but were excluded from the final primary-study corpus.
- `scopus_sensitivity_check_summary.csv`: post hoc Scopus sensitivity-check summary used in the rebuttal.
- `scopus_sensitivity_exports/`: raw Scopus CSV exports backing the sensitivity-check summary.
- `journals_venue_review_log.csv`: row-level review decisions for journal records.
- `conferences_venue_review_log.csv`: row-level review decisions for conference records.
- `unranked_venue_review_log.csv`: row-level review decisions for unranked venues.

For the Scopus sensitivity materials, the reported `result_count` values are derived from the per-year totals in the raw Scopus CSV exports.

The tables below summarize the paper's staged screening process, showing the cumulative status after each stage for journals, conferences, and unranked records.

## 1. Title Screening

| Source | Include | Maybe include | Do not include | Total |
| --- | ---: | ---: | ---: | ---: |
| Journal log | 40 | 107 | 1011 | 1158 |
| Conference log | 16 | 42 | 500 | 558 |
| Unranked log | 83 | 119 | 1721 | 1923 |
| Total | 139 | 268 | 3232 | 3639 |

## 2. Title + Abstract + Keywords

| Source | Include | Maybe include | Do not include | Total |
| --- | ---: | ---: | ---: | ---: |
| Journal log | 59 | 0 | 1099 | 1158 |
| Conference log | 24 | 0 | 534 | 558 |
| Unranked log | 119 | 0 | 1804 | 1923 |
| Total | 202 | 0 | 3437 | 3639 |

## 3. Quality Check

| Source | Include | Maybe include | Do not include | Total |
| --- | ---: | ---: | ---: | ---: |
| Journal log | 59 | 0 | 1099 | 1158 |
| Conference log | 18 | 0 | 540 | 558 |
| Unranked log | 56 | 0 | 1867 | 1923 |
| Total | 133 | 0 | 3506 | 3639 |

## 4. IDS vs NIDS

| Source | Include | Maybe include | Do not include | Total |
| --- | ---: | ---: | ---: | ---: |
| Journal log | 52 | 0 | 1106 | 1158 |
| Conference log | 16 | 0 | 542 | 558 |
| Unranked log | 53 | 0 | 1870 | 1923 |
| Total | 121 | 0 | 3518 | 3639 |

## 5. Public Access

| Source | Include | Maybe include | Do not include | Total |
| --- | ---: | ---: | ---: | ---: |
| Journal log | 52 | 0 | 1106 | 1158 |
| Conference log | 16 | 0 | 542 | 558 |
| Unranked log | 50 | 0 | 1873 | 1923 |
| Total | 118 | 0 | 3521 | 3639 |

## Taxonomy Mapping Status By Source

| Source | Final primary studies | Final secondary studies | Not selected |
| --- | ---: | ---: | ---: |
| Journal log | 42 | 5 | 1111 |
| Conference log | 11 | 2 | 545 |
| Unranked log | 41 | 3 | 1879 |
| Total | 94 | 10 | 3535 |
