## Overview
This document contains essential information for participating in the quantitative market research portion of **QuantChallenge 2025**, including rules, dataset structure, and scoring details.

## Rules Reminder
- Ensure the **Sylvian extension** is enabled at all times: https://marketplace.visualstudio.com/items?itemName=SylvianAI.sylvian
- Without the Sylvian extension, you will not be eligible for prizes.

## Dataset
Two CSV files are provided: **train.csv** and **test.csv**. The data represent time-series, with test events occurring strictly after train events.

### Training Data (train.csv)
- **Columns**: 17 columns (`time`, `A`–`N`, `Y1`, `Y2`)
- **Rows**: 80,000
- **Features**: `time` and columns `A` through `N` (anonymized real market features)
- **Targets**: `Y1` and `Y2` (variables to predict)

### Test Data (test.csv)
- **Columns**: 16 columns (`id`, `time`, `A`–`N`)
- **Rows**: 15,996
- **ID Column**: `id` appears only in the test set; it does not represent real market information but must be included in your submission.
- **Features**: `time` and columns `A` through `N` (same anonymized features as in the training data)

## Important Notes
- The `time` column indicates the chronological order of events (time 1 occurred before time 2).
- All times in `test.csv` are strictly after those in `train.csv`.
- Your goal is to predict test events based on train events.
- You need to predict columns `Y1` and `Y2` for the test set.

## Scoring
Predictions are evaluated using the **R²** metric, calculated separately for `Y1` and `Y2`. The final score is the **average** of the two R² values.

### R² Calculation

\[ R^2 = 1 - \frac{SS_{res}}{SS_{tot}} \]

Where:
- \(SS_{res} = \sum (y_{true} - y_{pred})^2\) (sum of squared residuals)
- \(SS_{tot} = \sum (y_{true} - \bar{y})^2\) (total sum of squares)
- \(\bar{y}\) is the mean of the true values
- R² ranges from \(-\infty\) to 1, where 1 indicates a perfect prediction

---

**Good luck, and may the best quantitative researchers win!**