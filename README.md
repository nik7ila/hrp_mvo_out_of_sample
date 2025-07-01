# hrp_mvo_out_of_sample
# Out-of-Sample Portfolio Comparison: MVO vs HRP

## Project Objective

This notebook evaluates **Minimum Variance Optimization (MVO)** and **Hierarchical Risk Parity (HRP)** portfolio strategies on **out-of-sample data**, simulating a more realistic scenario where strategies are trained on historical data and tested on unseen market conditions. The goal is to assess which method is more robust and consistent in real-world, out-of-sample performance.


## ⚙️ Methodology

1. **Train-Test Split**:
   - **Training Period**: Historical price data used to compute weights.
   - **Testing Period**: Subsequent period used to simulate actual portfolio performance.

2. **Strategy Implementation**:
   - **MVO**: Allocates weights to minimize portfolio variance using covariance matrix and expected returns.
   - **HRP**: Uses hierarchical clustering to allocate capital based on risk structure without requiring matrix inversion.

3. **Backtesting**:
   - Each portfolio was rebalanced using the weights derived from the training set and applied to the test data.
   - Results were analyzed through cumulative returns and risk-adjusted metrics.

---

## 📊 Performance Metrics
[Cumulative Returns : Out of sample]('plot/mvo_hrp_outofsample.png')

[Comparision Metrics]('plot/comp_metrics.png')

| Metric                  | MVO     | HRP     |
|-------------------------|---------|---------|
| Cumulative Return       | 0.51    | 0.13    |
| Annual Return (CAGR)    | 0.15    | 0.04    |
| Annual Volatility       | 0.36    | 0.27    |
| Sharpe Ratio            | 0.42    | 0.15    |
| Max Drawdown            | -0.52   | -0.46   |

> 📉 Despite outperforming in-sample, MVO shows **significantly reduced performance** in the out-of-sample period. HRP, while more conservative, appears to be **more stable and robust**, especially under volatility and structural changes.

---

## 🧠 Key Learnings

- **In-Sample ≠ Real-World**: MVO may look superior in-sample but suffers from high sensitivity to input errors, particularly expected returns.
- **HRP’s Strength**: HRP avoids inverting the covariance matrix, which makes it **less sensitive to estimation noise** and better suited for out-of-sample robustness.
- **Sharpe vs Drawdown**: Although MVO had a higher Sharpe, it also experienced higher drawdowns. HRP maintained **better capital preservation**.

---

## 🧪 Tools & Libraries

- `pandas`, `numpy`, `matplotlib`, `seaborn`
- `scikit-learn` for clustering (HRP)
- `cvxpy` for MVO optimization

---

## 💼 Consultant Insights

In a professional setting, this study shows the importance of validating portfolio strategies not just on historical performance, but in forward-looking simulations. While MVO may impress in backtests, HRP provides a **more dependable framework** under uncertainty, which aligns better with risk-conscious investment mandates.

---

## 🔄 Next Steps

- Expand the out-of-sample period for a longer validation.
- Incorporate **rolling rebalancing** and **transaction costs**.
- Compare other risk-based methods such as **Risk Parity** or **Volatility Weighted** portfolios.

---

## 🤖 AI-Assisted Workflow

This project leveraged AI tools to:
- Understand core differences between MVO and HRP.
- Debug and correct optimization pipeline issues.
- Interpret results from a consultant-friendly perspective.

---

