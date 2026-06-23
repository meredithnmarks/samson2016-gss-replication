# Samson (2016) — GSS 2012 replication

TL;DR: Reproduces Samson (2016) analyses on GSS 2012 and produces the replication report and tables (see replication_report.pdf / replication_tables.pdf).

Badges: (CI / renv / badges — optional)

Why this repo
- Reproduces the principal analyses and tables from Samson (2016) using the 2012 General Social Survey (GSS).
- Demonstrates an end-to-end reproducible research workflow in R: data preparation, principled missing-data handling, variable construction, modeling, and report outputs.

Methods used
- Data wrangling and feature engineering with dplyr for reproducible, pipe-based transforms
- Multiple imputation (predictive mean matching) using mice to address missingness robustly
- Variable scaling and composite score construction for interpretable effect sizes
- Linear regression (OLS) and ordinal logistic regression with model diagnostics and comparison across specifications
- Reproducible pipeline automation via Rscript and Makefile (driver script installs dependencies when needed)

Quick start (from repo root)
1. Obtain the GSS 2012 data per the GSS terms and save it at the repository root:
   - Filename: `gss2012.RDS`
2. Reproduce the full analysis:
```
make reproduce
# or
Rscript reproduce.R
```
3. Clean generated artifacts:
```
make clean
```

What’s included
- `code/` — sequential R scripts implementing the pipeline (01 → 10)
- `reproduce.R`, `Makefile` — driver and convenience commands to install missing packages and run the pipeline
- `replication_report.pdf`, `replication_tables.pdf` — replication outputs (report and tables)
- `Samson2016_originalpaper.pdf` — original paper (for reference)

Script flow (high level)
1. `01` — load GSS 2012 and subset variables
2. `02–04` — recoding, missing-value diagnostics, and table-1 variable creation
3. `05` — descriptive analyses
4. `06` — multiple imputation with `mice`
5. `07` — scaling / variable transforms
6. `08–10` — produce tables and run OLS / OLR models

Requirements
- R >= 4.4.2 (tested)
- Required packages: `dplyr`, `mice`, `ordinal` (the driver will install missing packages)
- The GSS 2012 data file is not included in this repository; obtain it separately and place it as `gss2012.RDS` in the repository root before running.

Expected outputs
- `.RDS` intermediate files (mmarks9-PDIR-*.RDS)
- `.log` files for each script (one per script)
- `replication_report.pdf` and `replication_tables.pdf` (final outputs / included)

Contact & citation
- Meredith Marks — https://github.com/meredithnmarks
- Cite: Samson (2016). This repository: meredithnmarks/samson2016-gss-replication

Next improvements (I can add)
- Add `renv` and commit a lockfile to pin package versions for reproducibility
- Add a GitHub Actions workflow to run a smoke-check (or conditional reproduce)
- Add an R Markdown that re-assembles the final report from model outputs
- Add repository badges and an explicit `LICENSE` if desired
