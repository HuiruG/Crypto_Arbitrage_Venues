# High-Frequency Crypto Market Microstructure & Basis Arbitrage
**Author:** Dr. Gao (Finance, University of Birmingham)  
**Project Focus:** Price Discovery Dynamics, Lead-Lag Relationships, and Systematic Arbitrage.

## 📌 Project Overview
This repository hosts an advanced analytical framework designed to dissect market microstructure within the cryptocurrency domain. Unlike simplistic backtesters, this project focuses on **informational efficiency** and **structural identification** across fragmented liquidity venues (Binance, Gate.io, etc.).

The core objective is to identify how price information propagates through the Limit Order Book (LOB) and leverage these insights for cross-venue basis and funding rate arbitrage.

## 🔬 Core Analytical Modules

### 1. Structural Identification & Price Discovery
Using high-frequency LOB data, this module implements:
* **Information Share (Hasbrouck) & Component Share (Gonzalo-Granger):** Quantifying which exchange leads the price discovery process.
* **VECM (Vector Error Correction Model):** Modeling the long-term equilibrium (cointegration) between spot and perpetual futures prices.
  $$\Delta P_t = lpha eta' P_{t-1} + \sum_{i=1}^k \Gamma_i \Delta P_{t-i} + \epsilon_t$$
* **Lead-Lag Analysis:** Utilizing Cross-Correlation Functions (CCF) to identify microsecond-level latency advantages.

### 2. Basis & Funding Rate Arbitrage Engine
A systematic strategy builder that targets:
* **Dynamic Basis Convergence:** Capturing the spread between $P_{perp}$ and $P_{spot}$.
* **Predictive Funding Rate Modeling:** A regime-switching approach to forecast next-period funding costs, optimizing the entry/exit timing for delta-neutral positions.
* **Execution Edge:** Backtesting with realistic LOB slippage, taker/maker fee structures, and market impact modeling.

### 3. High-Frequency Backtester
* **Granularity:** Support for 100ms interval data processing.
* **Realism:** Accounting for exchange-specific liquidation thresholds and latency jitter.

## 🛠 Tech Stack
* **Language:** Python 3.x
* **Data Engineering:** `pandas`, `numpy`, `CCXT` for API integration.
* **Econometrics:** `statsmodels`, `arch` (for GARCH volatility modeling).
* **Visualization:** `Plotly` / `Matplotlib` for PnL and Spread analysis.

---

## 📈 Key Insights (Sample)
> *Refining the 'Who Leads, Who Follows' section revealed that during high-volatility regimes, Binance Perpetual markets exhibit a 65% Information Share, leading spot markets by approximately 200-500ms.*

---

## 🚀 Future Roadmap
- [ ] Integration of Transformer-based LOB sequence prediction.
- [ ] Multi-asset portfolio optimization under liquidity constraints.
- [ ] Real-time execution via Websocket connectors.

---
**Disclaimer:** This is an academic and professional research project. Trading involves significant risk. As Nietzsche once said, "If you gaze long into an abyss, the abyss also gazes into you"—especially if that abyss is a 50x leveraged perpetual contract.

📩 Contact: hxg17880@gmail.com | Dr. Gao @ UoB
