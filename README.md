# CloudCore Retention Review Assistant

A small decision-support demonstration for ISYS6014: AI Driven Knowledge Systems.

**Live demo:** https://irh00.github.io/cloudcore-retention-review/

## Purpose

The assistant creates a short customer review watchlist from historical CloudCore data, then presents traceable account evidence before a Customer Success employee considers outreach.

It supports a human decision — it does not replace one.

## What the demo does

- Creates a five-account demonstration watchlist.
- Uses a transparent Logistic Regression workflow.
- Does not use customer names, customer IDs, region, or `churn_flag` as operational model features.
- Combines customer profile, transaction, support-ticket, and review evidence.
- Shows source record IDs so displayed evidence can be checked.

## Human-review safeguards

- It does not confirm that a customer will churn.
- It does not automatically contact customers, offer discounts, or make retention decisions.
- Customer Success staff must review the evidence and decide any next action.
- This is a classroom pilot, not a production system.

## Site files

| File | Purpose |
| --- | --- |
| `index.html` | Demo interface |
| `assistant_data.js` | Watchlist and traceable evidence used by the interface |

## Project context

Developed from supplied CloudCore case-study extracts for an academic assessment.
