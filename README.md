# Retail-Revenue-Optimization-Demand-Forecasting
This project builds an end-to-end analytics pipeline to forecast retail demand and evaluate dynamic pricing strategies to maximize revenue. Using historical transaction data, the workflow predicts future demand, models price elasticity effects, and quantifies revenue uplift from dynamic pricing compared to static pricing.

## Problem
Retail businesses must determine pricing strategies that balance **customer demand and profitability**. Static pricing strategies often ignore changes in demand patterns, which can lead to missed revenue opportunities.

This project addresses the following questions:

1) Can we **forecast future demand** using historical retail transactions?

2) How does **dynamic pricing** compare to static pricing?

3) What **revenue improvement** can be achieved using elasticity-based pricing?

4) How sensitive is revenue to **price elasticity assumptions**?

## Dataset
The analysis uses the **Online Retail dataset**, which contains historical e-commerce transactions including:

1) InvoiceDate

2) CustomerID

3) Quantity

4) UnitPrice

5) Product information

Dataset characteristics:

- ~500k transaction records

- International retail transactions

- Multiple products and customers

The data was transformed into a **monthly demand time series** to support forecasting.


## Methodolgy

The project follows a structured analytics pipeline.

## 1. Data Cleaning
Invalid records were removed to ensure data quality.

Filters applied:

- Quantity > 0

- UnitPrice > 0

- CustomerID not null

This removes returns, incorrect prices, and incomplete transactions.

## 2. Feature Engineering
New analytical features were created:

- Revenue = Quantity × UnitPrice

- Month and Year extracted from InvoiceDate

- Monthly demand aggregation

This converts transaction-level data into a **time series demand dataset**.

## 3. Time Series Foreasting
Demand forecasting was performed using Alteryx time-series tools.

Steps:

- Monthly demand aggregation

- Time-series model training

- Forecast generation for the next 6 months

- Adjustment of negative forecasts

Output:

 - Forecasted monthly demand

Visualization includes **historical vs forecast demand trends**.

## 4. Dynamic Pricing Model
A demand-based pricing strategy was implemented using price elasticity.

Price adjustment formula:

```bash
Optimal Price = Base Price × (1 + Elasticity × (Demand Ratio − 1))
```

Where:

- Demand Ratio = Forecast Demand / Historical Average Demand

- Elasticity measures customer sensitivity to price changes

Price limits were applied to ensure realistic pricing.

## 5. Revenue Optimization
Two pricing strategies were compared:

### Static Pricing
```bash
Revenue = Base Price x Forecast Demand
```

### Dynamic Pricing
```bash
Revenue = Optimal Price x Forecast Demand
```

Total Revenue was calculated for each scenario.

## 6.Sensitivity Analysis

Revenue performance was evaluated under different **price elasticity assumptions**.

Elasticity values tested:
```bash
0.1
0.2
0.3
0.4
0.5
```

This analysis shows how **demand responsiveness impacts revenue outcomes**.


## Results

Key findings from the analysis:

| **Metric**              | **Result** |
|-------------------------|------------|
| Static Pricing Revenue  | ~$69M      |
| Dynamic Pricing Revenue | ~$81M      |
| Revenue Increse         | ~$12M      |
| Revenue Uplift          |   18%      |

Sensitivity analysis indicates revenue increases as **price elasticity increases**, highlighting the importance of demand responsiveness in pricing decisions.

## Visualizations

The project includes the following visual outputs:

- Demand Forecast (Historical vs Forecast)

- Revenue Comparison (Static vs Dynamic Pricing)

- Revenue Sensitivity to Price Elasticity

These charts help communicate insights clearly for decision-makers.

## Executive Report

An automated PDF report was generated from the Alteryx workflow including:

- Title Page

- Executive Summary

- Forecast Visualization

- Pricing Comparison

- Elasticity Sensitivity Analysis

- Key Insight

## Tools & Technologies

- Alteryx Designer

- Time Series Forecasting

- Data Cleaning & Transformation

- Pricing Optimization Modeling

- Machine Learning Model
  
- Interactive Data Visualization

- Automated PDF Reporting


## Project Structure

```
Retail-Revenue-Optimization
│
├── data
│   └── Online Retail.xlsx
│
├── workflow
│   └── revenue_optimization_workflow.yxwz
│
├── report
│   └── retail_pricing_optimization_report.pdf
│
├── screenshots
│   ├── workflow_overview.png
│   ├── demand_forecast_chart.png
│   ├── revenue_comparison_chart.png
│   └── sensitivity_analysis_chart.png
│
├── diagrams
│   └── workflow_architecture.png
│
└── README.md
```

## Business Impact

The analysis demonstrates that dynamic pricing can significantly improve revenue compared to static pricing strategies.

Key benefits include:

- Improved revenue performance

- Demand-responsive pricing

- Better understanding of price elasticity effects

- Data-driven pricing decisions

This type of modeling is widely used in:

- E-commerce

- Airlines

- Ride-sharing platforms

- Hospitality pricing systems


## Workflow Architecture

### Project Pipeline Overview
```
Raw Retail Data
      │
      ▼
Data Cleaning
(Remove invalid transactions)
      │
      ▼
Feature Engineering
(Create revenue, month, demand features)
      │
      ▼
Demand Aggregation
(Monthly demand totals)
      │
      ▼
Time Series Forecasting
(Forecast next 6 months demand)
      │
      ▼
Forecast Adjustment
(Clean negative forecasts)
      │
      ▼
Dynamic Pricing Model
(Elasticity-based price optimization)
      │
      ▼
Revenue Simulation
Static Pricing vs Dynamic Pricing
      │
      ▼
Sensitivity Analysis
(Test multiple elasticity scenarios)
      │
      ▼
Optimal Scenario Selection
(Highest revenue outcome)
      │
      ▼
Business Recommendation
(Optimal elasticity + pricing strategy)
      │
      ▼
Executive Report
```

This project follows a structured analytics pipeline:

1. **Data Cleaning**

Raw retail transaction data is cleaned by removing invalid records such as negative quantities, zero prices, and missing customer IDs.

2. **Feature Engineering**

Revenue, month, and year features are created. Data is aggregated to monthly demand to form a time series dataset.

3. **Demand Forecasting**

Time series forecasting is applied to estimate demand for the next six months.

4. **Dynamic Pricing Model**

An elasticity-based pricing formula adjusts prices based on forecasted demand relative to historical averages.

5. **Revenue Simulation**

Revenue is calculated under both static pricing and dynamic pricing scenarios.

6. **Sensitivity Analysis**

Multiple elasticity assumptions are tested to evaluate how revenue changes under different demand responsiveness conditions.

7. **Recommendation Engine**
   
The elasticity scenario producing the highest projected revenue is selected and translated into a pricing recommendation.

9. **Executive Reporting**

The workflow generates an automated report including executive summary, revenue impact analysis, and business recommendations.
