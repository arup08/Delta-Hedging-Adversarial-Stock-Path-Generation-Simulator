🏦 Delta Hedging & Adversarial Stock Path Generation Simulator

An end-to-end quantitative finance simulator for European option delta hedging, featuring traditional mathematical models and advanced deep learning-based hedging strategies. 

## 📊 Project Overview
This project simulates dynamic delta hedging for short European call options. It compares traditional Black-Scholes hedging against a custom Neural-Network (LSTM) hedger across multiple market scenarios, including Geometric Brownian Motion (GBM), stress conditions, and adversarial paths.

> **Key Result:** The PyTorch-based LSTM hedger achieves **78% tighter VaR** and **76% lower CVaR** compared to traditional Black–Scholes delta hedging.

## 🛠 Technologies & Tools
* **Python** 
* **PyTorch** (LSTM Neural Networks, Autograd for Adversarial Generation)
* **NumPy & Pandas** (Data manipulation)
* **SciPy** (Statistical functions)
* **Matplotlib & Seaborn** (Data visualization)

## 🚀 Key Features

* **Black–Scholes Analytical Engine:** Computes pricing, Greeks (Δ, Γ, ν, Θ), and includes a fast Newton-Raphson Implied Volatility solver.
* **Three Stock Path Generators:**
  1. **GBM (Geometric Brownian Motion):** Standard log-normal baseline.
  2. **Stress Scenarios:** Combines Merton Jump-Diffusion with Ornstein-Uhlenbeck Stochastic Volatility for fat tails and volatility clustering.
  3. **Adversarial Generation:** Uses PyTorch autograd to learn worst-case market paths that maximize Black-Scholes hedging errors.
* **Discrete-Time Hedging Engine:** Simulates 50–252 rebalancing steps per path, accounting for both fixed and proportional transaction costs.
* **Deep Learning Hedger:** A 2-layer LSTM trained to output optimal hedge ratios by minimizing the Conditional Value-at-Risk (CVaR).
* **NIFTY-50 Calibration:** Out-of-the-box parameters calibrated to the Indian NIFTY-50 index, with optional auto-calibration from real tick data.

## 📈 Visualizations
The simulator generates a suite of publication-quality plots, including:
* Simulated Price Paths (GBM, Stress, Adversarial)
* P&L Distributions (BS vs. LSTM)
* Hedging Error vs. Rebalancing Frequency
* Transaction Cost Impact
* Risk Metrics Comparisons (VaR, CVaR, Max Loss, Skewness, Kurtosis)

## 💻 How to Run
1. Clone this repository.
2. Install the required dependencies: `pip install numpy pandas torch scipy matplotlib seaborn`
3. Run the Jupyter Notebook cell by cell to generate the paths, train the LSTM, and output the risk analysis plots (saved automatically to a `plots/` directory).
4. *(Optional)* Place NIFTY-50 minute-level CSV data in the root directory for real-world calibration.
