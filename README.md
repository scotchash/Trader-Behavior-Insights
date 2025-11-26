# Trader-Behavior-Insights
Junior Data Scientist – Trader Behavior Insights

REPROT BY ASHISH TRIVEDI 

Trader Behavior Insights
Analysis of Hyperliquid Trading Data and Bitcoin Market Sentiment
Introduction
This project investigates how Bitcoin market sentiment influences trader performance on the Hyperliquid exchange. By combining the Bitcoin Fear & Greed Index with detailed historical trading records, the analysis identifies behavioral patterns, performance trends, and sentiment-driven characteristics of profitable and unprofitable trades. The assignment focuses on extracting insights that can support smarter crypto trading strategies.
________________________________________
Objective
The primary objectives of this project are:
1.	To merge daily Bitcoin sentiment data with Hyperliquid trading activity.
2.	To explore how market sentiment affects trader performance, position sizing, and trade direction.
3.	To analyze profitability differences across sentiment regimes such as Fear, Greed, Extreme Greed, etc.
4.	To compare BUY versus SELL performance under various sentiment conditions.
5.	To build a baseline predictive model that estimates the likelihood of a profitable trade.
6.	To provide clear, actionable insights for improving trading decisions.
________________________________________
Datasets Used
1. Hyperliquid Historical Trader Data
This dataset contains execution-level trading data with fields including:
•	Account
•	Symbol
•	Execution Price
•	Size (USD and Tokens)
•	Side (BUY or SELL)
•	Fee
•	Closed PnL
•	Start Position
•	Leverage
•	Event Type
•	Trade Timestamp
This dataset is used to measure trader behavior, outcomes, and performance patterns.
2. Bitcoin Fear & Greed Index
This dataset includes:
•	Date
•	Sentiment Value (0 to 100)
•	Sentiment Classification (Extreme Fear, Fear, Neutral, Greed, Extreme Greed)
This dataset provides daily market sentiment indicators.
________________________________________
Data Preparation
1. Parsing and Cleaning
•	Converted timestamp fields into a standard datetime format.
•	Extracted date components to align with daily sentiment data.
•	Converted monetary and numeric fields into consistent numeric types.
•	Created a binary indicator variable, is_win, representing profitable or non-profitable trades.
2. Merging the Datasets
The trading dataset and sentiment dataset were merged on the date column so each trade contains the sentiment classification and sentiment index value for that specific day.
3. Handling Missing Values
Missing values in both numeric and categorical fields were imputed using:
•	Median imputation for numeric fields
•	Most frequent category imputation for categorical fields
This preprocessing was implemented within a scikit-learn pipeline.
________________________________________
Exploratory Data Analysis
Profitability by Sentiment Classification
Analysis shows that sentiment regimes have a measurable impact on trading outcomes:
•	Extreme Greed has the highest average PnL per trade and the highest win rate.
•	Fear contributes the highest total PnL due to higher trade volumes, but performance is less efficient.
•	Extreme Fear is the least profitable regime with the lowest win rate and lowest total PnL contribution.
•	Neutral and Greed regimes show moderate performance.
BUY vs SELL Trade Performance
There is a significant performance difference between BUY and SELL trades:
•	SELL trades consistently achieve higher win rates than BUY trades across all sentiment categories.
•	SELL win rates typically range from 55 to 59 percent.
•	BUY win rates are substantially lower, generally between 20 and 32 percent.
•	SELL trades perform particularly well in Extreme Greed and Fear regimes.
This suggests that short positions tend to be more profitable in this dataset, especially during strong sentiment periods.
Trade Size Behavior
Trade sizing varies significantly with sentiment:
•	Larger trade sizes occur during Fear and Extreme Fear.
•	Smaller, more controlled position sizes appear during Greed and Extreme Greed.
This indicates that traders tend to increase risk exposure during fearful markets, which often corresponds with poorer outcomes.
Correlation with Sentiment Index
Correlation analysis between the numeric Fear & Greed score and daily PnL shows:
•	Weak negative cor
REPROT BY ASHISH TRIVEDI 

Trader Behavior Insights
Analysis of Hyperliquid Trading Data and Bitcoin Market Sentiment
Introduction
This project investigates how Bitcoin market sentiment influences trader performance on the Hyperliquid exchange. By combining the Bitcoin Fear & Greed Index with detailed historical trading records, the analysis identifies behavioral patterns, performance trends, and sentiment-driven characteristics of profitable and unprofitable trades. The assignment focuses on extracting insights that can support smarter crypto trading strategies.
________________________________________
Objective
The primary objectives of this project are:
1.	To merge daily Bitcoin sentiment data with Hyperliquid trading activity.
2.	To explore how market sentiment affects trader performance, position sizing, and trade direction.
3.	To analyze profitability differences across sentiment regimes such as Fear, Greed, Extreme Greed, etc.
4.	To compare BUY versus SELL performance under various sentiment conditions.
5.	To build a baseline predictive model that estimates the likelihood of a profitable trade.
6.	To provide clear, actionable insights for improving trading decisions.
________________________________________
Datasets Used
1. Hyperliquid Historical Trader Data
This dataset contains execution-level trading data with fields including:
•	Account
•	Symbol
•	Execution Price
•	Size (USD and Tokens)
•	Side (BUY or SELL)
•	Fee
•	Closed PnL
•	Start Position
•	Leverage
•	Event Type
•	Trade Timestamp
This dataset is used to measure trader behavior, outcomes, and performance patterns.
2. Bitcoin Fear & Greed Index
This dataset includes:
•	Date
•	Sentiment Value (0 to 100)
•	Sentiment Classification (Extreme Fear, Fear, Neutral, Greed, Extreme Greed)
This dataset provides daily market sentiment indicators.
________________________________________
Data Preparation
1. Parsing and Cleaning
•	Converted timestamp fields into a standard datetime format.
•	Extracted date components to align with daily sentiment data.
•	Converted monetary and numeric fields into consistent numeric types.
•	Created a binary indicator variable, is_win, representing profitable or non-profitable trades.
2. Merging the Datasets
The trading dataset and sentiment dataset were merged on the date column so each trade contains the sentiment classification and sentiment index value for that specific day.
3. Handling Missing Values
Missing values in both numeric and categorical fields were imputed using:
•	Median imputation for numeric fields
•	Most frequent category imputation for categorical fields
This preprocessing was implemented within a scikit-learn pipeline.
________________________________________
Exploratory Data Analysis
Profitability by Sentiment Classification
Analysis shows that sentiment regimes have a measurable impact on trading outcomes:
•	Extreme Greed has the highest average PnL per trade and the highest win rate.
•	Fear contributes the highest total PnL due to higher trade volumes, but performance is less efficient.
•	Extreme Fear is the least profitable regime with the lowest win rate and lowest total PnL contribution.
•	Neutral and Greed regimes show moderate performance.
BUY vs SELL Trade Performance
There is a significant performance difference between BUY and SELL trades:
•	SELL trades consistently achieve higher win rates than BUY trades across all sentiment categories.
•	SELL win rates typically range from 55 to 59 percent.
•	BUY win rates are substantially lower, generally between 20 and 32 percent.
•	SELL trades perform particularly well in Extreme Greed and Fear regimes.
This suggests that short positions tend to be more profitable in this dataset, especially during strong sentiment periods.
Trade Size Behavior
Trade sizing varies significantly with sentiment:
•	Larger trade sizes occur during Fear and Extreme Fear.
•	Smaller, more controlled position sizes appear during Greed and Extreme Greed.
This indicates that traders tend to increase risk exposure during fearful markets, which often corresponds with poorer outcomes.
Correlation with Sentiment Index
Correlation analysis between the numeric Fear & Greed score and daily PnL shows:
•	Weak negative correlation with total daily PnL
•	Near zero correlation with average PnL per trade
This shows that sentiment categories (Extreme Greed, Extreme Fear, etc.) are more informative than the raw sentiment score.
________________________________________
Predictive Modeling
A baseline predictive model was built using Logistic Regression to estimate whether a given trade would be profitable.
Features Used
•	Side (BUY or SELL)
•	Size USD
•	Sentiment Value
•	Sentiment Classification (encoded using One-Hot Encoding)
Preprocessing
A ColumnTransformer pipeline was used to handle:
•	Numerical imputing
•	Categorical imputing
•	One-hot encoding
•	Logistic regression training
Model Summary
The model demonstrates that:
•	Trade side (BUY or SELL) is a strong predictor of profitability.
•	Certain sentiment categories increase the probability of positive outcomes.
•	Although simple, the baseline model effectively captures key behavioral patterns.
________________________________________
Key Insights and Recommendations
1.	Extreme Greed is the most favorable trading environment, showing the highest win rate and highest average profitability.
2.	Extreme Fear is the worst environment for trading, indicating that risk management should be tightened during these periods.
3.	SELL trades significantly outperform BUY trades across all sentiment regimes, suggesting that short-biased strategies may be more effective.
4.	Traders tend to increase position sizes during Fear, which correlates with lower win rates and thus higher risk.
5.	The sentiment regime categories (Fear, Greed, Extreme Greed, etc.) are more predictive of performance than the raw sentiment value.
6.	Incorporating sentiment classification into trading strategies may improve decision-making and risk management.


Conclusion
This project provides a comprehensive analysis of how market sentiment influences trading behavior and performance on Hyperliquid. The findings demonstrate clear relationships between sentiment regimes, trader profitability, trade direction preferences, and risk-taking tendencies. These insights can be directly applied to improve risk management, trading strategies, and trader evaluation processes within a crypto trading environment.

elation with total daily PnL
•	Near zero correlation with average PnL per trade
This shows that sentiment categories (Extreme Greed, Extreme Fear, etc.) are more informative than the raw sentiment score.
________________________________________
Predictive Modeling
A baseline predictive model was built using Logistic Regression to estimate whether a given trade would be profitable.
Features Used
•	Side (BUY or SELL)
•	Size USD
•	Sentiment Value
•	Sentiment Classification (encoded using One-Hot Encoding)
Preprocessing
A ColumnTransformer pipeline was used to handle:
•	Numerical imputing
•	Categorical imputing
•	One-hot encoding
•	Logistic regression training
Model Summary
The model demonstrates that:
•	Trade side (BUY or SELL) is a strong predictor of profitability.
•	Certain sentiment categories increase the probability of positive outcomes.
•	Although simple, the baseline model effectively captures key behavioral patterns.
________________________________________
Key Insights and Recommendations
1.	Extreme Greed is the most favorable trading environment, showing the highest win rate and highest average profitability.
2.	Extreme Fear is the worst environment for trading, indicating that risk management should be tightened during these periods.
3.	SELL trades significantly outperform BUY trades across all sentiment regimes, suggesting that short-biased strategies may be more effective.
4.	Traders tend to increase position sizes during Fear, which correlates with lower win rates and thus higher risk.
5.	The sentiment regime categories (Fear, Greed, Extreme Greed, etc.) are more predictive of performance than the raw sentiment value.
6.	Incorporating sentiment classification into trading strategies may improve decision-making and risk management.


Conclusion
This project provides a comprehensive analysis of how market sentiment influences trading behavior and performance on Hyperliquid. The findings demonstrate clear relationships between sentiment regimes, trader profitability, trade direction preferences, and risk-taking tendencies. These insights can be directly applied to improve risk management, trading strategies, and trader evaluation processes within a crypto trading environment.

