# Retail-Revenue-Optimization-Demand-Forecasting
This project builds an end-to-end analytics pipeline to forecast retail demand and evaluate dynamic pricing strategies to maximize revenue. Using historical transaction data, the workflow predicts future demand, models price elasticity effects, and quantifies revenue uplift from dynamic pricing compared to static pricing.

# Problem
Retail businesses must determine pricing strategies that balance **customer demand and profitability**. Static pricing strategies often ignore changes in demand patterns, which can lead to missed revenue opportunities.

This project addresses the following questions:

1) Can we **forecast future demand** using historical retail transactions?

2) How does **dynamic pricing** compare to static pricing?

3) What **revenue improvement** can be achieved using elasticity-based pricing?

4) How sensitive is revenue to **price elasticity assumptions**?

# Dataset
The analysis uses the **Online Retail dataset**, which contains historical e-commerce transactions including:

1) InvoiceDate

2) CustomerID

3) Quantity

4) UnitPrice

5) Product information

Dataset characteristics:

1) ~500k transaction records

2) International retail transactions

3) Multiple products and customers

The data was transformed into a **monthly demand time series** to support forecasting.


# Methodolgy

The project follows a structured analytics pipeline.

# 1. Data Cleaning
Invalid records were removed to ensure data quality.

Filters applied:

1) Quantity > 0

2) UnitPrice > 0

3) CustomerID not null

This removes returns, incorrect prices, and incomplete transactions.

# 2. Feature Engineering
New analytical features were created:

- Revenue = Quantity × UnitPrice

- Month and Year extracted from InvoiceDate

- Monthly demand aggregation

This converts transaction-level data into a **time series demand dataset**.

# 3. Time Series Foreasting
Demand forecasting was performed using Alteryx time-series tools.

Steps:

- Monthly demand aggregation

- Time-series model training

- Forecast generation for the next 6 months

- Adjustment of negative forecasts

Output:

 - Forecasted monthly demand

Visualization includes **historical vs forecast demand trends**.

# 4. Dynamic Pricing Model
