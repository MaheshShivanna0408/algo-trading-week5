# Group 22 – Project Log File

**Version 1.1** (15 Nov 2026): one log for the whole project, from week 1 onwards. v1.0 (in the week04 repo) started in week 4.
Each member adds their own work. Newest entries at the bottom of each week. Fields marked **[to fill]** are for the team member concerned to complete.

## Weeks 1–3: forming the team and planning

| Date | Task ID | Work done | Who | Evidence |
|---|---|---|---|---|
| **[to fill]** | – | Week 1: team formed; roles agreed (Team Leader & Pipeline Architect, Lead ML Engineer, Feature & Sentiment Engineer, Backtesting & Risk Lead, QA/DevOps & Front-End Co-Lead) | All team | **[to fill: meeting notes]** |
| **[to fill]** | – | Week 2: project topic chosen (algorithmic trading with technical indicators and news sentiment); datasets selected (stock prices, dated news headlines, Financial PhraseBank) | All team | **[to fill]** |
| 21 Oct 2026 | – | GitHub organisation Algo-project-22 chosen as the official repo; starter structure (src/, tests/, CI workflow, pull request template) prepared | GitHub Manager **[to fill: name]** | week03 repo |
| 22 Oct 2026 | T01–T03 | Six project plans drafted: Project Specifications, Team Plan, Timeline, Data Management Plan, Pipeline Workflow, Test Plan | All team | week03 repo |
| 23 Oct 2026 | T03 | Six project plans finalised and submitted on Canvas (Assessment 1) | All team | week03 repo |

## Week 4: EDA and data preparation

| Date | Task ID | Work done | Who | Evidence |
|---|---|---|---|---|
| 28 Oct 2026 | – | Week 4 group session: Scrum meeting, actions agreed | Scrum Master **[to fill: name]** | Meeting notes **[to fill]** |
| 28 Oct 2026 | T04, T05, T06 | EDA and data preparation notebook v1.0 created and run on the real data: combined prices and news for 30 stocks, quality checks, technical features | Nahkum (Data Preparation Manager) – notebook drafted with AI assistance, reviewed and run by Nahkum | week04/code |
| 28 Oct 2026 | T05 | EDA finding: 5 of the 30 selected symbols were ETNs or funds, not companies (UGAZ, DGAZ, DZZ, DRR, CHN). Notebook v1.1 removes them | Nahkum | week04 README |
| 28 Oct 2026 | T07 | Test Plan updated to v1.1 to match the week 4 code | Test Plan Manager **[to fill: name]** | week04/plans |
| 28 Oct 2026 | – | Project Timeline updated with progress | Team Leader (Mahesh P) **[to fill: confirm]** | week04/plans |
| 29 Oct 2026 | – | Literature papers chosen (FinBERT, Araci 2019; Attention Is All You Need, Vaswani et al. 2017); study guide corrected to v1.1 | All team | week04/docs |
| 3 Nov 2026 | T05 | Notebook v1.2 and v1.3: bad price rows and repeated dates removed before quality checks | Nahkum | week04/code |
| 3 Nov 2026 | T05 | v1.3 run on real data: 75,457 rows, 30 companies, 10/10 quality checks passed | Nahkum | week04/results/data_quality_report.csv |
| 3 Nov 2026 | T07 | Test Plan v1.2: real-data quality results added | Test Plan Manager **[to fill: name]** | week04/plans |
| **[to fill]** | | **[Other members: add your week 4 work here]** | | |

## Week 5: first model results

| Date | Task ID | Work done | Who | Evidence |
|---|---|---|---|---|
| **[to fill: session date]** | – | Week 5 group session: Scrum meeting, actions agreed | Scrum Master **[to fill: name]** | Meeting notes **[to fill]** |
| 15 Nov 2026 | – | week04 folder uploaded to GitHub | **[to fill: name]** | week04 repo |
| 15 Nov 2026 | T09 | Week 5 notebook v1.0: first model M0 (logistic regression on technical indicators), tuned on 2018 and tested once on 2019–2020 against a majority-class baseline; 7 model checks coded | Nahkum – notebook drafted with AI assistance, reviewed and run by Nahkum | week05/code |
| 15 Nov 2026 | T10 | FinBERT checked on a held-out 20% of Financial PhraseBank against a TF-IDF baseline (supports Kalyan's FinBERT scoring of the headlines) | Nahkum | week05/code |
| 15 Nov 2026 | T09, T10 | Notebook run on the real data (Colab, T4 GPU); 7/7 model checks passed. M0: accuracy 53.1% (baseline 52.4%), precision 53.5%, ROC-AUC 0.521, so all three KPIs missed. FinBERT on PhraseBank: 87.5% accuracy (target 85% met) vs TF-IDF baseline 75.2% | Nahkum | week05/results |
| 15 Nov 2026 | T07 | Test Plan v1.3: model checks table, 3 new unit tests, M0 column in the KPI table | Nahkum (Test lead) | week05/plans |
| **[to fill]** | – | Code review branches set up for the 3 reviewers (weeks 5/6) | GitHub Manager **[to fill: name]** | GitHub branches |
| **[to fill]** | – | Code reviews done and signed off | Code Review Manager **[to fill: name]** | Pull requests |
| **[to fill]** | – | Literature discussion practised as a team (30 minutes) | Communications Leader **[to fill: name]** | week05/docs |
| **[to fill]** | – | Project plans and timeline updated to match progress | Team Leader (Mahesh P) **[to fill: confirm]** | week05/plans |
| **[to fill]** | | **[Other members: add your week 5 work here]** | | |

## Open actions for next week

| Action | Owner | Due |
|---|---|---|
| Score the news headlines with FinBERT and add daily sentiment features (T10) | Kalyan | **[to fill]** |
| Compare M0 with and without sentiment features (M0 alone: 53.1%, ROC-AUC 0.521) | **[to fill]** | **[to fill]** |
| Prepare individual parts for the literature discussion (Assessment 3) | Each member | **[to fill]** |
