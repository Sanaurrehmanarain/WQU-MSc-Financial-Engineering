## Step 1 — Time Series Analysis and Stationarity

### 1(a) Price Level Series (AAPL adjusted close)
- Download AAPL daily adjusted close prices (≤ 2000 observations)
- Visualize price level series
- Summary statistics (count, mean, std, quantiles, skewness, excess kurtosis)
- Stationarity testing:
  - ADF test
  - KPSS test
- Autocorrelation diagnostics:
  - ACF plot
  - PACF plot
- Rolling mean and rolling standard deviation plots

**Deliverables**
- Figures: levels line plot, histogram, rolling mean/std, ACF, PACF
- Tables: summary stats + ADF/KPSS outputs

---

### 1(b) Stationary Transform: Log Returns
- Compute log returns:  \( r_t = \ln(P_t) - \ln(P_{t-1}) \)
- Visualize log returns
- Summary statistics + distribution inspection
- Stationarity testing (ADF + KPSS)
- ACF/PACF for log returns

**Deliverables**
- Figures: returns plot, histogram, ACF, PACF
- Tables: summary stats + ADF/KPSS outputs

---

### 1(c) Fractional Differencing (Fixed-Width)
- Implement fractional differencing
- Grid search over \( d \in [0, 1] \)
- Select \( d \) using:
  - ADF p-value threshold
  - minimum observations retained (≥ 1000)
  - preference for smaller \( d \) + higher correlation with levels
- Compute final fracdiff series

**Deliverables**
- Table: grid search results (`res_df`)
- Selection summary (selected d, obs retained, ADF/KPSS, corr with levels)

---

### 1(d) Final Diagnostic Comparison Table
- Build a single table comparing:
  - Levels
  - Log returns
  - FracDiff(d=selected)
- Include:
  - n_obs
  - ADF p-value
  - KPSS p-value
  - mean, std, skew, excess kurtosis

**Deliverables**
- Table: representation comparison diagnostics

---

## Step 2 — MLP Forecasting (Lag Features)

### 2(a) Predict Levels
- Create lag features (p = 20)
- Chronological train/val/test split
- Train MLP with early stopping
- Evaluate: RMSE, MAE, R²
- Plot: test prediction line + training curve

### 2(b) Predict Log Returns
- Same pipeline for log returns
- Evaluate and plot results

### 2(c) Predict Fractionally Differenced Series
- Same pipeline for fracdiff series
- Evaluate and plot results

### 2(d) Compare MLP Performance Across Representations
- Build `mlp_compare` table
- RMSE comparison bar chart

**Deliverables**
- Figures: 3 test prediction plots + 3 training curves + RMSE comparison
- Table: `mlp_compare`
- CSV: `step2_mlp_results.csv`

---

## Step 3 — CNN Forecasting with GAF Images

### 3(a) Predict Levels using CNN (GAF + scalar context)
- Create windows (W = 32)
- Convert windows to GAF images (summation)
- Add scalar context: last observed value
- Multi-input CNN (image branch + scalar branch)
- Train with early stopping
- Evaluate: RMSE, MAE, R²
- Plot: sample GAF, test prediction plot, training curve

### 3(b) Predict Log Returns using CNN (GAF + scalar)
- Same pipeline on returns

### 3(c) Predict Fractionally Differenced Series using CNN (GAF + scalar)
- Same pipeline on fracdiff

### 3(d) Compare CNN Performance Across Representations
- Build `cnn_compare` table
- RMSE comparison bar chart

**Deliverables**
- Figures: sample GAF images (3), test prediction plots (3), training curves (3), RMSE bar chart
- Table: `cnn_compare`
- CSV: `step3_cnn_gaf_scalar_results.csv`

---

## Step 4 — MLP vs CNN Comparative Analysis
- Merge Step 2 and Step 3 metrics
- Produce a combined comparison table
- Plot RMSE by model (per representation)
- Plot R² by model (per representation)

**Deliverables**
- Table: `step4_mlp_vs_cnn_comparison.csv`
- Figures: RMSE comparison plots + R² comparison plots

---

## Final Deliverables
- Full professional report (MS Word) with:
  - methodology, results, discussion, conclusions
  - APA 7 in-text citations + references
  - all figures and tables with captions
- Repository documentation:
  - `README.md`
  - `TASKS.md`
  - `requirements.txt`
