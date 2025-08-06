Stock Market Strategy: First Candle High Breakout
=================================================

![Alt text](Assets/Images/Github_banner.jpg)

A Python-powered intraday trading project for the NSE 50 index, leveraging a simple and systematic breakout strategy, historical data analysis, and automation potential. This repository is intended for **educational use only**.

Project Overview
----------------

*   **Goal**: Earn passive income through systematic trading.
    
*   **Scope**: Formulate, test, and automate an intraday trading strategy using minute-level data.
    

Strategy Summary
----------------

*   **Reference Point**: The _first candle high_ of the trading day (using 1min, 2min, or 5min data).
    
*   **Entry Rule**: Enter a long position when any subsequent candle's open is above the first candle's high.
    
*   **Exit Rules**:
    
    *   **Target**: Exit when price reaches a set profit target.
        
    *   **Stop Loss**: Exit if price falls to a specified loss limit.
        
*   **Customization**: Choose target and stop loss based on risk appetite (aggressive vs. conservative).
    

Data
----

*   **Primary Source**: Kaggle (minute-level OHLCV data for NSE 50 index).
    
*   **Acquisition**: Automated script collects 1min candle data sequentially for a 1-year period.
    
*   **Features**:
    
    *   OHLCV (Open, High, Low, Close, Volume)
        
    *   Engineered: risk/reward, success ratio
        

Methodology
-----------

1.  **Parameterized Backtesting**:
    
    *   Test all combinations of target (T) and stop loss (SL) within a grid.
        
    *   For each day:
        
        *   Group and loop through minute-level data.
            
        *   Only one trade per day.
            
        *   Results in 361 (19×19) T/SL combinations tested per period.
            
2.  **Performance Metrics**:
    
    *   **Profit Days**
        
    *   **Win Ratio**
        
    *   **Risk-Reward outcomes**
        
    *   **Optimal settings for risk appetite**
        
3.  **Approaches**:
    
    *   Manual loop-based grid search for T/SL optimization.
        
    *   Machine Learning analysis based on results.
        

Findings
--------

*   **Aggressive**: T = 70, SL = 35 (risk/reward 2:1, 53% success rate)
    
*   **Conservative**: T = 20, SL = 30 (risk/reward <1, 80% success rate)
    
*   **Tradeoff**: Higher targets yield bigger gains but lower win rate; Lower targets hit more consistently.
    
## Click here to the Notebook -> [Link](Assets/stock_strategy_final.ipynb)

Automation
----------

*   **Python Implementation**: End-to-end pipeline for data cleaning, backtesting, and analytics.
    
*   **Broker Integration**: Scripts can be extended to APIs (e.g., Zerodha Connect) for live trading automation.
    

Project Structure
-----------------

*   data/ : Scripts and pointers for dataset acquisition
    
*   notebooks/ : Analysis and exploratory notebooks
    
*   src/ : Strategy and backtest engine
    
*   results/ : Backtest outputs and visualizations
    
*   README.md : Project documentation
    

How To Use
----------

1.  Install Python dependencies (see requirements.txt)
    
2.  Download/train/test using provided Kaggle dataset instructions.
    
3.  Modify parameters in the configuration file/script to experiment with different target and stop loss values.
    
4.  Run strategy/backtest scripts for different timeframes or assets.
    

Considerations & Recommendations
--------------------------------

*   Dataset applies to **NSE 50 index**; can be adapted for other stocks.
    
*   For deeper historical data, consider a premium API (e.g., Zerodha).
    
*   Test with as much data as your resources allow before live trading.
    
*   **No financial advice** – this is a research & learning tool.
    

Disclaimer
----------

> This project is for **educational purposes** only. Trading involves risk. Use the code and strategies at your own discretion. The author assumes **no liability** for financial losses incurred.

Feedback & Contributions
------------------------

Feel free to open Issues or Pull Requests for features, improvements, or requests (e.g., shorting strategies).

_Happy trading and learning!_
