## AIM:
To perform time series analysis and decomposition on the monthly average temperature of a
city using Python.

We will use simple sample temperature data for 12 months and decompose it into:

Observed = Trend + Seasonal + Residual

## PROGRAM:
@@ -12,17 +14,21 @@ Observed = Trend + Seasonal + Residual
import pandas as pd
import matplotlib.pyplot as plt
from statsmodels.tsa.seasonal import seasonal_decompose

# Dataset 1: Monthly E-Commerce Sales (12 Months)
sales_data = [
120, 115, 130, 140, 150, 160,
155, 165, 175, 180, 210, 250
]

# Create date index for 2025
dates = pd.date_range(start="2025-01-01", periods=12, freq="ME")

# Create time series
data = pd.Series(sales_data, index=dates)
print("Monthly E-Commerce Sales ($1k):")
print(data)

# Plot original series
plt.figure(figsize=(10, 5))
plt.plot(data.index, data.values, marker="o", color="blue")
@@ -31,6 +37,7 @@ plt.xlabel("Month")
plt.ylabel("Sales ($1,000s)")
plt.grid(True)
plt.show()

# Decompose time series
result = seasonal_decompose(data, model="additive", period=12)
result.plot()
