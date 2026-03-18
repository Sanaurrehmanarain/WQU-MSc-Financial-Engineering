# Deep Learning for Finance: Analysis of Overfitting & Data Leakage

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![TensorFlow](https://img.shields.io/badge/TensorFlow-2.x-orange)
![Status](https://img.shields.io/badge/Status-Completed-green)

## 📌 Project Overview
This project investigates the application of Deep Learning architectures—**MLP, LSTM, and CNN (GAF)**—to predict the directional returns of Bitcoin (BTC-USD).

The core objective is not merely prediction, but a rigorous **forensic analysis of Data Leakage** in financial machine learning. We demonstrate how improper preprocessing (Global Scaling) can artificially inflate backtest performance and how a robust **Walk-Forward Validation** pipeline exposes these flaws.

## 🚀 Key Features
* **Multi-Model Approach:** Comparative analysis of dense (MLP), recurrent (LSTM), and image-based (CNN-GAF) neural networks.
* **Gramian Angular Fields:** Novel application of converting time-series data into images for CNN processing.
* **Leakage Simulation:** Deliberate injection of "Look-Ahead Bias" to demonstrate common backtesting pitfalls.
* **Robust Validation:** Implementation of a strict, leakage-free Non-Anchored Walk-Forward Validation pipeline.

## 📊 Results Summary
Our analysis reveals a critical insight for algorithmic trading:
| Scenario | MLP Accuracy | Observation |
| :--- | :--- | :--- |
| **Step 1 (Static Split + Leakage)** | **52.78%** | Apparent predictive edge. |
| **Step 2 (Walk-Forward + Leakage)** | **52.86%** | "Edge" persists with frequent retraining. |
| **Step 3 (Robust No-Leakage)** | **49.93%** | **Edge disappears.** Returns to random chance. |

**Conclusion:** The initial success was driven by **backtest overfitting**. When strictly isolated, historical price data alone provided no consistent signal for the test period.

## 🛠️ Installation & Usage

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/yourusername/dl-finance-leakage.git](https://github.com/yourusername/dl-finance-leakage.git)
    cd dl-finance-leakage
    ```

2.  **Install dependencies:**
    ```bash
    pip install -r requirements.txt
    ```

3.  **Run the Analysis:**
    Open the Jupyter Notebook to replicate the experiments:
    ```bash
    jupyter notebook "Deep_Learning_Finance_Project.ipynb"
    ```

## 📂 Repository Structure
* `Deep_Learning_Finance_Project.ipynb`: The main codebase containing all steps (Data, Models, Backtesting).
* `TASKS.md`: Project roadmap and completion status.
* `requirements.txt`: Python dependencies.
* `outputs/`: Folder containing generated plots (Price History, Cumulative Returns, Accuracy Comparisons).

## 📚 Methodological References
* **Models:** Multi-Layer Perceptron, Long Short-Term Memory, CNN (Gramian Angular Field).
* **Validation:** Non-Anchored Walk-Forward Validation (Rolling Window).
* **Data:** Yahoo Finance API (BTC-USD, Daily, 2018-2024).

---
*Author: Sana Ur Rehman Arain*

*Date: October 2023*