# Predictive Real Estate Market Analysis and Housing Price Estimation
Prasad Rao – 12/23/2024

## Problem Statement
The real estate market is influenced by a wide range of factors including property characteristics, economic conditions, and demographic trends. This project aims to predict housing prices based on location, property attributes (e.g., number of bedrooms and bathrooms, construction quality), and evaluate macroeconomic factors like interest rates and population migration. The goal is to gain insights into market trends and predict future directions.

## Data Requirements
1.	Real Estate Data
- Property listings from regions such as Los Angeles, San Francisco, Austin, Dallas, and Chicago.
- Attributes like location, size, number of bedrooms and bathrooms, construction quality, and age of the property.
2.	Macroeconomic Data
- Historical and current interest rates, particularly during periods of easing.
- Historical trends showing how interest rate changes have impacted real estate buying and selling.
3.	Demographic and Migration Data
- Population migration trends across the US.
- Data on employment rates, average income, and urbanization.

## Approach
1.	Data Preparation
- Cleanse and preprocess all datasets to remove inconsistencies and outliers.
- Merge data into a single comprehensive dataframe for analysis.
2.	Data Exploration
- Use data visualization techniques to understand trends, distributions, and correlations.
3.	Dimensionality Reduction
- Apply techniques like SVD (Singular Value Decomposition) and PCA (Principal Component Analysis) to identify key factors influencing housing prices and reduce dimensionality.
4.	Clustering Techniques
- Employ clustering algorithms such as KMeans, DBSCAN, and OPTICS to segment data and identify patterns in the market.
5.	Predictive Modeling:
- Use machine learning models from scikit-learn to fit the data and predict housing prices.
- Train models on historical data and validate using testing datasets.
6. Timeseries data
- Use Zillow data to gather the supply vs demand data that may have significant impact on the prices. Use Auto-correlation to understand the impact of price trend. Extract the trend, cyclic and 

## AI/ML Techniques:
- Data Cleaning and Preprocessing: Pandas and NumPy.
- Visualization: Matplotlib, Seaborn, Plotly.
- Dimensionality Reduction: SVD and PCA via sklearn.
- Clustering Algorithms: KMeans, DBSCAN, OPTICS from sklearn.
- Prediction: Fit and predict methods for regression and classification models.

## Expected Outcomes:
- Predictions of housing prices with an expected margin of error based on location and property attributes
- Understanding of Insights into the impact of macroeconomic trends like interest rate changes on the real estate market.
- Understanding of impacts of migration trends and their influence on housing demand in various regions.

## Outcome:
This is a very relatable project for me from what is happening to property prices. The transactions are large and usually have a good reason that we can relate to. Having a good understanding of the problem domain is essential to be able to accurately predict something.I expect to be able to apply all the techniques learned in the class, and apply to any problem.  Hence I would like to use this problem to solve for my Capstone project

