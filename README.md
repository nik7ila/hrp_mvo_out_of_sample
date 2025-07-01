# hrp_mvo_out_of_sample
# Out-of-Sample Evaluation: HRP vs MVO Portfolio Performance

##  Objective

This study evaluates how two portfolio strategies perform **on future unseen data** (out-of-sample). The aim is to test **generalization** — whether a strategy that performs well in training data continues to do so in real market conditions.



##  Setup

- **Training Period**: Jan 2015 – Dec 2021  
- **Testing Period**: Jan 2022 – Jan 2025  
- **Assets**: AAPL, AMZN, DIS, TSLA  
- **Optimization Methods**:  
  - MVO (Mean-Variance Optimization)  
  - HRP (Hierarchical Risk Parity)

Each strategy was fit on **training data only**, and the resulting portfolio weights were used to simulate **test-period performance**.


## Out-of-Sample Results

**Growth of $1 Invested (2022–2025)**

From the plot (`out_of_sample_returns.png`):

- **MVO** achieved higher peak returns, but with greater fluctuations.
- **HRP** delivered smoother growth and lower volatility.

**Key Metrics (Out-of-Sample)**


| Metric               | MVO    | HRP    |
| -------------------- | ------ | ------ |
| Cumulative Return    | 25.65% | 3.09%  |
| Annual Return (CAGR) | 38.95% | 15.15% |
| Annual Volatility    | 31.95% | 23.67% |
| Sharpe Ratio         | 1.22   | 0.64   |
| Max Drawdown         | 65.52% | 42.61% |



##  Interpretation

| Insight | Observation |
|--------|-------------|
| **MVO** | Higher returns, but also exposed to market swings. |
| **HRP** | More balanced, with smaller drawdowns and smoother path. |
| **Risk Management** | HRP’s diversification through clustering shows stronger stability during volatile phases. |
| **Forecast Dependency** | MVO’s sensitivity to forecast errors affected out-of-sample resilience. |



## Consultant Takeaway

> “When markets behave as forecasted, MVO wins. But when uncertainty rises, HRP survives.”

In real-world asset management:
- **Consistency** often beats **max return**.
- Robust strategies like HRP offer peace of mind through lower risk exposure.
- Portfolio selection should consider **client risk profile**, **market regime**, and **long-term goals**.



##  Files Included

- `hrp_mvo_out_of_sample.ipynb` — Full test notebook  
- `plots/` — Return chart  
- `hrp_mvo_out_of_sample/README.md` — This file  



##  Suggested Next Steps

- Conduct **rolling-window backtests** for better robustness checks.
- Compare with **Volatility Weighted (VW)** and **Risk Parity** approaches.
- Prepare a presentation deck for client-facing summary.

