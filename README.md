# EXECUTIVE SUMMARY

## Overview 
- This report documents the entirety of our options pricing group project – from planning stages to conclusion and summary. 

## Problem Statement 
- Using European call option pricing data on the S&P 500, we will find the best regression model (in terms of out-of-sample r squared) and best classification model (in terms of classification error) to predict “Value” and “BS” respectively. Our dataset had stock options with the following recorded variables: 
  - Value (C): Current option value 
  - S: Current asset value 
  - K: Strike price of option 
  -	r: Annual interest rate 
  -	tau: Time to maturity (in years) 
  - BS: The Black-Scholes formula was applied to this data (using some σ) to get C_pred. If an option has C_pred – C > 0, i.e., the prediction overestimated the option value

- Our best selected models would then be used to make predictions on an unseen test dataset of 1,120 options. 

## Solution Summary
- We underwent data cleaning, data analysis, and interpretation on the given training data set. We explored a variety of regression methods and classification methods. Our best model for “Value” was a linear regression model using transformed variables: (Value = K + S + tau + K*S + K^2 + log(tau) + e^K + 1/r + tau^K). Our best model for “BS” was using XGBoost Classifier with hyper-tuned parameters: XGBClassifier(learning_rate= 1, max_depth= 4, eta=1). 

## Conclusions
- While we have confidence both of our models will perform well on the unseen test dataset, we would not suggest using our model to make predictions on anything other than European S&P 500 options data. 
