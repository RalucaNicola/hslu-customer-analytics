## The data

**`customer_data.csv`** — 5,576 customers, one row each, 42 columns,
**no missing values**. Column families:

| Prefix | Meaning | Verified behaviour |
|---|---|---|
| `n_*`, `total_amount`, `days_active` | scalar summaries | — |
| `pos_perc` / `ecom_perc` | offline vs online split | sums to 1.0 (some rows 1.01 — rounding) |
| `cat_*` (20 cols) | CHF spent per category | **sums to `total_amount`** |
| `cur_*` (7 cols) | CHF spent per currency | does *not* sum to `total_amount` |
| `country_*` (7 cols) | transaction **counts** per country | does *not* sum to `n_transactions` |

**`customer_data_labels.csv`** — 3,903 labelled (2,140 churned / 1,763 not
≈ 55% churn).

**`customer_data_predict.csv`** — the 1,673 unlabelled IDs.
3,903 + 1,673 = 5,576 ✓

**`sow_category.csv`** / **`sow_category_counterpart.csv`** — monthly
Share-of-Wallet aggregates, 37 months (`year_month` stored as `"1-2021"`
strings).
