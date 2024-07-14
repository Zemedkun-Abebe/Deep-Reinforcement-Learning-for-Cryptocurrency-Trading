## Reinforcement Learning for Cryptocurrency Trading

**Authors:** Zemedkun Abebe, Bekalu Tamrat

**Date:** July 14, 2024

**Abstract**

This project explores the development and evaluation of a reinforcement learning (RL) agent for cryptocurrency trading, focusing on the Bitcoin market. We detail data collection, feature engineering with technical indicators, a custom trading environment, and RL model training using Proximal Policy Optimization (PPO). The results highlight the potential and limitations of the trained agent in a simulated trading environment.

**1. Introduction**

This project, undertaken for a Reinforcement Learning course, investigates applying RL techniques to cryptocurrency trading. The goal is to build an agent that makes profitable decisions based on historical market data.

**2. Data Preparation**

**2.1. Data Collection**

Historical Bitcoin-USDT trading data was collected from Binance's API. This minute-level data includes OHLCV (Open, High, Low, Close, Volume) and additional features like mark price and technical indicators.

**2.2. Feature Engineering**

To enrich the dataset, we calculated various technical indicators:

* **Mark Price:** Used for margin calculations and liquidation.
* **VWAP (Volume Weighted Average Price):** A trading benchmark reflecting average price based on volume.
* **EMA (Exponential Moving Average):** Calculated for 12 and 26 periods.
* **MACD (Moving Average Convergence Divergence):** Difference between 12-period and 26-period EMA.
* **RSI (Relative Strength Index):** Measures the speed and change of price movements.
* **ROC (Rate of Change):** Measures percentage change between current and past prices.
* **OBV (On-Balance Volume):** A momentum indicator using volume flow to predict price changes.
* **ATR (Average True Range):** A measure of market volatility.
* **Lagged Mark Prices:** Capture recent price trends.

Additionally, time-based features (day of the week, hour of the day) and holiday indicators were incorporated for contextual trading decisions.

**3. The Trading Environment**

A custom trading environment was built using OpenAI's Gym framework to simulate the trading process. The agent interacts with this environment, taking actions and receiving rewards based on its performance. Key components include:

* **Initial Balance:** Starting capital.
* **Leverage:** Amount of borrowed funds used for trading.
* **Transaction Fee:** Cost associated with each trade.
* **Action Space:** Possible actions (buy, sell, hold).
* **Observation Space:** Features available to the agent at each time step.
* **Reward Structure:** Calculated based on profit/loss from trades, adjusted for transaction fees.

**4. Training the RL Model**

**4.1. Algorithm Selection**

We chose the PPO algorithm due to its robustness and stability in continuous action spaces. PPO is well-suited for complex, high-dimensional state spaces like financial markets.

**4.2. Training Process**

The training process involved normalizing the dataset and using a vectorized environment for faster learning. The model was trained for 900,000 timesteps. Key training metrics like KL divergence, entropy loss, and value loss provided insights into the model's learning dynamics.

**5. Testing and Evaluation**

**5.1. Performance Evaluation**

The trained agent was evaluated in the same environment. We recorded its actions (buy, sell, hold) and the resulting balance over time. The total reward and sequence of actions were used to assess the agent's trading strategy.

**5.2. Results**

The agent maintained the balance close to the initial amount with minor fluctuations, indicating a cautious strategy. However, it did not demonstrate significant profitability, suggesting the need for further tuning and exploration of different strategies.

**6. Discussion**

**6.1. Challenges**

Several challenges were encountered during the project:

* **Data Quality:** Ensuring the reliability and completeness of historical data.
* **Feature Selection:** Choosing the most relevant features and technical indicators.
* **Hyperparameter Tuning:** Finding the optimal hyperparameters for the PPO algorithm.

**6.2. Future Work**

Future improvements could include:

* **Advanced Feature Engineering:** Incorporating additional features and alternative technical indicators.
* **Risk Management:** Implementing advanced strategies to protect capital.
* **Model Enhancements:** Exploring other RL algorithms and architectures.

**7. Conclusion**

This project demonstrated the application of reinforcement learning to cryptocurrency trading. While the initial results were modest, the established framework provides a foundation for further exploration and improvement. The combination of technical indicators and RL holds promise for developing sophisticated trading strategies.
