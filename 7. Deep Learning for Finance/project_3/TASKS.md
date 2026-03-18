# Project Roadmap & Status

This document outlines the step-by-step implementation plan for the "Deep Learning for Finance" project, tracking progress from data acquisition to the final robust backtesting pipeline.

## ✅ Step 1: Data Acquisition & Initial Modeling (Leakage Induced)
- [x] **1a. Data Gathering**: Fetched daily `BTC-USD` data (Jan 2018 - Jan 2024) via Yahoo Finance and truncated to the most recent 2,000 observations.
- [x] **1b. Feature Engineering & Leakage**: Created binary target labels (Next Day Return > 0). **Intentionally induced leakage** by applying `StandardScaler` to the entire dataset before splitting.
- [x] **1c. Model Architecture**: Implemented three Deep Learning models:
    - Multi-Layer Perceptron (MLP)
    - Long Short-Term Memory (LSTM)
    - Convolutional Neural Network (CNN) using Gramian Angular Fields (GAF).
- [x] **1d. Initial Backtest**: Performed a vectorized backtest on an 80/20 train/test split.
    - *Result:* MLP achieved ~52.78% accuracy (with leakage).

## ✅ Step 2: Walk-Forward Validation (With Leakage)
- [x] **2a. Walk-Forward (500/500)**: Implemented a Non-Anchored Walk-Forward validation with Train=500 / Test=500.
    - *Result:* Performance dropped to ~49-50% for most models.
- [x] **2b. Walk-Forward (500/100)**: Implemented a Non-Anchored Walk-Forward validation with Train=500 / Test=100.
    - *Result:* Accuracy improved significantly (MLP ~52.86%), confirming that shorter test windows benefit from the leaked global statistics.
- [x] **2c/2d. Analysis**: Confirmed that the "edge" in Step 2b was largely due to **backtest overfitting via leakage**.

## ✅ Step 3: Leakage Mitigation & Robust Backtesting
- [x] **3a. Pipeline Design**: Designed a strict **No-Leakage Pipeline** where scaling and GAF transformation occur *inside* the cross-validation loop, using only training fold statistics.
- [x] **3b. Robust Walk-Forward (500/500)**: Re-ran the validation with the leakage-free pipeline.
- [x] **3c. Robust Walk-Forward (500/100)**: Re-ran the validation with the leakage-free pipeline.
    - *Result:* Accuracy converged to random chance (~50%), proving that the earlier success was illusory.
- [x] **3d. Final Conclusion**: Documented the disappearance of the "predictive edge," validating the Efficient Market Hypothesis for this specific technical setup.

## ✅ Step 4: Reporting & Documentation
- [x] **Code Organization**: Cleaned and optimized Jupyter Notebooks.
- [x] **Final Report**: Compiled a comprehensive 30+ page technical report analyzing Overfitting, Leakage, and Model Architectures.
- [x] **Repository Setup**: Created `README.md`, `TASKS.md`, and `requirements.txt`.