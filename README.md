# 🚲 Bike Rental Demand Prediction

## 💼 Business Use Case

Bike-sharing operators need to anticipate demand so that bikes, docking capacity, and operational resources are available when riders need them. Rental volume changes with weather, seasonality, time of day, and calendar effects, making demand forecasting useful for rebalancing and capacity planning.

This project compares an interpretable linear model with regression trees and uses out-of-sample performance to evaluate the trade-off between explainability and predictive strength.

## 🎯 Principal Objective

The objective is to predict bike-rental demand from weather and calendar variables while keeping the results useful for operational decision-making. In addition to point forecasts, the notebook shows how a regression estimate can be reframed as a probability of exceeding a defined demand threshold.

## 🔍 Key Takeaways

The linear regression reaches a test R² of approximately **0.680**. An unpruned regression tree improves out-of-sample performance to about **0.782**, but its perfect training fit and 11,301 nodes make the overfitting problem clear. After cost-complexity pruning, the selected tree reaches approximately **0.806 OSR²** with a much smaller 753-node structure.

The pruned tree is the strongest predictor in this experiment, while the linear model remains valuable for explanation and scenario analysis. That distinction matters operationally: a planning team may prefer the more accurate model for forecasting and the simpler model for understanding how weather or time-related factors affect demand.

A production system would benefit from station-level features, recent demand history, holidays and events, time-aware validation, and empirically calibrated prediction intervals.

## 💻 Explore the Notebook

The [notebook](https://github.com/saels/blue-bikes-rental-prediction/blob/194026e0a6660e463de5f2d500a9c095a2a80989/Bike_rental_demand_prediction.ipynb) contains the complete feature-selection, linear-regression, probability-estimation, tree-pruning, and model-comparison workflow. Review the code for the modeling details and for a closer look at how forecast accuracy and interpretability are balanced.
