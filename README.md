# Parkinsons Disease Admissions — Exploratory Data Analysis

An end-to-end exploratory data analysis of **1,199 Parkinson-related neurological admissions** at a Kenyan referral hospital, examining patient demographics, diagnosis patterns, and clinical outcomes.

## Overview

This project analyses hospital admission records for patients presenting with Parkinsons disease and related neurological conditions. The goal is to understand who is being admitted, why, and what happens to them — providing a data-driven picture of the patient population for clinical and public-health decision-making.

## Dataset

- **Raw records:** 1,205 admissions x 13 columns
- **After cleaning:** 1,199 admissions
- **Columns:** `SEX`, `AGE`, `RESIDENT`, `dx 1`-`dx 4` (four diagnosis fields), `Code`-`Code.3`, `OUTCOME`, `DOD` (date of death)
- **Source:** Hospital admission records (Parkinsons Study - Disease cleaned.csv)

## Data Cleaning

The following issues were identified and handled:

| Column | Missing values | Treatment |
|--------|----------------|-----------|
| resident | 9 | Retained as Unknown |
| dx_1 | 16 | Retained as Unknown |
| dx_2 | 431 | Retained as Unknown (multiple diagnoses not always recorded) |
| dx_3 | 802 | Retained as Unknown |
| dx_4 | 1,056 | Retained as Unknown |
| outcome | 5 | Retained as Unknown |
| dod | 248 | Expected — only deceased patients have a date of death |

Additional steps: standardised column names, converted `AGE` to integer, cleaned `OUTCOME` categories, and removed 6 invalid records.

## Key Findings

### Demographics

| Metric | Value |
|--------|-------|
| Total admissions | **1,199** |
| Mean age | **45.7 years** (SD = 21.1) |
| Median age | **42 years** |
| Age range | **12 – 99** |
| Female | **618 (51.5%)** |
| Male | **581 (48.5%)** |

### Age Distribution

| Age Group | Patients | % |
|-----------|----------|---|
| Under 20 | 131 | 10.9% |
| 20 – 39 | **410** | **34.2%** |
| 40 – 59 | 316 | 26.4% |
| 60 – 79 | 249 | 20.8% |
| 80+ | 93 | 7.8% |

### Clinical Outcomes

| Outcome | Patients | % |
|---------|----------|---|
| Discharged | **951** | **79.3%** |
| Died | **227** | **18.9%** |
| Referred | 14 | 1.2% |
| Unknown / Absconded | 2 | 0.2% |
| Missing | 5 | 0.4% |

## Analysis Workflow

1. **Data loading and inspection** — shape, columns, data types, sample rows
2. **Data cleaning** — missing value audit, column standardisation, record validation
3. **Feature engineering:**
   - `age_group` bins (<20, 20–39, 40–59, 60–79, 80+)
   - `outcome_clean` (normalised outcome categories)
   - Neurological keyword tagging on diagnosis text
4. **Descriptive statistics** — age, gender, age-group, and outcome distributions
5. **Objective-driven analysis** — three research objectives explored in sequence
6. **Visualisations** — matplotlib and seaborn charts for each finding

## Project Structure

```
parkinsons-eda/
├── parkinsons_eda.ipynb   # Full analysis notebook
└── README.md
```

## How to Run

```bash
git clone https://github.com/ojwangmaxwell3-ux/parkinsons-eda.git
cd parkinsons-eda
pip install pandas numpy matplotlib seaborn jupyter
jupyter notebook
```

Open `parkinsons_eda.ipynb` and run all cells.

## Tech Stack

Python | Pandas | NumPy | Matplotlib | Seaborn | Jupyter

## Author

**Maxwell Odhiambo**

Actuarial Science Student | Data Science & Artificial Intelligence

- GitHub: [@ojwangmaxwell3-ux](https://github.com/ojwangmaxwell3-ux)
- Email: ojwangmaxwell3@gmail.com
