# Securitisation Risk Analytics and Dashboard Design

## Project Overview
This project builds an end-to-end Power BI dashboard for **Auto Loan Securitisation Risk Analytics**. It provides automated tracking of pool credit metrics, IFRS 9 expected credit loss stages, delinquency aging buckets, and monthly time-series performance metrics.

## Key Metrics & Portfolio Summary
* **Total Pool Balance**: ~317.79M (representing active securitised auto loan assets)
* **IFRS 9 ECL Provision**: ~24.66M (total expected credit loss reserves)
* **Weighted Average Coupon (WAC)**: ~10.95%
* **Weighted Average LTV (WA-LTV)**: ~67.54%

## Data Schema & Architecture
* **`auto_loan_securitisation_data`**: Core portfolio table housing loan-level attributes, current balances, IFRS 9 stages, interest rates, and LTV ratios.
* **`dpd_snapshot_history`**: Tracks historical delinquency aging buckets ranging from `Current` to `Repossessed`.
* **`dynamic_loss_monthly`**: Time-series table tracking monthly performance indicators like CPR (Constant Prepayment Rate) and Collection Efficiency.
* **`_Measures`**: Dedicated repository table for all explicit DAX calculations and portfolio risk models.

## Key Risk Insights & Visuals
1. **IFRS 9 Credit Risk Breakdown (Donut Chart)**:
   * **Stage 1 (Performing)**: Dominates the portfolio at ~85.89% (272.93M).
   * **Stage 2 (Underperforming)**: Accounts for ~8.54% (27.15M) showing significant increase in credit risk.
   * **Stage 3 (Credit-Impaired/Default)**: Represents ~5.57% (17.7M) of total exposure.
2. **Delinquency Distribution (Clustered Column Chart)**: Highlights high concentration in the `Current` bucket with a gradual tail tapering across early-to-late DPD buckets (`1-29 DPD` up to `Repossessed`).
3. **Dynamic Loss Trend (Line Chart)**: Monitors monthly portfolio health trends over time via annualized CPR and collection efficiency metrics.
