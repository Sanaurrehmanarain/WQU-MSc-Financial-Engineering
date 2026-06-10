# Portfolio Management Project: Machine Learning Optimization

## Project Scenario & Objective
Portfolio management is currently undergoing a renaissance. Traditional, Nobel-Prize-winning ideas—such as Markowitz's Modern Portfolio Theory—are increasingly being supplemented or replaced by machine learning algorithms. Machine learning fundamentally changes how financial professionals make decisions under uncertainty and conduct statistical analyses. 

When applied to the portfolio optimization process, ML techniques can provide a distinct advantage. Combined with leverage and other structural factors, these advantages can lead to substantial outperformance over traditional competition. In this project, we apply 21st-century machine learning concepts—specifically denoising, detoning, clustering, and advanced backtesting—to modernize and optimize an equity portfolio.

## Data Parameters
* **Asset Universe:** A selected portfolio of at least 10 highly liquid assets.
* **Frequency:** Daily market data.
* **In-Sample (Training) Period:** January 1, 2024 – September 30, 2025.
* **Out-of-Sample (Testing) Period:** October 1, 2025 – December 31, 2025.
* **Full Backtest Period:** January 1, 2024 – December 31, 2025.

---

## Detailed Project Tasks

### Step 1: Base Optimization (The Kelly Criterion)
* **Objective:** Determine the optimal Kelly portfolio for the selected assets using the in-sample training data.
* **Constraint Application:** Acknowledging the aggressive concentration risk inherent to the unconstrained Kelly criterion, calculate a constrained optimal Kelly portfolio where no single asset is allowed to exceed a 20% weight of the total portfolio.

### Step 2: Out-of-Sample Performance and Leverage
* **Objective:** Test the constrained Kelly portfolio on the out-of-sample data (October 1, 2025 to December 31, 2025).
* **Leverage Variations:** Compare the baseline constrained Kelly portfolio with levered/de-levered variations (e.g., Half-Kelly and Double-Kelly).
* **Metrics:** Evaluate risk and performance across all variations using Cumulative Return, Sharpe Ratio, Maximum Drawdown, and 95% Conditional Value at Risk (cVaR). Organize the findings in a clear comparative table.

### Step 3: Advanced Backtesting (K-Fold Cross Validation)
* **Objective:** Backtest the portfolio models to evaluate true robustness across different market regimes, avoiding the bias of a single chronological train-test split. 
* **Execution:** Write Python code to perform a K-Fold cross-validation utilizing the entire 2-year dataset (January 1, 2024 – December 31, 2025).
* **Documentation:** Provide a detailed written explanation detailing the theoretical framework and necessity of K-Fold cross-validation in financial modeling. 

### Step 4: Machine Learning Methodologies (Theory)
* **Objective:** Provide a comprehensive theoretical explanation (max 2 pages per item) of the features and benefits of modern quantitative improvements, specifically focusing on:
    1. **Denoising:** Shrinking empirical covariance noise using Random Matrix Theory (e.g., Marčenko-Pastur distribution).
    2. **Detoning:** Removing the dominant market eigenvector to isolate idiosyncratic relative-value relationships.
    3. **Clustering:** Utilizing distance metrics and graph theory, specifically Hierarchical Risk Parity (HRP), to allocate weights without requiring matrix inversion.

### Step 5: Machine Learning Methodologies (Application)
* **Objective:** Apply the ML methodologies described in Step 4 to the base portfolio from Step 1.
* **Execution:** Detail the programmatic steps taken to implement these improvements.
* **Sequencing Analysis:** Document the merits of applying one, two, or all of these improvements to the current portfolio. Theorize and mathematically justify the optimal sequence with which to deploy Denoising, Detoning, and Clustering.

### Step 6: ML Outperformance vs. Traditional Baselines
* **Objective:** Discuss and mathematically prove if and how multiple ML improvements outperform single improvements or traditional baselines out-of-sample.
* **Execution:** Evaluate a combination of improvements (e.g., ML HRP vs. Standard HRP vs. Kelly) using at least three distinct metrics (e.g., Return, Sharpe Ratio, Expected Shortfall, Variance).
* **Analysis:** Discuss whether the ML methodologies helped out-of-sample performance by answering:
    1. What are the specific numerical differences in performance?
    2. What structural reasons explain these differences (referencing specific asset dynamics, historical data, and model math)?
    3. Does the incremental gain in risk-adjusted performance justify the added computational complexity of the ML improvements?

### Step 7: Technical Presentation
* **Objective:** Synthesize the project findings into a professional format suitable for stakeholders.
* **Execution:** Prepare 3-5 slides for a technical talk detailing how the applied portfolio methodology addressed and solved a major financial modeling problem. 
* **Focus Area:** The presentation must focus on one of the following areas: Regularization, Prediction vs. Interpretation, Estimation Error, or Regime Shifts.
* **Requirements:** Slides must include relevant definitions and formulas, draw a direct connection to the analyzed data, and explicitly show how the chosen mathematical method resolved the specific financial challenge.