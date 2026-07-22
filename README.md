# Global Data Science Survey Analysis | 2017–2021

A reproducible Python analysis of **106,301 Kaggle survey responses** across five annual Machine Learning & Data Science Survey editions, focused on participation, age, gender, geography, professional roles, education, and programming-language preferences.

![Age Group Distribution](images/age-group-distribution.png)

## Executive Snapshot

| KPI | Verified result |
|---|---:|
| Survey editions | **5** |
| Total responses | **106,301** |
| Largest age group | **25–34: 39,892 (37.5%)** |
| Largest country contribution | **India: 25,192 (23.7%)** |
| Largest professional role | **Data Scientist: 17,128** |
| Python recommended first | **66,892 responses** |
| Python regular-use selections | **65,942** |
| SQL regular-use selections | **33,090** |

> Counts across years represent survey responses, not necessarily unique individuals. The survey is voluntary and should not be treated as a census of the global data workforce.

## Analytical Problem

Multi-year survey analysis is difficult because question wording, answer labels, available fields, and respondent composition change between editions. This project addresses:

- Which age groups and countries contributed the most responses?
- Which professional roles appear most frequently?
- Which languages are used and recommended most often?
- How does participation differ by gender and geography?
- What can be compared across years without overstating the evidence?
- Which conclusions require more controlled analysis?

## Dataset Scope

| Year | Responses |
|---|---:|
| 2017 | 16,716 |
| 2018 | 23,859 |
| 2019 | 19,717 |
| 2020 | 20,036 |
| 2021 | 25,973 |
| **Total** | **106,301** |

The source archive is included as `kaggle_survey_2017_2021.zip`. The notebook loads the CSV directly from the ZIP and removes the embedded question-label row.

## Reproducible Workflow

1. Load the source ZIP using a repository-relative path.
2. Remove the survey-question label row.
3. Standardize comparable gender and country labels.
4. Harmonize age bands correctly.
5. Consolidate only clear job-title synonyms while preserving unmatched roles.
6. Count multiple-selection language fields correctly.
7. Build demographic, geographic, role, and language visualizations.
8. Apply explicit interpretation boundaries to salary and participation results.

The revised [Jupyter notebook](Survey_Project.ipynb) has cleared outputs and can be rerun against the published archive.

## Verified Findings

### Age participation

- **25–34** was the largest harmonized age group with **39,892 responses (37.5%)**.
- **18–24** followed with **34,821 responses (32.8%)**.
- Together, these groups accounted for most recorded participation, but this reflects the survey sample—not necessarily the global workforce.

### Geography

- India contributed **25,192 responses (23.7%)**.
- The United States contributed **16,885 responses (15.9%)**.
- China, Russia, Brazil, and Japan were the next largest named country groups.
- Country comparisons measure survey participation and should not be interpreted as national workforce size.

### Professional roles

After preserving original values and consolidating only clear synonyms:

| Role | Responses |
|---|---:|
| Student | 21,242 |
| Data Scientist | 17,128 |
| Software Engineer | 12,473 |
| Data Analyst | 8,509 |
| Research Scientist | 6,968 |
| Business Analyst | 4,112 |
| Machine Learning Engineer | 3,198 |

**Data Scientist**, not Business Analyst, was the largest professional role in the corrected analysis.

### Programming languages

- Python was recommended first in **66,892 responses**.
- Regular-use selections included **65,942 for Python**, **33,090 for SQL**, and **20,884 for R**.
- Regular-use questions allow multiple selections, so these counts do not add to the number of respondents.

### Gender participation

- Among respondents selecting the harmonized binary categories, **82.0% were men** and **18.0% women**.
- Other gender identities and disclosure preferences remain part of the source data but are excluded from this particular two-category percentage.
- This finding describes survey participation, not the gender composition of the entire data profession.

### Defined Arab-country subset

For the explicitly selected countries Egypt, Morocco, Tunisia, Saudi Arabia, United Arab Emirates, Algeria, and Iraq:

- The subset contained **2,292 responses**.
- Egypt led with **945**.
- Women represented **26.4%** of binary gender responses.
- Students represented **497 responses (21.7%)**.

This seven-country subset is not a complete representation of the Arab world.

## Visual Insights

### Age Group Distribution

![Age Group Distribution](images/age-group-distribution.png)

### Top Countries

![Top Countries by Number of Respondents](images/top-countries-by-respondents.png)

### Age by Professional Role

![Age Group by Job Title](images/age-group-by-job-title.png)

### Gender by Professional Role

![Gender Distribution by Job Title](images/gender-distribution-by-job-title.png)

### Top Roles

![Top Job Titles](images/top-job-titles.png)

### Gender Participation

![Gender Distribution](images/gender-distribution.png)

### Age by Gender

![Age Group by Gender](images/age-group-by-gender.png)

## Interpretation and Recommendations

1. Use Python and SQL as broad foundational skills, then specialize by target role.
2. Report annual denominators when discussing trends across survey editions.
3. Preserve original categories and document every harmonization rule.
4. Treat participation gaps as signals for further study, not population estimates.
5. Separate students and employed respondents in career and compensation analysis.
6. Adjust salary comparisons for country, role, experience, education, and year before making pay-equity claims.
7. Avoid causal conclusions from descriptive survey data.

## Documentation

- [Verified KPI reference](docs/kpi-reference.md)
- [Survey harmonization methodology](docs/methodology.md)

These documents explain calculations, corrections, survey limitations, and reproducibility decisions.

## Tools and Skills Demonstrated

- Python and Pandas
- NumPy
- Matplotlib and Seaborn
- Jupyter Notebook
- Multi-year survey harmonization
- Data cleaning and validation
- Exploratory data analysis
- Demographic and workforce analysis
- Evidence-based reporting

## Repository Structure

```text
global-data-science-survey-analysis/
├── README.md
├── Survey_Project.ipynb
├── kaggle_survey_2017_2021.zip
├── docs/
│   ├── kpi-reference.md
│   └── methodology.md
└── images/
    ├── age-group-distribution.png
    ├── top-countries-by-respondents.png
    ├── age-group-by-job-title.png
    ├── gender-distribution-by-job-title.png
    ├── top-job-titles.png
    ├── gender-distribution.png
    └── age-group-by-gender.png
```

## How to Run

1. Clone the repository.
2. Create a Python environment with Pandas, NumPy, Matplotlib, Seaborn, and Jupyter.
3. Start Jupyter from the repository root.
4. Open `Survey_Project.ipynb`.
5. Run all cells; the notebook reads the CSV directly from the included ZIP archive.

## Validation Note

All exact values in this README were recomputed from the published combined CSV after removing the embedded question row. Salary midpoint outputs remain descriptive estimates and are not presented as causal evidence.

## Author

**Yasir Awad**  
Data Analyst | Business Intelligence | Energy & Operations Analytics

- [GitHub](https://github.com/Yasir101-hi)
- [LinkedIn](https://www.linkedin.com/in/yasirawad)
- Email: [yasir.petro.analytics@outlook.com](mailto:yasir.petro.analytics@outlook.com)

## Project Status

Completed and reproducible. Future improvements include year-specific trend tables, question-availability auditing, and controlled compensation analysis.
