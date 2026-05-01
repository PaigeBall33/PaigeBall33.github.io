---
layout: page
title: "Module 4: Data Visualization"
permalink: /capstone/module4/
nav: false
---

## Overview

Applied every major chart type across nine labs using Matplotlib and Pandas, each one answering a specific analytical question about developer compensation, job satisfaction, technology preferences, or demographics. Data was loaded both from CSV and directly via a SQLite RDBMS, reinforcing the habit of writing SQL queries before plotting.

**Tools:** Python, Matplotlib, Pandas, SQLite, NumPy, Seaborn

---

## What I Did

- Loaded the 152 MB survey CSV into a persistent SQLite database using sqlite3 and df.to_sql() for efficient querying throughout the module
- Produced all eight major chart types in a single lab: histogram, box plot, scatter plot, bubble plot, pie chart, stacked bar, line chart, and horizontal bar
- Built overlapping multi-group histograms of compensation by age group to compare distributions side-by-side
- Added polynomial regression trend lines using np.polyfit() to surface directional patterns in dense scatter plots
- Built a bubble matrix of programming language popularity by age group with bubble size scaled by respondent count
- Applied IQR outlier removal consistently to all compensation charts so visuals reflect where most developers land
- Compared median compensation by age group with standard deviation overlaid as error bars

---

## Key Findings

The 25–34 cohort represents over 36% of all respondents — nearly double the next-largest group, meaning aggregate findings about language preferences and satisfaction are largely findings about what mid-career developers think. The first decade of experience drives the steepest salary growth; after 10 years the curve levels off significantly. PostgreSQL leads on both current use and desired next year, signaling a sustained shift toward open-source relational databases.

---

## Top 5 Desired Databases

| Rank | Database | Approx. Respondents |
|---|---|---|
| 1 | PostgreSQL | ~24,000 |
| 2 | SQLite | ~13,500 |
| 3 | MySQL | ~12,000 |
| 4 | MongoDB | ~11,000 |
| 5 | Redis | ~11,000 |

---

## Code Highlights

**Loading CSV into a persistent SQLite database:**
```python
import sqlite3
import pandas as pd

df = pd.read_csv('survey-data.csv')

conn = sqlite3.connect('survey-data.sqlite')
df.to_sql('main', conn, if_exists='replace', index=False)
conn.close()

# Verify row count
conn = sqlite3.connect('survey-data.sqlite')
df_check = pd.read_sql_query("SELECT COUNT(*) FROM main", conn)
# Output: 65437
```

**Adding error bars to show compensation variability:**
```python
comp_age = df_clean.groupby('Age')['ConvertedCompYearly'].agg(['median', 'std'])

x = range(len(comp_age))
plt.bar(x, comp_age['median'], color='steelblue',
        edgecolor='black', label='Median Compensation')
plt.errorbar(x, comp_age['median'], yerr=comp_age['std'],
             fmt='none', color='black', capsize=5, label='Std Dev')
```

**Regression trend line on a scatter plot:**
```python
import numpy as np

z = np.polyfit(scatter_df['Age_Numeric'], scatter_df['JobSatPoints_6'], 1)
p = np.poly1d(z)
x_line = np.linspace(scatter_df['Age_Numeric'].min(),
                     scatter_df['Age_Numeric'].max(), 100)

plt.scatter(scatter_df['Age_Numeric'], scatter_df['JobSatPoints_6'],
            alpha=0.3, color='steelblue', edgecolors='none')
plt.plot(x_line, p(x_line), color='red', linewidth=2, label='Trend Line')
```

---

## Skills Demonstrated

Matplotlib and Pandas plotting, SQLite database creation and SQL querying, histograms, box plots, scatter plots, bubble plots, pie charts, stacked bar charts, line charts, bar charts with error bars, IQR outlier removal, trend line fitting with NumPy polyfit, multi-value field exploding, data aggregation with groupby and agg, color mapping, data storytelling with visuals.

[← Back to Capstone Overview](/projects/ibm_capstone/){:.btn}
