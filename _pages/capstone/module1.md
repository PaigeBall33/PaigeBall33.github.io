---
layout: page
title: "Module 1: Data Collection"
permalink: /capstone/module1/
nav: false
---

## Overview

Gathered data on in-demand programming skills from two sources: a job postings API and web scraping. All work done in Jupyter Notebook using Python.

**Tools:** Python, Requests, BeautifulSoup, Pandas, openpyxl, csv

---

## What I Did

- Connected to a JSON job postings endpoint containing 27,005 records and built functions to query by skill and location
- Looped through 12 technologies and exported results to Excel using openpyxl
- Scraped the IBM.com homepage extracting 35 hyperlinks and 12 image URLs using BeautifulSoup
- Scraped an HTML table of programming language salaries and exported to CSV
- Loaded the Stack Overflow Developer Survey (65,457 rows × 117 columns) and engineered an Age_midpoint column using regex, finding a mean respondent age of 32.6 years across 185 unique countries

---

## Key Findings

C had the highest job posting count at 25,114 — nearly seven times Java's 3,428. Despite lower current demand, Python ranked second in average annual salary at $114,383, trailing only Swift at $130,801. The dataset contained 185 unique countries, establishing the global scope of the survey from the first lab.

---

## Job Postings by Technology

| Technology | Job Count |
|---|---|
| C | 25,114 |
| Java | 3,428 |
| JavaScript | 2,248 |
| Python | 1,173 |
| MySQL | 952 |
| Oracle | 899 |
| C# | 526 |
| SQL Server | 423 |
| MongoDB | 208 |
| PostgreSQL | 86 |

---

## Average Annual Salary by Language

| Language | Average Annual Salary |
|---|---|
| Swift | $130,801 |
| Python | $114,383 |
| C++ | $113,865 |
| JavaScript | $110,981 |
| Java | $101,013 |
| Go | $94,082 |
| R | $92,037 |

---

## Code Highlights

**API data collection and querying:**
```python
def count_jobs_for_skill(data, skill):
    count = 0
    for job in data:
        skills = job.get("Key Skills", "")
        if skill.lower() in skills.lower():
            count += 1
    return count
```

**Exporting results to Excel:**
```python
from openpyxl import Workbook

technologies = ["C", "C#", "C++", "Java", "JavaScript", "Python",
                "Scala", "Oracle", "SQL Server", "mysql", "PostgreSQL", "MongoDB"]

workbook = Workbook()
sheet = workbook.active
sheet.append(["Technology", "Job Count"])

for tech in technologies:
    job_count = count_jobs_for_skill(jobs_data, tech)
    sheet.append([tech, job_count])

workbook.save("job-postings.xlsx")
```

**Age feature engineering with regex:**
```python
df['Age'] = df['Age'].astype(str)
df[['Age_start', 'Age_end']] = df['Age'].str.extract(r'(\d+)\D+(\d+)')
df['Age_start'] = pd.to_numeric(df['Age_start'], errors='coerce')
df['Age_end']   = pd.to_numeric(df['Age_end'],   errors='coerce')

mask_ranges = df['Age_start'].notna() & df['Age_end'].notna()
df.loc[mask_ranges, 'Age_midpoint'] = (
    df.loc[mask_ranges, 'Age_start'] + df.loc[mask_ranges, 'Age_end']
) / 2

print("Mean age:", df['Age_midpoint'].mean())  # 32.60
```

---

## Skills Demonstrated

REST API integration and JSON parsing, web scraping with BeautifulSoup, data export to Excel and CSV, dataset profiling with Pandas, feature engineering with regex and NumPy.

[← Back to Capstone Overview](/projects/ibm_capstone/){:.btn}
