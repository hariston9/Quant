# Quant
Quantitative Analyst - 10 point assignment set
DEADLINE - 17th of April, 2022

Note that working without supervision is a desirable skill in this role, so you are expected to fill in the gaps in assumptions with the below assignment with your own judgment. Critical thinking will go a long way in reaching the right goal. 

Please read the entire assignment carefully, and section each part of the assignment in different files in your repository. Comments in your code explaining the thought process are encouraged, and will be rewarded for clarity of thought. Jupyter Notebooks can be used to document each step and output extremely clearly and the use of the same is encouraged.

This assignment is designed to be easy for those used to time series analytics, and is very constructive in teaching the process of market making to those that don’t have experience with this type of work. You can learn more about market making here - https://blog.quantinsti.com/market-making/#:~:text=With%20Market%20Making%20Strategy%2C%20the,price%20than%20the%20market%20price.
Assignment I - Basic Python - 3 points

The purpose of this assignment is to assess your ability to use Python to retrieve a large public dataset and store it in memory using Pandas for further analysis. The documentation and endpoint is laid out below this section. You are expected to retrieve data at the tick level for BTCUSDT for the first 3 days of March.

https://github.com/binance/binance-public-data/#trades-2
	The endpoint - https://data.binance.vision/?prefix=data/spot/daily/trades/

	Note - The 2nd, 3rd, 4th and 5th columns are:
Traded Price, Traded Size, Traded Notional, Timestamp
You do not require any other columns to do this assignment. 

	
Assignment II - Simple Forward Looking Market Making Strategy - 5 points 
You may use any Python library you are familiar with to do this, but pandas and backtrader are preferred. Using the above dataset, you are to create a Market Making strategy in Python that uses the above data, and run the following strategy on it:
Bid Size and Offer Size = 1000 USD notional (note, the actual traded base quantity on Binance BTCUSDT is BTC, so you will need to convert the Sizes to the equivalent BTC amount at every quote “refresh”
Buy and Sell Margins = 3 basis points i.e. the distance between your bid or offer quote and the mid market in absolute terms.
Maximum position before hedging = 5000 USD notional i.e. if your position exceeds this either on the buy or sell side, your strategy stops quoting on that side of the market and hedges your position. If your strategy uses a market order to exit the position, you will be rewarded one less point. A passive hedger approach will be rewarded full points upon completion.
You may assume that the latencies in each step of the market maker is 100 milliseconds. A realistic random latency would be closer to the “real” result.
You may assume that the cost of trading is zero i.e. there are no commissions
You may assume that a trade match happens when the trading price “crosses” your bid or offer order, for simplicity.

The output of the trades generated from this strategy should reside in a different dataframe, for the next step. Completion upto this point in the Assignment Set would reward a maximum of 7 points.



3. Assignment III - Execution Analysis - 2 points
For each day, using the output of the trades generated above, calculate the:
Gross PNL in basis points (this is your PNL in $ divided by your $ volume, multiplied by 10000)
Gross PNL in $
Maximum drawdown
Average win pnl
Average loss pnl
Number of trades

And showcase the result in either a CSV or DataFrame.
