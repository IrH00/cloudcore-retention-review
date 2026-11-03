<div align="center">

# CloudCore Retention Review Assistant

### A human-in-the-loop workspace for prioritising Customer Success reviews

[![Open the live website](https://img.shields.io/badge/Live%20demo-Open%20website-4F46E5?style=for-the-badge&logo=githubpages&logoColor=white)](https://irh00.github.io/cloudcore-retention-review/)

</div>

## What is this?

CloudCore Retention Review Assistant is a classroom decision-support prototype for Customer Success. It helps employees decide **which customer accounts to review first** by bringing historical profile, usage, billing, support-ticket and review evidence into one place.

It is designed to support professional judgement—not replace it.

## Start in three steps

| Step | What to do |
|---|---|
| **1. Review the account** | Start with the Top 5 queue or search for a specific company. Read the historical evidence in the account card. |
| **2. Check current context** | Verify renewal timing, recent escalations, current usage and account-owner notes in CloudCore’s current systems. |
| **3. Choose and record action** | Contact, monitor, resolve an issue, or close as no action—then record the reason for the decision. |

## What the website includes

| Feature | Purpose |
|---|---|
| **Customer review queue** | Ranks the 280 supplied customer accounts as a practical review order. |
| **Account search** | Finds an account by company, customer ID, industry, region, product or support tier. |
| **Evidence cards** | Shows customer profile, May 2026 usage/billing context, recent supplied tickets and reviews. |
| **Human-evidence checks** | For the five highest-priority accounts, highlights historical evidence that supports, challenges or does not clarify the queue position. |
| **Data guide** | A minimisable guide explaining the fields, source IDs, scores and limitations. |

## Reading the queue responsibly

> **A high score means “review this account sooner.” It does not mean “this customer will churn.”**

- The review score is a historical Logistic Regression prioritisation signal, not a confirmed future-churn probability.
- Model associations are not explanations or causes of churn.
- The displayed usage and billing information is a single May 2026 snapshot; it cannot show a trend.
- Support tickets and reviews are historical supplied records, not live CRM status.
- The prototype cannot contact customers, approve an action or make an automatic retention decision.

## Data basis

This demonstration uses the **280-customer consultant engagement extract** created for the CloudCore classroom scenario. In this dataset, `churn_flag = 1` means an account had **churned or been flagged at risk** during the historical observation window. Monetary values are shown in USD.

The separate 400-customer public portfolio is intentionally excluded: it has a different population, currency and churn definition. The two data families must not be combined.

## Classroom context

Built as part of **ISYS6014 — AI-Driven Knowledge Systems**. CloudCore Networks, its customer records and all displayed data are fictional classroom material. This is a static demonstration with no live system connection.
