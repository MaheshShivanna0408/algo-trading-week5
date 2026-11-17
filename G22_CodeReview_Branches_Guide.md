# Group 22 – Code Review Branches (weeks 5/6)

**Version 1.0** (15 Nov 2026) · For the GitHub Manager (week 5 activity 7) and the Code Review Manager (activity 2). Follows section 7 of the Test Plan.

## 1. Who reviews what

| Reviewer | Branch | Code to review | Author |
|---|---|---|---|
| **[to fill: reviewer 1]** | `review/week5-reviewer1` | week04 EDA notebook v1.3 (data cleaning, quality checks, features) | Nahkum |
| **[to fill: reviewer 2]** | `review/week5-reviewer2` | week05 model notebook v1.0 (M0 model, model checks) | Nahkum |
| **[to fill: reviewer 3]** | `review/week5-reviewer3` | **[to fill: e.g. FinBERT headline scoring (T10)]** | **[to fill: e.g. Kalyan]** |

A reviewer never reviews their own code. Replace `reviewer1` etc. with first names if the team prefers (e.g. `review/week5-mani`).

## 2. Create the branches (GitHub website, about 2 minutes)

1. Open the repo (e.g. **week05**) on GitHub.
2. Click the branch button that says **main** (top left, above the files).
3. Type the new branch name, e.g. `review/week5-reviewer1`, then click **Create branch review/week5-reviewer1 from main**.
4. Repeat for the other two reviewers.

## 3. Protect the main branch

**Settings → Branches → Add branch protection rule** (or **Add ruleset**), branch name `main`:
- tick **Require a pull request before merging**
- set **Required approvals** to **1**

Now nothing reaches `main` without a reviewer's approval.

## 4. How a review works

1. The author puts the code to be reviewed on the reviewer's branch, then opens a **pull request** from that branch into `main` (**Pull requests → New pull request**).
2. They fill in the pull request template and add the reviewer under **Reviewers** (right-hand side).
3. The reviewer opens **Files changed** and leaves comments on lines. They check: correct results, readable code, error handling, and that the tests or checks exist.
4. The author fixes the comments and pushes the changes to the same branch.
5. The reviewer clicks **Review changes → Approve**, and the Code Review Manager merges the pull request into `main`.

## 5. Sign-off record (Code Review Manager)

| Pull request | Code | Reviewer | Comments resolved | Approved on | Merged into main |
|---|---|---|---|---|---|
| #**[to fill]** | week04 EDA notebook v1.3 | **[to fill]** | | | |
| #**[to fill]** | week05 model notebook v1.0 | **[to fill]** | | | |
| #**[to fill]** | **[to fill]** | **[to fill]** | | | |
