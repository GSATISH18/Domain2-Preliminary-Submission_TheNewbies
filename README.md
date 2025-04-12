# Domain2-Preliminary-Submission_TheNewbies
UM hackathon 2025

README: Domain 2 Preliminary Submission – Balaena Quant
Team Name: THE NEWBIES
1. Overview
This is a conceptual framework for a modular backtesting library focused on quantitative crypto trading, specifically for BTC/ETH pairs. The framework includes:

- API integration (Cybotrade)
- Custom ML-based signal generation
- Strategy simulation and performance evaluation
2. Architecture (See attached diagram)
The framework has the following modules:

1. Data Sources
   Pull on-chain and off-chain market indicators from:
   - CryptoQuant (whale inflow/outflow, exchange reserves)
   - Glassnode (network metrics)
   - Coinglass (long/short ratio, funding rates)

2. API Layer (Cybotrade)
   Connects to Cybotrade’s API for real-time or backtesting order execution. Follows OpenAPI standards.

3. Preprocessing
   - Clean and normalize data
   - Feature engineering: rolling mean, volatility, L/S ratio

4. ML Module (HMM)
   Hidden Markov Model is used to detect latent market states:
   - Bullish (State 1)
   - Bearish (State 2)
   - Neutral (State 3)

5. Signal Generator
   Based on current state:
   - Bullish → Buy
   - Bearish → Sell
   - Neutral → Hold

6. Backtest Engine
   - Simulate historical performance
   - Calculate performance metrics

7. Visualizer
   - Sharpe Ratio
   - Drawdown
   - Trade frequency
   - Equity curve
3. Proposed Strategy
Use Hidden Markov Models to detect shifts in crypto market regimes. Generate Buy/Sell signals based on transition probabilities.

Key Goals:
- Sharpe Ratio ≥ 1.8
- Maximum Drawdown ≥ -40%
- Trade frequency ≥ 3x / week
4. Evaluation Metrics
Metric
Target
Sharpe Ratio
≥ 1.8
Max Drawdown
≥ -40%
Weekly Trade Freq
≥ 3
Win Rate
Optional
Profit Factor
Optional
5. What Makes It Unique?
- Combines on-chain data, ML models, and API-ready execution
- Uses interpretable HMM states to build explainable signals
- Simple enough to implement, scalable enough to improve
6. Next Steps (Finals)
- Implement minimal version of the backtest engine in Python
- Train/test the HMM on BTC/ETH price data
- Use Cybotrade API to simulate execution
- Improve signal rules via reinforcement learning
