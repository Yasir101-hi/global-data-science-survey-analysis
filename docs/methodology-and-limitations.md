# Methodology and limitations

## Unit of analysis

One row represents one submitted survey response. The first data row in the supplied CSV contains question descriptions, not a respondent, and is excluded.

Source dataset: https://www.kaggle.com/datasets/andradaolteanu/kaggle-data-science-survey-20172021

## Time coverage

The file contains records for 2017, 2018, 2019, 2020, and 2021.

## Harmonization

- Gender labels were standardized across questionnaire wording changes.
- Programming-language multi-select fields were converted to a year-language table. Shares use all respondents in that year as the denominator.
- The merged file has no regular-use language multi-select values for 2017, so language usage trends begin in 2018.
- Known Excel-style date conversions in team-size categories were repaired (`2-Jan` → `1-2`, `4-Mar` → `3-4`, `9-May` → `5-9`, `14-Oct` → `10-14`).
- Mojibake such as `Bachelorâ€™s` was decoded where safely identifiable.

## Comparability

The questionnaire changed between years. A missing answer can mean respondent non-response, skip logic, or that the question was not asked. Therefore, this project does not interpret missing values as negative answers and avoids trends on fields whose meaning changed materially.

## Interpretation

The findings are descriptive and reflect Kaggle's voluntary respondent pool. They are not population estimates and should not be used to claim causal relationships.
