---
layout: page
title: "Module 2: Data Wrangling"
permalink: /capstone/module2/
nav: false
---

## Overview

Cleaned and prepared the Stack Overflow Developer Survey dataset by identifying and handling duplicate entries, detecting and imputing missing values, normalizing compensation data, encoding categorical variables, and engineering new features.

**Tools:** Python, Pandas, NumPy, Matplotlib, Seaborn

---

## What I Did

- Detected 20 fully duplicate rows and analyzed partial duplicates by grouping on key demographic columns
- Removed duplicates strategically based on 5 critical columns, reducing the dataset from 65,457 to 4,748 rows
- Identified missing values across all 114 columns — 109 columns had at least some missing data
- Imputed EdLevel (4,653 missing) using the mode and ConvertedCompYearly (42,002 missing) using the median ($65,000)
- Applied Min-Max Scaling and Z-score Normalization to compensation data
- Mapped verbose EdLevel strings to concise labels and applied one-hot encoding to Employment using pd.get_dummies()
- Engineered an ExperienceLevel feature from YearsCodePro using a custom binning function

---

## Key Findings

After imputation, the median annual compensation across all respondents was $65,000 with a mean of $72,576, reflecting significant right skew driven by extreme outliers (max $16,256,600). The Check column was identical in 100% of duplicate groups, confirming it as a reliable deduplication key. Hybrid remote work was the most common work arrangement with 23,015 respondents, narrowly ahead of fully remote at 20,831.

---

## Top Columns by Missing Percentage

| Column | Missing Count | Missing % |
|---|---|---|
| AINextMuch less integrated | 64,289 | 98.25% |
| AINextLess integrated | 63,082 | 96.40% |
| AINextNo change | 52,939 | 80.90% |
| ConvertedCompYearly | 42,002 | 64.19% |
| EdLevel | 4,653 | 7.11% |

---

## EdLevel After Standardization

| EdLevel | Count |
|---|---|
| Bachelor's | 24,942 |
| Master's | 15,557 |
| Some College | 7,651 |
| Secondary School | 5,793 |
| Professional Degree | 2,970 |

---

## Code Highlights

**Duplicate detection and removal:**
```python
duplicate_count = df.duplicated().sum()
print("Number of duplicate rows:", duplicate_count)  # 20

critical_columns = ["MainBranch", "Employment", "RemoteWork", "Age", "EdLevel"]
df_cleaned = df.drop_duplicates(subset=critical_columns, keep="first")
print("After deduplication:", df_cleaned.shape[0])  # 4748
```

**Missing value imputation:**
```python
most_frequent_edlevel = df['EdLevel'].mode()[0]
df['EdLevel'] = df['EdLevel'].fillna(most_frequent_edlevel)

median_comp = df['ConvertedCompYearly'].median()
df['ConvertedCompYearly'] = df['ConvertedCompYearly'].fillna(median_comp)
```

**Min-Max and Z-score normalization:**
```python
col_min = df['ConvertedCompYearly'].min()
col_max = df['ConvertedCompYearly'].max()
df['ConvertedCompYearly_MinMax'] = (df['ConvertedCompYearly'] - col_min) / (col_max - col_min)

mean_comp = df['ConvertedCompYearly'].mean()
std_comp  = df['ConvertedCompYearly'].std()
df['ConvertedCompYearly_Zscore'] = (df['ConvertedCompYearly'] - mean_comp) / std_comp
```

**Custom experience level binning:**
```python
def assign_experience_level(years):
    if pd.isnull(years):   return 'Unknown'
    elif years < 3:        return 'Junior'
    elif years < 7:        return 'Mid-level'
    elif years < 15:       return 'Senior'
    else:                  return 'Expert'

df['ExperienceLevel'] = df['YearsCodePro'].apply(assign_experience_level)
```

---

## Skills Demonstrated

Duplicate detection with groupby analysis, strategic subset-based deduplication, missing value profiling and imputation using mode, median, and forward-fill, Min-Max Scaling and Z-score Normalization, log transformation, categorical standardization, one-hot encoding, feature engineering with custom binning functions.

[← Back to Capstone Overview](/projects/ibm_capstone/){:.btn}
