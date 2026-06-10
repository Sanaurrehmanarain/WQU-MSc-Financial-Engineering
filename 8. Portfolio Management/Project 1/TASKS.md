# Portfolio Management Project Tasks

## Scenario Overview
A portfolio manager is evaluating 10 securities (TSLA, WMT, BAC, GS, LLY, MRK, GOOG, META, AAPL, XOM) to build a client portfolio.
* **Estimation Period:** September 1, 2023, to September 30, 2025.
* **Out-of-Sample Testing Period:** October 1, 2025, to December 31, 2025.

## Part 1: Standard Mean-Variance Portfolio Optimization
* **Step 1:** Determine the weights of the optimal mean-variance portfolio assuming weights sum to 1 and no short-selling is allowed.
* **Step 2:** Determine the new weights of the optimal mean-variance portfolio when no asset is allowed to have a weight of more than 18%. 
* **Step 3:** Compare the efficient frontiers of the portfolios from Step 1 and Step 2 by plotting them on the same graph and analyzing the main differences.
* **Step 4:** Evaluate the out-of-sample performance of both portfolios from October 1, 2025, to December 31, 2025, calculating cumulative return, Sharpe ratio, and Maximum Drawdown. Optimal weights must be determined via strict optimization.

## Part 2: Factor Exposure and Style Analysis
* **Step 4 (Part 2):** Explain the meaning and role of the Fama-French 5 factors: Market Risk Premium, SMB, HML, CMA, RMW. Provide and comment on their correlation matrix.
* **Step 5:** Perform an OLS and a robust linear regression to estimate the portfolio's exposure to these factors, explicitly defining the training and testing data split.
* **Step 6:** Write a report detailing how these factors explain the returns of the selected portfolio.

## Part 3: Mean-Variance Optimization via Simulations
* **Asset Selection:** Choose a subset of 5 assets from the original 10 for the same time period.
* **Step 7:** Determine the optimal portfolio (weights sum to 1, no short-selling) using both hard optimization and Monte Carlo simulations. Discuss the number of simulations required for convergence.
* **Step 8:** Add a maximum weight constraint of 30% per asset. Compute optimal weights using both optimization and simulation, and analyze the convergence difficulty given the added box constraints.

## Part 4: Black-Litterman Model Implementation
* **Step 9:** Implement the Black-Litterman (BL) model to incorporate subjective market views.
    * **(a)** Define a synthetic composite market portfolio by appending the S&P 500 as an 11th asset, ensuring correct market capitalization weighting. Determine the Sharpe ratio of this market portfolio.
    * **(b)** Explain and justify the choice of the scalar parameter tau, factoring in the data's time horizon.
    * **(c)** Define subjective views using the pick matrix P and explain the uncertainty matrix Q.
    * **(d)** Calculate the Black-Litterman expected returns and covariance, then compute the new optimal portfolio weights.
    * **(e)** Compare the resulting BL portfolio weights to those obtained in Part 1, discussing how specific views and constraints impacted the allocation.