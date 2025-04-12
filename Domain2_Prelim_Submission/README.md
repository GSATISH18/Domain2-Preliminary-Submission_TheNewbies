# Domain2-Preliminary-Submission_TheNewbies  
UMHackathon 2025 – Domain 2: Quantitative Trading (Balaena Quant)

---

## 🧠 Team Name: THE NEWBIES

---

## 1. 🧭 Overview

This is our conceptual design for a **modular backtesting framework** that supports the development and evaluation of ML-driven crypto trading strategies — specifically targeting **BTC/ETH** pairs. The system emphasizes flexibility, on-chain signal integration, and practical performance tracking.

It includes:

- ✅ Data integration from major on-chain sources  
- ✅ Machine Learning strategy module (HMM-based)  
- ✅ Custom backtest engine with Sharpe & drawdown evaluation  

This framework is designed to be extended in the final round to work with real-time APIs and additional ML models.

---

## 2. 🧱 Architecture 

The framework is divided into 7 key components:

### 1. **Data Sources** (🔵 Blue)
- On-chain and off-chain metrics from:
  - **CryptoQuant**: Whale inflows/outflows, reserves  
  - **Glassnode**: Network indicators  
  - **Coinglass**: Long/short ratios, funding rates  

### 2. **API Layer (Cybotrade)** (⚪️ Grey)
- Connects to the **Cybotrade API** (REST/WebSocket)  
- Standardized access to historical and live data  
- Supports multi-source integration

### 3. **Preprocessing** (⚪️ Grey)
- Data normalization and alignment  
- Feature engineering:
  - Rolling mean  
  - Volatility  
  - L/S ratio  

### 4. **ML Module – HMM** (🟠 Orange)
- Applies **Hidden Markov Model** to detect hidden market regimes:  
  - State 1: Bullish  
  - State 2: Bearish  
  - State 3: Neutral  
- Translates time-series features into market state predictions  

### 5. **Signal Generator** (⚪️ Grey)
- Maps market states to trading signals:  
  - Bullish → Buy  
  - Bearish → Sell  
  - Neutral → Hold  

### 6. **Backtest Engine** (🟢 Green)
- Simulates trades based on generated signals  
- Incorporates:
  - Historical candle data  
  - Trading fee (0.06%)  
- Calculates:
  - Portfolio returns  
  - Drawdowns  
  - Sharpe Ratio  
  - Trade frequency  

### 7. **Visualizer** (⚪️ Grey)
- Outputs:
  - Equity curve  
  - Sharpe Ratio  
  - Drawdown chart  
  - Trade markers  

---

## 3. 📊 Proposed Strategy

We propose using an **HMM-based regime detection model** trained on a mixture of on-chain indicators (like whale inflows and funding rates) and price-derived features (returns, volume spikes).

Each hidden market state corresponds to a discrete signal:
- **Bullish (State 1):** Long entry (Buy)  
- **Bearish (State 2):** Exit or Short (Sell)  
- **Neutral (State 3):** No trade (Hold)

This approach is robust in adapting to structural volatility in the crypto markets.

---

## 4. 🧪 Evaluation Metrics

We aim to meet the following quantitative thresholds during simulation and live testing:

| Metric           | Target             |
|------------------|--------------------|
| **Sharpe Ratio** | ≥ 1.8              |
| **Max Drawdown** | ≥ -40%             |
| **Trade Frequency** | ≥ 3 trades/week |
| **Win Rate**     | *Optional*         |
| **Profit Factor**| *Optional*         |

---

## 5. 🔮 Future Work (For Finals)

- Integrate with **live Cybotrade API endpoints**  
- Collect and store **real BTC/ETH multi-year data**  
- Build alternative ML strategies (LSTM, hybrid HMM-XGBoost)  
- Add an auto-optimization module for parameter tuning  
- Develop a **web dashboard** for visual trade monitoring

---

**Submitted by: THE NEWBIES**  
*(Duo Preliminary Submission – UMHackathon 2025 | Balaena Quant – Domain 2)*                                                                                                         
*[It's not in out scope of experty,but we will learn  and try to make our idea happen.]*
