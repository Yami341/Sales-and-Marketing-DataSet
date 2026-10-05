# Sales-and-Marketing-DataSet
Data Analysis para portfolio en Marketing
# Sales and Marketing Analysis

## Project Overview

This project analyzes a synthetic Sales & Marketing dataset using Google Sheets.

The main objective is to practice a complete data analysis workflow, including:

- Data cleaning
- Data validation
- Missing value treatment
- Data quality checks
- Exploratory analysis
- Dashboard creation
- Business-oriented insights

The dataset contains approximately **15,000 customer records** and includes information related to customer demographics, marketing activity, spending behaviour and satisfaction.

> Note: The dataset is synthetic, although it was designed to simulate realistic Sales & Marketing data.

---

## Tools

- Google Sheets
- GitHub

Additional tools will be incorporated in future projects, including SQL, Python and Power BI.

---

## Data Cleaning & Transformation

The original data was preserved whenever possible.

Instead of overwriting original variables, additional **clean** and **flag** columns were created to maintain traceability between the raw and transformed data.

### Gender

Two additional variables were created:

- `gender_clean`
- `gender_flag`

#### `gender_clean`

Missing gender values were replaced with:

`Unknown`

Possible values:

- Male
- Female
- Unknown

This allows missing values to remain visible while still making the variable usable for analysis.

#### `gender_flag`

A separate data-quality flag was created:

- `Valid`
- `Missing`

This makes it possible to distinguish between the cleaned value and the quality of the original record.

The transformation was automated in Google Sheets using `ARRAYFORMULA` so the rule applies automatically to the entire dataset.

---

### Age

Age was reviewed separately to identify data-quality issues before using it in analysis.

Additional fields were created to preserve the original variable while allowing cleaned values and validation rules to be applied.

The process included checking:

- Missing values
- Invalid or unrealistic ages
- Valid observations

An `age_flag` variable was used to classify the quality of the original values.

---

### Total Spend

`Total_Spend` was analyzed to identify missing values and extreme observations.

Summary of the validation:

- Total rows: **15,000**
- Non-missing observations: **13,950**
- Missing values: **1,050**
- Minimum: **0.27**
- Median: **498.84**
- Q1: **300.43**
- Q3: **702.40**
- Maximum: **15,910.43**

The IQR method was used to identify unusually high values.

Upper outlier threshold:

**1,305.34**

High outliers detected:

**79**

Rather than automatically deleting these observations, they were flagged for further analysis.

This avoids removing potentially legitimate high-value customers without understanding their business relevance.

---

### Satisfaction Score

The `Satisfaction_Score` variable was validated and grouped into broader satisfaction levels.

Available observations:

- Valid records: **14,298**
- Missing records: **702**

Distribution:

- Score 1: 753
- Score 2: 1,455
- Score 3: 3,739
- Score 4: 5,323
- Score 5: 3,028

A new variable called `Satisfaction_Level` was created.

Classification:

- **Low:** scores 1–2
- **Medium:** score 3
- **High:** scores 4–5
- **Unknown:** missing values

Result:

- Low: **2,208**
- Medium: **3,739**
- High: **8,351**
- Unknown: **702**

A separate satisfaction flag was also used to preserve information about missing or valid original values.

---

## Data Quality Approach

Throughout the cleaning process, the following principles were applied:

1. Preserve the original raw data.
2. Create cleaned variables instead of overwriting source columns.
3. Use flags to identify missing, invalid or unusual observations.
4. Avoid automatically deleting outliers without business justification.
5. Document every transformation and cleaning decision.
6. Automate repetitive transformations whenever possible.

This approach improves reproducibility and makes the cleaning process easier to audit.

---

## Data Audit

A separate `DATA_AUDIT` section was created in Google Sheets to monitor data quality.

The audit includes:

- Missing values
- Invalid values
- Valid observations
- Outliers
- Distribution checks
- Transformation rules

This provides a clear overview of the quality of the dataset before performing the final analysis.

---

## Dataset Characteristics

The dataset covers approximately:

**January 2022 – March 2025**

Marketing acquisition channels include:

- Organic
- Google Ads
- Facebook Ads
- Referral
- Email

The distribution across acquisition channels is highly balanced.

Because the dataset is synthetic, this balanced distribution should be considered when interpreting marketing performance.

---

## Repository Structure

```text
Sales-and-Marketing-DataSet/
│
├── README.md
│
└── data/
    └── raw/
