---
layout: page
title: "Module 3: Exploratory Data Analysis"
permalink: /capstone/module3/
nav: false
---

## Overview

Performed in-depth EDA on the cleaned Stack Overflow survey dataset, examining data distributions, identifying outliers using statistical methods, and measuring correlations between key variables including compensation, experience, and job satisfaction.

**Tools:** Python, Pandas, NumPy, Matplotlib, Seaborn

---

## What I Did

- Binned YearsCodePro into four experience ranges and calculated median job satisfaction per range
- Analyzed remote work preferences by employment type using pd.crosstab() — full-time employees showed the strongest hybrid preference
- Exploded the semicolon-delimited LanguageHaveWorkedWith column and visualized as an annotated heatmap across top 5 countries and top 10 languages
- Identified outliers using both the 3-standard-deviations method (89 outliers above $646,426) and the IQR method (978 outliers above $220,861)
- Removed IQR outliers reducing the dataset from 65,437 to 22,457 rows
- Computed Pearson correlation between ConvertedCompYearly and WorkExp (r = 0.407) and between compensation and JobSatPoints_1 (r = −0.060)

---

## Key Findings

Median job satisfaction was uniformly 8/10 across all experience ranges, suggesting experience level has no meaningful impact on developer satisfaction. Work experience moderately predicts compensation (r = 0.407), but salary has essentially no relationship with job satisfaction (r = −0.060). Age and professional experience are very strongly correlated (r = 0.82), confirming they move together across the career arc.

---

## Correlation Matrix (Post-IQR Removal)

| | Age | YearsCodePro | ConvertedCompYearly |
|---|---|---|---|
| Age | 1.0000 | 0.8201 | 0.3588 |
| YearsCodePro | 0.8201 | 1.0000 | 0.3869 |
| ConvertedCompYearly | 0.3588 | 0.3869 | 1.0000 |

---

## Code Highlights

**Outlier detection using IQR:**
```python
Q1, Q3 = comp_data.quantile(0.25), comp_data.quantile(0.75)
IQR = Q3 - Q1
lower_bound = Q1 - 1.5 * IQR
upper_bound = Q3 + 1.5 * IQR
df_clean = df[(df['ConvertedCompYearly'] >= lower_bound) &
              (df['ConvertedCompYearly'] <= upper_bound)].copy()
print("Cleaned rows:", df_clean.shape[0])  # 22,457
```

**Exploding multi-value columns for heatmap:**
```python
lang_df = df_filtered[['Country', 'LanguageHaveWorkedWith']].dropna()
lang_df = lang_df.assign(
    Language=lang_df['LanguageHaveWorkedWith'].str.split(';')
).explode('Language')
lang_df['Language'] = lang_df['Language'].str.strip()

lang_country = lang_df.groupby(['Country', 'Language']).size().unstack(fill_value=0)
sns.heatmap(lang_country, cmap='YlGnBu', annot=True, fmt='d')
```

**Pearson correlation matrix:**
```python
corr_df = df_clean[['ConvertedCompYearly', 'WorkExp', 'JobSatPoints_1']].dropna()
corr_matrix = corr_df.corr(method='pearson')
sns.heatmap(corr_matrix, annot=True, fmt='.4f', cmap='coolwarm', square=True)
```

---

## Skills Demonstrated

Full EDA pipeline, exploding multi-value semicolon-delimited columns, cross-tabulation with pd.crosstab(), outlier detection using 3-standard-deviations and IQR methods, Pearson correlation matrix computation and interpretation, segmented analysis filtering and comparing subgroups, visualization suite including KDE plots, annotated heatmaps, box plots, and regression scatter plots.

[← Back to Capstone Overview](/projects/ibm_capstone/){:.btn}
