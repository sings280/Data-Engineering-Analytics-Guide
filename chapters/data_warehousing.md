Data Warehousing
Data warehouses like Google BigQuery and Snowflake are optimized for storing and querying large datasets.
BigQuery Example
Below is a sample SQL query in BigQuery to aggregate sales data.
SELECT
  DATE_TRUNC(sale_date, MONTH) AS sale_month,
  SUM(amount) AS total_sales
FROM
  `project.dataset.sales`
GROUP BY
  sale_month
ORDER BY
  sale_month;

Snowflake Example
A similar query in Snowflake for time-based aggregation.
SELECT
  DATE_TRUNC('MONTH', sale_date) AS sale_month,
  SUM(amount) AS total_sales
FROM
  sales
GROUP BY
  sale_month
ORDER BY
  sale_month;

Warehouse Architecture
graph TD
    A[Data Sources] -->|ETL| B[Staging Layer]
    B -->|Transform| C[Data Warehouse]
    C -->|Query| D[BI Tools]
    C -->|ML| E[Machine Learning]

This diagram shows how data flows from sources to a warehouse for analytics and ML.