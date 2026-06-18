# Pionex Data Cleaning Workflow

## Project Overview

This project demonstrates a reproducible and modular data cleaning workflow for the Pionex dataset using Python and Jupyter Notebook.

The objective of the project is not only to produce a cleaned dataset, but also to demonstrate best practices in data preparation, workflow automation, logging, version control, and data quality validation.

The notebook is designed to run from start to finish with minimal manual intervention and follows a structured cleaning pipeline.

---

## Project Structure

```text
pionex-cleaning-project/

├── pionex_cleaning_script_AK.ipynb
├── README.md
├── .gitignore

├── records/
│   ├── raw/
│   ├── processed/
│   ├── garbage/
│   └── to-be-ingested/

└── logs/
```

---

## Required Libraries

The following Python libraries are used:

* pandas
* os
* logging
* re

Install dependencies using:

```bash
pip install pandas openpyxl
```

---

## Workflow

The notebook follows the workflow below:

1. Imports & Environment Setup
2. Folder Structure Creation
3. Logging Configuration
4. Dataset Loading
5. Pre-Cleaning Analysis
6. Data Cleaning
7. Garbage File Generation
8. Post-Cleaning Analysis
9. Row Reconciliation
10. Final Export

---

## Cleaning Activities Performed

The following cleaning operations were completed:

* Standardized column names
* Removed unnecessary columns:

  * Lang
  * RegistrationDate
  * BrandCode
* Removed records with missing email addresses
* Removed records with missing first names
* Checked for duplicate records
* Generated garbage files for removed data
* Validated row counts through reconciliation
* Exported cleaned dataset for ingestion

---

## Outputs

### Processed Files

Versioned datasets are stored in:

```text
records/processed/
```

Example:

```text
pionex_v1.csv
pionex_v2.csv
pionex_v3.csv
```

### Garbage Files

Removed records and discarded information are stored in:

```text
records/garbage/
```

Examples:

```text
pionex_removed_columns.csv
pionex_missing_email.csv
pionex_missing_first_name.csv
```

### Final Dataset

The final cleaned dataset is exported to:

```text
records/to-be-ingested/
```

Example:

```text
pionex_cleaned.csv
```

### Logs

Execution logs are written to:

```text
logs/pionex_cleaning.log
```

---

## Data Quality Summary

Original Records: 241,933

Records Removed:

* Missing Email: 1
* Missing First Name: 20

Final Records: 241,912

Duplicate Records Remaining: 0

Records with missing last names were retained to avoid unnecessary data loss and were documented during post-analysis.

---

## Running the Notebook

1. Open the notebook in VS Code or Jupyter Notebook.
2. Ensure the raw dataset is located in:

```text
records/raw/
```

3. Select **Run All**.
4. The workflow will:

   * Create required folders
   * Load the dataset
   * Execute cleaning steps
   * Generate garbage outputs
   * Perform validation checks
   * Export the final cleaned dataset

The notebook is designed to execute from start to finish without requiring manual intervention.
