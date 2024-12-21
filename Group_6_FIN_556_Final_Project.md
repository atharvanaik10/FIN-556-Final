Introduction

The objective of this report is to evaluate the performance of a trading strategy implemented using the Strategy Studio platform. This strategy employs two core technical indicators, VWAP (Volume Weighted Average Price) and Bollinger Bands, to make automated trading decisions. The strategy buys or sells based on the price's position relative to these indicators, aiming to capture profitable opportunities when markets are volatile. The strategy is fully automated and tracks real time price and volume data to make decisions.

The performance of this strategy is assessed using real trading data, which includes executed orders, price data, and cumulative profit and loss over time. The goal is to understand how effectively the strategy performs in various market conditions and evaluate the strategy's overall profitability, trade execution, and adherence to its intended trading logic.

Strategy Overview

The strategy is built on the foundation of two primary technical indicators: VWAP and Bollinger Bands.

The VWAP is a price indicator that accounts for both price and volume, offering an average price weighted by volume over a defined period. It provides a sense of the "fair" market value based on trading activity. The strategy uses VWAP to compare the current price of an instrument to its average price, identifying whether the instrument is undervalued or overvalued relative to market activity.

Bollinger Bands are volatility indicators that consist of a middle band (the simple moving average), and two outer bands (set a specific number of standard deviations above and below the moving average). The bands expand or contract based on market volatility, offering a measure of price range and potential overbought or oversold conditions. The strategy uses these bands to trigger buy or sell signals when the price crosses these thresholds.

The VWAPBollinger class created is responsible for calculating these indicators using rolling windows of price and volume data. This calculation allows the strategy to adjust its trading logic in real time as new data becomes available.

Trading Logic and Execution

The strategy utilizes the VWAPBollinger class to monitor the price and volume data of instruments and make trading decisions. The core trading logic is built around the following principles:

Position Size and Aggressiveness: The strategy is configured with two key parameters: position size and aggressiveness. The position size determines the number of units the strategy buys or sells when a signal is triggered, with a default setting of 100 units. The aggressiveness factor (default set to 0.01) is used to adjust the limit order price slightly above the bid price when buying and below the ask price when selling, ensuring orders are more likely to be filled promptly.

Buy Signal: A buy signal is triggered when the price falls below the lower Bollinger Band and is also below the VWAP. This suggests that the instrument is oversold, and the strategy expects the price to revert to the mean (VWAP) as market conditions stabilize.

Sell Signal: A sell signal occurs when the price rises above the upper Bollinger Band and is also above the VWAP, signaling that the instrument may be overbought. The strategy expects the price to revert downward and thus initiates a sell order.

Portfolio Adjustment: The strategy continually adjusts the portfolio based on market conditions. If a buy or sell signal is triggered, it calculates the difference between the current position and the desired position, placing an order to rebalance the portfolio to the target size.

Orders are executed using a limit order strategy that is slightly adjusted by the aggressiveness factor to improve the chances of execution.

Key Parameters

The key parameters that govern the execution of the strategy are:

Position Size: This defines how much of an instrument the strategy buys or sells during a trade. It is set to 100 units by default, but can be adjusted based on the trader's risk tolerance and trading objectives.

Aggressiveness: This parameter is used to adjust the price at which the strategy places limit orders, ensuring they are slightly above the bid price when buying or below the ask price when selling. It facilitates quicker execution of orders, especially in volatile markets.

These parameters are crucial for defining the risk profile and execution behavior of the strategy.

Performance Evaluation

To evaluate the performance of the strategy, several key metrics are analyzed, including cumulative profit and loss (PnL), order execution patterns, and the alignment of trade prices with the Bollinger Bands.

Cumulative PnL: The cumulative PnL chart tracks the overall profitability of the strategy over time. It reflects the success of the strategy in generating profits or losses from executed trades.



Order Frequency: The number of orders placed at different times of day is analyzed to understand the strategy's trading activity and the periods during which it is most active. This helps assess the market conditions under which the strategy is likely to place trades.



Trade Execution Analysis: By comparing the trade prices with the VWAP and Bollinger Bands, we can evaluate whether the strategy is adhering to its rules. Ideally, buy orders should be executed near the lower Bollinger Band and below the VWAP, while sell orders should be executed near the upper Bollinger Band and above the VWAP.



These performance metrics provide insight into how well the strategy is functioning in different market environments.

Conclusion

The strategy uses a systematic approach to trading based on VWAP and Bollinger Bands, which are powerful tools for identifying overbought and oversold conditions. By executing trades based on these indicators, the strategy aims to capitalize on price reversion patterns in the market. The analysis of cumulative PnL, order frequency, and trade execution provides a comprehensive view of the strategy’s effectiveness. While the strategy performs well in capturing trends, further optimizations in position sizing, slippage management, and parameter adjustments could enhance its performance in different market environments.



