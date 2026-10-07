# Sales and Marketing Analysis

## Project Overview

This project analyzes a synthetic Sales & Marketing dataset using Google Sheets.

The objective was to practice a complete data analysis workflow, including:

- Data cleaning and validation
- Missing value treatment
- Outlier detection
- Descriptive analysis
- Dashboard creation
- Business-oriented interpretation

The dataset contains approximately **15,000 customer records** and includes demographic, spending, satisfaction and marketing acquisition information.

> The dataset is synthetic and was designed to simulate a CRM / Sales & Marketing environment.

---

## Tools

- Google Sheets
- GitHub

---

## Data Cleaning & Transformation

The original data was preserved and additional **clean** and **flag** columns were created to maintain traceability between the source data and the transformed values.

### Gender

Missing values were classified as `Unknown` in a new `gender_clean` field.

A separate `gender_flag` variable was created to distinguish:

- `Valid`
- `Missing`

This approach allowed the analysis to use a complete categorical variable without overwriting the original data.

---

### Age

The age variable was reviewed to identify missing and potentially invalid observations.

The cleaning process included:

- Missing values
- Values outside the expected range
- Validation flags to differentiate usable and problematic records

The original age values were preserved.

---

### Total Spend

`Total_Spend` was reviewed for missing values and unusually high observations.

Key audit results:

- **1,050 missing values**
- Median spend: approximately **498.84**
- Q1: approximately **300.43**
- Q3: approximately **702.40**
- Maximum observed value: approximately **15,910.43**
- IQR upper threshold: approximately **1,305.34**

High-value observations above the IQR threshold were **flagged rather than removed**, because they could represent legitimate high-value customers.

---

### Satisfaction Score

The `Satisfaction_Score` field was validated and grouped into broader satisfaction levels:

- **Low:** scores 1–2
- **Medium:** score 3
- **High:** scores 4–5
- **Unknown:** missing values

The dataset contained:

- **14,298 valid satisfaction records**
- **702 missing values**

A separate flag was maintained to preserve data-quality traceability.

---

## Data Quality Approach

A dedicated `DATA_AUDIT` section was created in Google Sheets to track:

- Missing values
- Invalid values
- Valid observations
- Outliers
- Transformation rules

The main principles followed during the cleaning process were:

1. Preserve the original data.
2. Avoid overwriting source variables.
3. Create clean and flag variables when necessary.
4. Avoid deleting outliers without business justification.
5. Document each transformation clearly.
6. Automate repetitive transformations using formulas such as `ARRAYFORMULA`.

---

## Descriptive Analysis

The analysis focused on four main business questions:

1. Which customer profiles spend the most?
2. Which acquisition channels are associated with higher customer value?
3. Is there a relationship between satisfaction and spending?
4. How do high-value customers differ from the rest?

The acquisition channels available in the dataset are:

- Organic
- Google Ads
- Facebook Ads
- Referral
- Email

The distribution across channels is unusually balanced, which is one of the main limitations of the dataset.

---

## Dashboard

The final dashboard was structured around the four analysis questions and included:

- Average Spend by Age Group
- Customer Value by Acquisition Channel
- Average Spend by Satisfaction Level
- Top 20% Customer Uplift vs Other Customers
- Summary KPIs

The dashboard was designed to prioritize business questions rather than simply displaying all available variables.

---

## Key Findings

The analysis did not reveal strong differences across most acquisition channels or customer segments.

Main observations:

- Average customer value is relatively similar across acquisition channels.
- Satisfaction levels do not show a strong relationship with spending.
- Differences between demographic groups are limited.
- High-value customers show some uplift compared with the rest, but the separation is not particularly strong.

These results suggest that the synthetic construction of the dataset significantly limits the depth of the commercial insights that can be extracted.

---

## Limitations

The main limitation of this project is the synthetic nature of the dataset.

Several variables show highly balanced distributions, particularly acquisition channels, which is unlikely to reflect the variability normally observed in real-world commercial data.

For this reason, the project should be interpreted primarily as a **data cleaning, validation and dashboarding exercise**, rather than as a source of strong marketing conclusions.

---

## Conclusion

This project provided practical experience in:

- Data cleaning
- Data validation
- Missing value treatment
- Outlier detection
- Descriptive analysis
- Dashboard design
- Documentation of analytical decisions

Although the dataset limited the depth of the business insights, the project was useful for developing a structured analysis workflow in Google Sheets.

The next project will focus on a real-world dataset with greater business variability and stronger analytical value.

---

## Author

**Yamila Anabel Ojeda**  
Data Analytics Portfolio Project
