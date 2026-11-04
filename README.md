# Anyone AI — Customers & Orders Technical Challenge

A Python data-processing challenge completed as part of the **Anyone AI admissions process**. This repository contains my Jupyter Notebook implementation for analyzing customer and order records, with an emphasis on clean data handling, accurate aggregation, and readable code.

## Challenge overview

The assessment uses two CSV datasets provided by Anyone AI:

| Dataset | Fields | Description |
| --- | --- | --- |
| `customers.csv` | `CustomerID`, `FirstName`, `LastName`, `City`, `State` | Customer profiles and locations |
| `orders.csv` | `CustomerID`, `OrderID`, `Date`, `OrderTotal`, `ProductName`, `Price` | Orders and their associated products |

**Data relationships:** One customer can place multiple orders, and each order can contain multiple products. Therefore, an `OrderID` may appear in several CSV rows, while its `OrderTotal` represents the full order amount.

## Exercises

### Exercise 1 — Processing customer data

Five questions focused on:

- Counting customer records
- Identifying distinct states
- Finding states with the most and fewest customers
- Finding the most common last name

### Exercise 2 — Processing order data

Six questions focused on:

- Counting unique orders
- Calculating average and maximum items per order
- Counting orders from October 2021
- Identifying the highest-spending customer in 2021
- Determining the strongest historical sales month

## Implementation

The notebook uses **Python's standard library** for the analysis, including `csv`, `collections`, `datetime`, and `decimal`.

Key implementation decisions:

- Normalize whitespace and capitalization when analyzing customer information.
- Represent orders by `OrderID` to avoid counting multi-item orders more than once.
- Read the orders dataset once and reuse the resulting data structure across questions.
- Use `Decimal` for monetary calculations.
- Validate repeated order records and handle missing or invalid dates.
- Compare sales by calendar month and by individual year-month period.

The notebook includes code, explanations through comments, calculated results, and data-quality checks.

## Run the notebook

[**Open in Google Colab**](https://colab.research.google.com/github/CVILLA09/AnyoneAIChallenge/blob/main/customers_and_orders/customers_and_orders.ipynb) · [View the notebook on GitHub](customers_and_orders/customers_and_orders.ipynb)

1. Open the notebook in Google Colab.
2. Select **File → Save a copy in Drive** if you want to keep your changes.
3. Select **Runtime → Run all** to execute the cells in order.
4. Review the results for both exercises.

The first code cell downloads the datasets from Anyone AI's official repository into `./sample_data/`. Colab stores these files in a **temporary runtime**, so rerun that cell if your session resets.

## Repository structure

```text
.
├── README.md
└── customers_and_orders/
    └── customers_and_orders.ipynb
```

## Source and attribution

The challenge instructions and datasets were provided by **Anyone AI**:

- [Original challenge notebook](https://github.com/anyoneai/notebooks/blob/main/customers_and_orders/customers_and_orders.ipynb)
- [Customer dataset](https://github.com/anyoneai/notebooks/blob/main/customers_and_orders/data/customers.csv)
- [Orders dataset](https://github.com/anyoneai/notebooks/blob/main/customers_and_orders/data/orders.csv)

This repository documents my implementation of the assessment. It is **not an official Anyone AI repository**.
