# Trader Behavior & Sentiment Analysis

## Overview
This project analyzes how trader behavior and performance change under different market sentiment regimes using historical trade data and the Fear & Greed Index. The goal is to identify behavioral patterns, evaluate performance differences, and derive actionable trading strategies.

---

## Setup
```bash
pip install pandas numpy matplotlib scikit-learn
 #how to run
Jupyter notebook

Charts:
	•	Avarage trade size
	•	trades per day
	•	Long vs Short ratio
	•	Performance vs sentiment
  •Behaviour change by sentiment
  •trader segmentation
  •consistency segmentation

#Strategy 1: Risk Control Based on Market Sentiment

#From analysis: Fear days  higher volatility, lower win rate, larger drawdowns
              # Greed days  higher trade frequency but diminishing returns at high leverage

# Rule of Thumb
#During Fear days, reduce leverage and position size for high-leverage traders.
#During Greed days, allow higher trade frequency only for historically consistent traders.


#Strategy 2: Trader Segmentation–Based Controls

	#Consistent winners survive Fear days better
	#Inconsistent traders lose disproportionately when sentiment is extreme
#Rule of Thumb:
#Enable aggressive strategies only for consistent winners.
#Throttle leverage and trade count for inconsistent or infrequent traders during Fear periods.

#Methodology

#Part A — Data Preparation
		#Loaded and validated both datasets
		#Checked missing values and duplicates
		#Converted timestamps and aligned by date
		#Engineered key metrics:
		#Daily PnL per trader
		#Win rate
    #Average trade size
		#Trades per day
		#Long/short ratio

#Part B — Analysis

#Based on median trades per day
		#High vs Low Leverage Traders
#Based on USD trade size quantiles
	#Consistent Winners vs Inconsistent Traders
#Based on:
	#Positive average PnL
	#Low PnL volatility (standard deviation)

#Sentiment Impact
	#Compared performance across:
	#Fear days
	#Neutral days
	#Greed days
	#Analyzed changes in:
	#Trade frequency
	#Position sizing
	#Directional bias

#Part C — Predictive Modeling 
	#Target: Daily profitability bucket (Loss / Neutral / Profit)
	#Model: Random Forest Classifier
	#Features:
	#Average trade size
	#Trade count
	#Direction bias
  #Sentiment value
	#Accuracy ~55%

#Key Insights
	#1.	High leverage traders show higher average PnL but similar win rates, indicating higher risk rather than superior skill.
	#2.	Trader activity increases during Greed days, but performance dispersion also widens.
	#3.	Consistent winners are characterized by lower PnL volatility, not higher trade frequency.
	#4.	Fear periods penalize over-leveraged and over-active traders more severely.
