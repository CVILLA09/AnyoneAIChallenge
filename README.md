
# Anyone AI — Customers & Orders Technical Challenge

A Python data-processing challenge completed as part of the **Anyone AI admissions process**.

This repository contains my Jupyter Notebook implementation for analyzing customer and order records, with an emphasis on data integrity, accurate aggregation, efficient processing, and readable code.

## Challenge Overview

The assessment uses two CSV datasets provided by Anyone AI:

| Dataset | Fields | Description |
| --- | --- | --- |
| `customers.csv` | `CustomerID`, `FirstName`, `LastName`, `City`, `State` | Customer profiles and locations |
| `orders.csv` | `CustomerID`, `OrderID`, `Date`, `OrderTotal`, `ProductName`, `Price` | Orders and their associated products |

### Data Relationships

One customer can place multiple orders, and each order can contain multiple products. Therefore, an `OrderID` may appear across several rows.

The analysis distinguishes between two monetary fields:

- **`Price`:** The price associated with an individual product.
- **`OrderTotal`:** The total amount recorded for an order.

Since these values may differ, product prices are used to calculate customer spending and historical product sales, while order totals are retained for comparison.

## Exercises

### Exercise 1 — Processing Customer Data

Five questions focused on:

- Counting customer records
- Identifying distinct states
- Finding states with the most and fewest customers
- Identifying the most common last name

### Exercise 2 — Processing Orders Data

Six questions focused on:

- Counting unique orders
- Calculating average and maximum items per order
- Counting orders placed in October 2021
- Identifying the highest-spending customer in 2021
- Determining the strongest historical sales month

## Implementation

The analysis uses **Python's standard library**, including:

- `csv` — Reading and parsing CSV files
- `collections` — Data aggregation with `Counter` and `defaultdict`
- `datetime` — Date parsing and validation
- `decimal` — Precise monetary calculations
- `calendar` — Converting month numbers to names

### Key Implementation Decisions

- Normalize whitespace and capitalization in customer data.
- Organize orders by `OrderID` to avoid double-counting multi-item orders.
- Read the orders dataset once and reuse the resulting data structure.
- Use `Decimal` for monetary calculations.
- Distinguish product-level sales (`Price`) from order-level totals (`OrderTotal`).
- Validate repeated order records for inconsistent information.
- Handle missing or invalid dates without modifying the source files.
- Compare historical sales by calendar month and individual year-month period.

The notebook includes documented solutions, calculated results, and data-quality checks.

## Run the Notebook

[**Open in Google Colab**](https://colab.research.google.com/github/CVILLA09/AnyoneAIChallenge/blob/main/customers_and_orders/customers_and_orders.ipynb) · [View the Notebook on GitHub](customers_and_orders/customers_and_orders.ipynb)

1. Open the notebook in Google Colab.
2. Select **File → Save a copy in Drive** to preserve your changes.
3. Select **Runtime → Run all** to execute the cells in order.
4. Review the results for both exercises.

The first code cell downloads the datasets from Anyone AI's official repository into `./sample_data/`.

**Note:** Google Colab stores these files in a temporary runtime. If the session resets, the data-loading cell must be executed again.

No additional Python packages are required beyond those already available in Google Colab.

## Repository Structure

```text
.
├── README.md
└── customers_and_orders/
    └── customers_and_orders.ipynb
```

## Source and Attribution

The challenge instructions and datasets were provided by **Anyone AI**:

- [Original Challenge Notebook](https://github.com/anyoneai/notebooks/blob/main/customers_and_orders/customers_and_orders.ipynb)
- [Customer Dataset](https://github.com/anyoneai/notebooks/blob/main/customers_and_orders/data/customers.csv)
- [Orders Dataset](https://github.com/anyoneai/notebooks/blob/main/customers_and_orders/data/orders.csv)

This repository documents my implementation of the technical assessment. It is **not an official Anyone AI repository**.
