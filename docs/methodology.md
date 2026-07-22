# Survey Harmonization Methodology

## Purpose

The source combines five annual Kaggle Machine Learning & Data Science Survey editions. Question names, answer labels, and availability vary across years. The analysis therefore focuses on comparable fields and documents every consolidation rule.

## Reproducible Loading

The notebook loads `kaggle_survey_2017_2021.zip` from the repository root, selects the CSV inside the archive, and removes the embedded question-label row. The valid survey years are 2017, 2018, 2019, 2020, and 2021.

## Harmonized Fields

| Field | Method |
|---|---|
| Year | Parsed from the source year column |
| Gender | Male/Man and Female/Woman are consolidated; other responses remain Other |
| Country | Clear naming variants are standardized |
| Age | Original bands are combined into 18–24, 25–34, 35–44, 45–54, and 55+ |
| Job title | Only clear synonyms are consolidated; other labels are preserved |
| Programming language | Multiple-selection fields are counted as selections |
| Recommended language | Single-choice response counts |
| Salary | Reported bands mapped to approximate midpoints for descriptive analysis only |

## Corrected Quality Issues

The earlier notebook:

- loaded data from an author-specific Windows path;
- grouped 25–29 with 18–24 and 30–34 with 36–45;
- used `.map()` for job titles, which converted every unmapped role to missing;
- presented a pie chart of mean salary values as though they were population shares;
- labeled role counts as average salaries;
- made broad workforce and pay-equity claims from unadjusted survey responses.

The revised notebook uses a relative ZIP path, correct age bands, `.replace()` for selective role consolidation, appropriate salary charts, cleared outputs, and bounded interpretations.

## Interpretation Boundaries

- These are voluntary survey responses, not a random sample of the global workforce.
- A respondent may appear in more than one annual survey.
- Counts across years are response totals, not unique-person totals.
- Changing questions can create missingness that differs by year.
- Multiple-selection counts can exceed the number of respondents.
- Cross-country salary comparisons require adjustment for role, experience, year, and purchasing power.
- Gender participation shares do not estimate the gender composition of the entire data workforce.

## Recommended Analytical Extensions

1. Build year-specific trend tables with consistent denominators.
2. Quantify question availability and missingness by year.
3. Model salary midpoint with year, geography, role, experience, education, and gender controls.
4. Separate students from employed respondents in career and compensation analysis.
5. Add uncertainty intervals or sensitivity checks for midpoint-based salary estimates.
