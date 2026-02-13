---
----
# Week 5 — Data Preprocessing Workshop Submission (Data Tidying + Cleaning + Outliers)

## Executive Summary (What this notebook delivers)
This workshop submission demonstrates **end-to-end data preprocessing** using two datasets:
- **Cars dataset** → practical **data cleaning + missing value handling (imputation)**  
- **Diabetes dataset** → practical **outlier detection + handling** using **visual + statistical methods**

The notebook is designed to be:
- ✅ **Reproducible** (relative file paths, requirements pinned)
- ✅ **Readable** (strong markdown + clear code intent)
- ✅ **Rubric-aligned** (tidying → cleaning → outliers, with EDA + talking points)
----
---

## Learning Outcomes (What we’re actually learning)
By completing this notebook, we practice the core skills expected in real-world data engineering / ML pipelines:

### 1) Data Tidying (PEW + Billboard sections)
- Understand what “tidy data” means (variables as columns, observations as rows).
- Reshape messy datasets using:
  - `melt()` for long-format transformation
  - `pivot_table()` for structured wide-format outputs
- Clean messy string fields to make data analysis-ready.

### 2) Data Cleaning (Cars dataset)
- Detect messy/invalid records and irrelevant rows.
- Handle missing values responsibly:
  - Drop when truly unusable
  - **Impute** when the signal is valuable (mean/median/mode strategy)
- Validate results so the dataset becomes consistent and model-ready.

### 3) Outlier Detection (Diabetes dataset)
- Use **EDA-first** thinking to *see* anomalies before removing them.
- Detect outliers using:
  - **Box plots / scatter plots** (fast visual scan)
  - **Z-Score** (standard deviation-based detection)
  - **IQR method** (robust thresholding)
- Apply outlier handling in a controlled and explainable way.

---

## EDA (Exploratory Data Analysis) — Talking Points
EDA is the **pre-flight checklist** before any ML or serious analytics.  
It helps you answer:
- What does the data *look like*? (shape, types, missingness)
- How is it *distributed*? (histograms, box plots)
- What values are *suspicious*? (outliers, impossible values)
- How does the outcome relate to key predictors? (scatter/box by Outcome)

#
- “We don’t clean data because it’s messy — we clean it because **models amplify mess**.”
- “EDA helps us find **missingness patterns and outliers** before making assumptions.”
- “Imputation is not guessing; it’s a **controlled data repair strategy**.”
- “Outlier detection isn’t deleting data — it’s **risk management for reliability**.”

---

## Repository Structure
```text
Lab4--Workshop/
│
├── week5Lab_Submission_READY.ipynb        # Final notebook submission
├── requirements.txt                       # Frozen dependencies
├── .gitignore                             # Excludes venv/cache/junk
├── README.md                              # This file
│
└── data/
    ├── cars.csv                           # Cars dataset for cleaning
    └── diabetes.csv                       # Diabetes dataset for outlier detection
````
---
---

## How to Run (Step-by-step, first-time friendly)

### 1) Clone the repository

```bash
git clone https://github.com/SumanthReddyKConestoga/Lab4--Workshop.git
cd Lab4--Workshop
```

### 2) Create a virtual environment

**Windows (PowerShell):**

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
```

**Mac/Linux:**

```bash
python3 -m venv .venv
source .venv/bin/activate
```

### 3) Install dependencies

```bash
pip install -r requirements.txt
```

### 4) Launch Jupyter

```bash
jupyter notebook
```

### 5) Open and Run

Open:

* `week5Lab_Submission_READY.ipynb`

Then run:

* **Kernel → Restart & Run All** ✅

---

## Notes on Paths (Why your notebook runs on any machine)

The notebook uses **relative paths**, not your local absolute path like:
`C:\Users\ksuma\...`

Expected dataset location:

* `./data/cars.csv`
* `./data/diabetes.csv`

As long as the `data/` folder exists in the repo, anyone can run it immediately.

---

## What We’re Doing vs What We’re Achieving (Rubric Proof Table)

| Section           | What We Do                                      | What We Achieve                                            |
| ----------------- | ----------------------------------------------- | ---------------------------------------------------------- |
| PEW Tidying       | Reshape wide ↔ long using `melt()`              | Converts messy survey format into tidy analysis-ready rows |
| Billboard Tidying | Clean strings + restructure weekly ranks        | Converts raw chart logs into usable time-series format     |
| Cars Cleaning     | Handle missing values + remove invalid rows     | Creates consistent dataset suitable for analysis/modeling  |
| Diabetes Outliers | Boxplot + Z-score + IQR detection               | Identifies extreme values and reduces noise for stability  |
| Replicability     | requirements + relative paths + clean structure | Notebook runs on another machine without breaking          |

---

## What to Submit (Submission Format Reminder)

1. Export the notebook to PDF (or print-to-PDF)
2. Inside the PDF, include the repo link:

   * `https://github.com/SumanthReddyKConestoga/Lab4--Workshop.git`
3. Submit PDF to LMS before the deadline.

---

## Closing Note

This notebook reflects real-world preprocessing workflows:

* tidy → validate → clean → impute → detect outliers → document → reproduce
  That pipeline mindset is exactly what separates “code that runs” from “work that ships.”

```

