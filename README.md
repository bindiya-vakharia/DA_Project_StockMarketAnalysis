# Stock Market Analysis Project

## Table of Contents
- [Project Overview](#project-overview)
- [Data Source](#data-source)
- [Tools](#tools)
- [Data Cleaning and Preparation](#data-cleaning-and-preparation)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Analysis](#analysis)
- [Results/Findings](#results/findings)
- [Recommendation](#recommendation)

### Project Overview

This data analysis project is about a detailed financial analysis of the stock market data of two S&P500 companies; Moderna and Berkshire Hathaway. By analysing and sifting through the vast amount of financial data, we aim to extract, analyze, and visualize stock performance and investment risk, and return to pinpoint stocks that may be undervalued and identify various trends and patterns that will optimize the investment portfolio, maximizing returns while minimizing risks.

### Data Source

Stock Market Data: The primary dataset used for this analysis is the 'file_name' containing one year of historical data of Moderna, Berkshire Hathaway and S&P 500 from Yahoo Finance.

### Tools
- Python - Data Cleaning and Visualization
  - Pandas
  - NumPy
  - Matplotlib
  - Seaborn
  - Altair
- Excel - Data Visualisation

### Data Cleaning and Preparation

In the initial data preparation stage, we performed the following tasks:
1. Data loading and inspection
2. Handling missing values
3. Data cleaning and Formating

### Exploratory Data Analysis

EDA involves exploring the stock market data to examine and summarize key characteristics of the dataset.
- Identifying outliers in stock volume using a box plot.
- Explain the correlation between Moderna, Berkshire Hathaway and S&P 500 using Heat Map and Percentage Change line graph.
- Visualizations, including candlestick charts and momentum charts to provide a holistic view of stock price actions throughout 2023.

### Analysis
- Future Price Projections in Excel offering insights into potential growth trajectories.
- Linear Regression Model in Python to provide for model accuracy assessment.
```python
from sklearn.model_selection import train_test_split
from sklearn.linear_model import LinearRegression
from sklearn.metrics import mean_squared_error
import matplotlib.pyplot as plt

df['Date'] = pd.to_datetime(df['Date'])

X = df.index.values.reshape(-1, 1)
y = df['Close'].values

# Split the data into training and testing sets
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)

# Create a linear regression model
model = LinearRegression()

# Fit the model to the training data
model.fit(X_train, y_train)

# Make predictions on the test data
y_pred = model.predict(X_test)

# Calculate the mean squared error
mse = mean_squared_error(y_test, y_pred)
print(f'Mean Squared Error: {mse}')

# Plot the regression line
plt.figure(figsize=(10, 6))
plt.scatter(X_test, y_test, color='black', label='Actual Prices')
plt.plot(X_test, y_pred, color='blue', linewidth=3, label='Regression Line')
plt.title('Linear Regression Analysis on Stock Market Data')
plt.xlabel('Date')
plt.ylabel('Price')
plt.legend()
plt.show()
```

### Results/Findings
- Berkshire Hathaway and S&P 500 display more stability and show an upward trend in the future, making them a great investment choice.
- Moderna exhibits significant price volatility.

### Recommendation
Based on the analysis, we recommend Berkshire Hathaway as a reliable choice for long-term investors and Moderna as an opportunity for those interested in healthcare and innovation. However, it is essential to note that financial markets are uncertain and past performance may not guarantee future results. Therefore, investors should exercise due diligence and consider risk tolerance while investing their money in the stock market. 
