# Walmart Time Series Forecasting

A time series forecasting project that predicts product demand for Walmart electronics using **Holt-Winters Triple Exponential Smoothing**. The project analyzes historical sales data, builds forecasting models for multiple products, evaluates model performance, and generates future demand forecasts to support inventory planning.

## Project Overview

This project uses historical Walmart sales data to forecast demand for five electronics categories:

- TV
- Laptop
- Tablet
- Camera
- Headphones

Each product is modeled independently using **Holt-Winters Exponential Smoothing** with additive trend and seasonality.

## Objectives

- Explore historical demand patterns.
- Prepare daily time series data for each product.
- Train forecasting models using historical demand.
- Evaluate model accuracy on a holdout test set.
- Forecast future demand for inventory planning.
- Visualize actual vs. forecasted demand.

## Dataset

The dataset contains Walmart transaction records including:

- Transaction date
- Product name
- Store number
- Actual demand

The analysis focuses on the Electronics category.

## Methodology

### 1. Data Preparation

- Load Walmart sales data
- Filter electronics products
- Aggregate demand by:
  - Transaction date
  - Product
  - Store
- Convert dates to datetime format
- Create daily time series for each product

### 2. Train/Test Split

Each product's time series is split into:

- 70% training data
- 30% testing data

### 3. Forecasting Model

The project uses **Holt-Winters Triple Exponential Smoothing** from the Statsmodels library.

Model configuration:

- Trend: Additive
- Seasonality: Additive
- Seasonal period: 7 days

This approach captures:

- Overall demand trends
- Weekly seasonal patterns
- Short-term fluctuations

### 4. Model Evaluation

Forecast accuracy is evaluated using standard regression metrics, including:

- Mean Absolute Error (MAE)
- Mean Squared Error (MSE)
- Root Mean Squared Error (RMSE)
- Mean Absolute Percentage Error (MAPE)

### 5. Future Forecasting

After evaluation, each model is retrained on the complete dataset and used to forecast the next **21 days** of demand.

## Visualizations

The notebook includes:

- Historical demand trends
- Product-level time series plots
- Training vs. testing comparisons
- Forecasted demand
- Actual vs. predicted demand visualizations

## Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Statsmodels
- Scikit-learn
- Jupyter Notebook

## Project Structure

```
├── Walmart_Cleaned.csv
├── Time Series Analysis.ipynb
└── README.md
```

## Results

The Holt-Winters models successfully captured weekly demand patterns for each electronics product and produced 21-day forecasts. The evaluation metrics provide insight into forecasting accuracy, while the visualizations help compare predicted demand with observed sales.

## Future Improvements

- Use a longer historical dataset to better capture yearly seasonality.
- Tune smoothing parameters using grid search.
- Compare Holt-Winters with models such as SARIMA, Prophet, or TBATS.
- Incorporate external variables such as holidays, promotions, and pricing.
- Build a unified forecasting pipeline for all product categories.

## How to Run

1. Clone the repository.
2. Install the required Python packages:

```bash
pip install pandas numpy matplotlib statsmodels scikit-learn
```

3. Place the Walmart dataset in the project directory.
4. Update the dataset path if needed.
5. Run the Jupyter notebook to generate forecasts and visualizations.

## Author

**Salem T.**
