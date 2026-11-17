# Group 22 – Week 5: First Model Results

**Module:** 7PAM2033 Data Science Professional Team Project · **Group:** 22
**Project:** Automated algorithmic trading using technical indicators and financial news sentiment

This folder holds our work for the week 5 group session and the week that followed. Week 4 (EDA and data preparation) is in the [algo-trading-week-4](https://github.com/MaheshShivanna0408/algo-trading-week-4) repo.

## Contents

| Folder | File | What it is |
|---|---|---|
| `code/` | G22_Week5_Models_v1.0.ipynb | Run on 15 Nov 2026 (outputs included). Rebuilds the week 4 data, trains and tests the first model (M0), runs the model checks and checks FinBERT on Financial PhraseBank |
| `plans/` | G22_TestPlan_v1.3.docx / .pdf | Test Plan updated for week 5: model checks, new unit tests, M0 column in the KPI table |
| `results/` | week5_model_results.json, model_checks.csv | Model results and the 7 model checks (all PASS) |
| `results/figures/` | 05_direction_model_results.png, 06_finbert_confusion_matrix.png | Charts produced by the notebook |
| `docs/` | G22_ProjectLog_v1.1.md | Log of all work from week 1 to week 5 and who did it |
| `docs/` | G22_CodeReview_Branches_Guide.md | How to set up the review branches for the 3 reviewers (weeks 5/6) and sign off reviews |
| `docs/` | G22_Week5_Literature_Practice.md | 30-minute plan for practising the literature discussion |

## Week 5 session checklist

| # | Activity | Owner | Status |
|---|---|---|---|
| 1 | Scrum meeting (first 10 minutes) | Scrum Master | |
| 2 | Code reviews done and signed off | Code Review Manager | |
| 3 | Practise discussing our 2 papers (30 minutes) | Communications Leader | See docs/G22_Week5_Literature_Practice.md |
| 4 | EDA, pre-processing, feature engineering done; results of one model | All team | EDA/features: week04 v1.3 ✅ · Model results ✅ (see Results) |
| 5 | Test Plan edited after code reviews and coding | Test Plan Manager | plans/G22_TestPlan_v1.3 ✅ |
| 6 | Project plans and timeline updated | Team Leader | |
| 7 | week05 repo created; code review branches for 3 reviewers | GitHub Manager | See docs/G22_CodeReview_Branches_Guide.md |
| 8 | Each member summarises their actions (last 5 minutes) | Scrum Master | |

## The two models in this week's notebook

| Model | Question | Data | Compared with |
|---|---|---|---|
| **M0 – logistic regression (T09)** | Will the stock close higher tomorrow? | Technical indicators for 30 stocks; tuned on 2018, tested once on 2019–2020 | Majority-class baseline and the KPIs (accuracy ≥ 56%, precision on BUY ≥ 60%, ROC-AUC ≥ 0.60) |
| **FinBERT check (supports T10)** | Is this financial sentence negative, neutral or positive? | Financial PhraseBank, held-out 20% (968 sentences) | TF-IDF + logistic regression baseline; Test Plan target ≥ 85% |

M0 is the simple benchmark that the planned models (M1 Bi-LSTM, M2 FinBERT, M3 Hybrid) must beat.

## Results (run on Colab with a T4 GPU, 15 Nov 2026)

**M0 – next-day direction, test years 2019–2020 (9,390 stock-days, 52.4% up days)**

| | Accuracy | Precision (up) | Recall (up) | ROC-AUC |
|---|---|---|---|---|
| Majority-class baseline (always "up") | 52.4% | 52.4% | 100% | n/a |
| M0 logistic regression | **53.1%** | **53.5%** | 81.2% | **0.521** |
| KPI target | ≥ 56% | ≥ 60% | – | ≥ 0.60 |

- M0 beats the baseline by 0.7 points but **misses all three KPIs**. ROC-AUC 0.52 is only just above chance (0.5).
- It predicts "up" on 80% of days, so it behaves much like the baseline. The strongest regularisation (C = 0.001) was chosen because every C scored about 50% on the 2018 validation year, which means the technical indicators on their own carry very little signal.
- The largest weight is negative on RSI: stocks that rose strongly recently were slightly less likely to rise the next day.
- **Next:** add FinBERT news sentiment (T10) and test the planned non-linear models (M1 Bi-LSTM, M3 Hybrid) against this benchmark.

**FinBERT check – Financial PhraseBank, held-out 20% (968 sentences)**

| | Accuracy | Macro F1 |
|---|---|---|
| TF-IDF + logistic regression baseline | 75.2% | 0.715 |
| FinBERT (no extra training) | **87.5%** | **0.867** |
| Test Plan target | ≥ 85% | – |

- FinBERT **passes** the 85% target and beats the baseline by 12 points.
- Its main mistake is reading sentiment into neutral sentences: 62 neutral sentences were labelled positive and 31 negative.
- FinBERT was originally fine-tuned on PhraseBank, so this score is probably optimistic; the real test is on our news headlines.

All 7 model checks passed (results/model_checks.csv).

## How to reproduce

1. Open `code/G22_Week5_Models_v1.0.ipynb` in Google Colab. CPU is enough; a T4 GPU makes the FinBERT step faster.
2. Runtime → Run all (log in to Kaggle if asked).

## File naming

`G22_<Name>_v<major>.<minor>` – the version number increases with every change (see Data Management Plan).
