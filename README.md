# iPhone Sales Analysis Project

## Introduction

This project aims to analyze various key performance indicators (KPIs) related to the sales of iPhones on Flipkart. Using Python libraries like Pandas, Numpy, Matplotlib, and Seaborn, we will clean, visualize, and interpret the data to derive meaningful insights.

## Libraries Used

- **Pandas**: For data manipulation and analysis
- **Numpy**: For numerical operations and array manipulations
- **Matplotlib**: For creating static, interactive, and animated visualizations
- **Seaborn**: For making statistical graphics in Python

## Data Description

The dataset contains the following columns:
- **Product Name**: The name of the iPhone model
- **Brand**: The brand of the iPhone (e.g., Apple)
- **Sale Price**: The sale price of each iPhone model
- **MRP (Maximum Retail Price)**: The original price of the iPhone
- **Discount Percentage**: The discount percentage on each iPhone model
- **Number of Ratings**: The number of ratings each iPhone model has received on Flipkart
- **Number of Reviews**: The number of reviews each iPhone model has received on Flipkart
- **Star Rating**: The star rating of each iPhone model

## Key Performance Indicators (KPIs)

1. **iPhone with the Highest Number of Reviews**
   - The iPhone model with the highest number of reviews on Flipkart.
   - **Example**: `iPhone 15 (Black, 128 GB)` with `2,36,643 ratings`.

2. **Relationship between Sale Price and Number of Ratings**
   - Analyze the relationship between the sale price of iPhones and the number of ratings on Flipkart.
   - Generally, a negative correlation is observed; more affordable iPhones tend to have higher ratings.

3. **Relationship between Discount Percentage and Number of Ratings**
   - Explore how the discount percentage impacts the number of ratings on Flipkart.
   - Higher discounts might attract more ratings, reflecting consumer interest in better deals.

4. **Most Expensive and Least Expensive iPhone Models**
   - Identify the most and least expensive iPhone models in the dataset.
   - **Most Expensive**: Example: `iPhone 13 Pro` priced at `₹1,10,000`.
   - **Least Expensive**: Example: `iPhone SE` priced at `₹40,000`.

## Data Analysis Steps

### Step 1: Data Preparation and Cleaning

- Import the data using Pandas.
- Clean the data by removing duplicates and handling missing values.

### Step 2: Data Visualization

#### Using Matplotlib

```python
import matplotlib.pyplot as plt
import numpy as np
from sklearn.linear_model import LinearRegression

# Create a scatter plot
plt.figure(figsize=(10, 6))
plt.scatter(data['Number of Ratings'], data['Sale Price'], alpha=0.5, color='blue')
plt.xlabel('Number of Ratings')
plt.ylabel('Sale Price')
plt.title('Relationship between Sale Price of iPhones and Number of Ratings on Flipkart')

# Add a trendline
X = data['Number of Ratings'].values.reshape(-1, 1)
Y = data['Sale Price'].values.reshape(-1, 1)
regressor = LinearRegression()
regressor.fit(X, Y)
Y_pred = regressor.predict(X)
plt.plot(data['Number of Ratings'], Y_pred, color='red')
plt.show()
