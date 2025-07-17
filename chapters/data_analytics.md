Data Analytics
Data analytics involves querying and analyzing data to uncover insights. This chapter covers time series analysis and SQL-based analytics.
Time Series Analysis with Python
Below is a Plotly example for visualizing a time series.
import pandas as pd
import plotly.express as px

# Sample data
df = pd.DataFrame({
    'date': pd.date_range('2025-01-01', periods=100, freq='D'),
    'value': range(100)
})

# Plot time series
fig = px.line(df, x='date', y='value', title='Sample Time Series')
fig.write_layout(template='plotly_white')
fig.show()

SQL Analysis Example
A SQL query to calculate moving averages.
SELECT
  date,
  value,
  AVG(value) OVER (
    ORDER BY date
    ROWS BETWEEN 6 PRECEDING AND CURRENT ROW
  ) AS moving_average
FROM
  time_series_data
ORDER BY
  date;

This query computes a 7-day moving average for time series data.