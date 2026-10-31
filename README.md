# CloudCore Retention Review Assistant

A classroom decision-support prototype for ISYS6014. The site ranks the 280 customers in the supplied CloudCore extract and brings profile, usage, billing, support and review evidence together for a Customer Success employee to review.

## Using the demonstration

Open an account card to see its evidence. Use Ctrl+F (Cmd+F on a Mac) to find a customer by name or ID. Rank-band links provide shortcuts through the queue. Each card shows up to the latest three tickets and all reviews found in the supplied extracts.

## How the model works

Python builds a Logistic Regression model using industry, support tier, tenure, monthly recurring revenue and derived product count. Region, customer identifiers, customer names and raw product mix are excluded as model inputs. `churn_flag` is the training target.

The displayed account scores come from a model fitted on the same 280 accounts. They are in-sample review signals, not independently validated individual predictions. The headline metrics use stratified 10-fold out-of-fold predictions; precision and recall use a 0.50 threshold.

The target combines customers who churned and customers flagged at risk. Scores are therefore not confirmed future-churn probabilities. Model associations are not causes. A person must verify current context and decide whether any action is appropriate. The prototype does not contact customers or make retention decisions.

Usage and billing are a single May 2026 snapshot and cannot establish trends. Support tickets and reviews are historical extracts, not live account status. This is not production software.

## Technology and deployment

`build_assistant.py` prepares the model and evidence; `render_python_site.py` generates the static HTML/CSS page. The website uses no JavaScript or live data connection. GitHub Pages serves the generated page; it does not execute Python.

To publish the prepared version, upload `index.html` to the repository root on `main` and replace the previous file. Upload this `README.md` to the same location to update the repository description. The site contains the displayed classroom customer and support data; publishing the page makes that content public.

To reproduce locally, place the four provided CSVs in a `project_sources` folder beside the project folder, using their prefixed filenames (`01-cloudcore_reviews.csv`, `03-cloudcore_transactions.csv`, `04-cloudcore_support_tickets.csv`, `05-cloudcore_customers.csv`). Install Python with `numpy`, `pandas` and `scikit-learn`, then run `python build_assistant.py` from the project folder. The result is `dist/index.html`. Run tests with `python -m unittest tests/test_assistant.py`.

## Data sources

- Customers: profile, model inputs and historical target.
- Transactions: May 2026 usage and billing snapshot.
- Support tickets: latest three available records per customer.
- Reviews: supplied customer review records.

Record IDs shown on the page support traceability to the supplied extracts.
