\# Data sources



\## Primary source



\- \*\*Dataset:\*\* Stack Overflow Annual Developer Survey, 2025 edition

\- \*\*Publisher:\*\* Stack Exchange Inc.

\- \*\*Official site:\*\* https://survey.stackoverflow.co/2025/

\- \*\*Official repository:\*\* https://github.com/StackExchange/Survey (folder `packages/archive/2025`)

\- \*\*Survey year:\*\* 2025

\- \*\*Downloaded on:\*\* 2026-10-25



\## Files



| File | Source URL | Size (bytes) | SHA-256 |

|---|---|---|---|

| `results.csv` | https://github.com/StackExchange/Survey/raw/refs/heads/main/packages/archive/2025/results.csv | 140,893,245 | `2d1f65308877282edfb4470520eabbc08cb499118432a3dcec6a66c086aa2baa` |

| `schema.csv` | https://github.com/StackExchange/Survey/raw/refs/heads/main/packages/archive/2025/schema.csv | 30,403 | `1d24951e04eab46c6f9fecef6ce8e6b32a0a14a3f0eecdcf62f70833a74b3ff8` |

| `survey.pdf` | https://github.com/StackExchange/Survey/raw/refs/heads/main/packages/archive/2025/survey.pdf | 1,069,269 | not computed (reference document) |



Raw files are stored locally in `data/raw/2025/` and are never committed (see `.gitignore`).



\## License and attribution



\- Data: Open Database License (ODbL) 1.0. Cell contents: Database Contents License (DbCL) 1.0.

\- Cite as: \*Stack Overflow Developer Survey, Stack Exchange Inc.\*

\- This repository does not redistribute the raw data. Derived tables keep the attribution and the license notice.



\## Published reference figures



The survey site reports 49,000+ responses, 177 countries and 62 questions for 2025. These are published figures, to be reconciled against the row counts of the ingested data (not assumed to match).



\## Structure observed on 2026-10-25



\- `results.csv`: 172 columns in the header; first column is `ResponseId`.

\- `schema.csv`: columns `qid`, `qname`, `question`, `type`, `sub`, `sq\_id`; 139 rows when parsed with a CSV parser (the raw line count is higher because some cells span several lines).

\- Question types in the schema: RO 49, MC 48, TE 29, Matrix 13 (codes to be confirmed against `survey.pdf`).

\- Column reconciliation: 126 result columns match a schema `qname` exactly. 13 schema questions are expanded into 44 suffixed columns in `results.csv` (for example `Language` becomes `LanguageHaveWorkedWith`, `LanguageWantToWorkWith`, `LanguageAdmired`; `AITool` becomes five `AITool<status>` columns). Two columns have no schema entry: `ResponseId` (respondent identifier) and `ConvertedCompYearly` (meaning to be verified in the survey methodology before any salary analysis).



\## Known limitations



\- The respondent pool is self-selected, so results describe respondents, not all developers.

\- The meaning of variables across survey years must be checked in the documentation before any 2024 vs 2025 comparison.

\- The encoding of multi-answer columns will be verified on the actual data during ingestion and EDA.

