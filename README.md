# quant-robot : Deep Learning for Quantitative Research

## Project Overview
This project is designed to introduce the principles of quantitative research using deep learning. 
*Goal* : Build a recurrent neural network (RNN) or long short-term memory (LSTM) model that predicts price movements of a selected stock (S&P 500, Tesla, or Airbus). 
The model will make continuous trading decisions based on live financial data pulled from an API. The key objective is to allow the algorithm to trade autonomously so that it is globally neutral / profitable (hypothesis that trading will not impact the market, which is a conservative one considering that the amounts traded will be small)

## Objectives
- **Deep Learning Introduction**: Hands-on experience with RNN/LSTM architectures for time-series prediction, which I have never implemented in the past.
- **Quantitative Research**: Understanding how to apply financial data analysis using AI models - choice of features exterior to financial series (FOREX, industry verticals & horizontals, etc...)
- **Trading Strategy**: Create a model that is profitable 51% of the time, ensuring more winning than losing trades (Ambitious but the goal will be to optimize it as much as possible).
- **More realistic goal**: Create a model that performs better than a baseline model (Ouverture, Renforcement/Scaling in, Pyramiding, Stop Loss, Take Profit)

## Key Metrics
- **Win Rate**: Aim for a trading strategy performing better than the baseline model. If that goal is achieved, use the 51% profitability metric.
- **Capital Gain/Loss**: Algorithm stops once it either gains 10% or loses 50% of the initial capital.
- **Trade Frequency**: Trades should execute with a maximum duration of 6 hours between each - so that I can run the algorithm on a side computer

## Pipeline
1. **Data Collection**: Continuously retrieve price data from a financial API for a chosen stock.
2. **Preprocessing**: Clean and normalize the data to reduce noise and avoid overfitting using classic financial/quant methods (not yet defined or clear, but the goal is not to overfit on noisy data)
3. **Modeling**: Develop an RNN & LSTM model for predicting price movements based on historical and real-time data, and compare the performances with a baseline algorithm (buy after drop, sell after increase)
4. **Trading Algorithm**: The model will generate buy/sell signals and execute trades based on its predictions

## Requirements
- Python 3.11.7
- TensorFlow for model development → Library I am most familiar with as I have developped many NNs in the past (MLP mainly)
- Financial API (e.g., Alpha Vantage, Yahoo Finance) for continuous data retrieval → Benchmark to see which one is easiest to use
- Pandas, NumPy for data manipulation → Classic libraries for better 
- Matplotlib/Seaborn for visualization → Classic libraries 

## Questions
- **Financial Data**: How reliable and clean is the data from the chosen API? How does the model handle missing data or anomalies? → Consulting benchmarks to see which one to choose & how easy they are to use
- **Overfitting**: What measures are in place to prevent overfitting on short-term price movements or noise in the market? → Data processing (Academic research to see which methods are most used)
- **Model Architecture**: Why choose RNN or LSTM over other models like GRU or Transformer for time-series prediction? → Tradeoff based on computer resources (as I have a 5-years-old GPU)
- **Risk Management**: What risk management strategies should be implemented to protect against significant losses in real trading scenarios? → Minimize risks, maximize profits. Will use classic hard-coded limits such as stop losses and take profits
- **Trade Frequency**: How does the 6-hour trade frequency impact the algorithm's performance compared to more frequent or less frequent trades? → Hyperparameters to optimize for better profitability rates
- **Market Conditions**: How does the model adapt to different market conditions (bull, bear, high volatility)? → I will target the Bull market. Arbitrary choice because of many common rising indices such as the S&P500, Dow Jones and other benchmarks. Plus, it has positive sentiment and price usually rise steadily.
- **Practical Applications**: What are the broader applications of this algorithm in quantitative finance? Could it be scaled to trade across multiple assets or markets? → Because of the task's complexity, I will choose a defined set of actions on which I will train my model. the algorithm will be able to trade on those actions only. However, in terms of features and data, I will consider adding more features to have better the results (in phase two only though)

## License
MIT License
