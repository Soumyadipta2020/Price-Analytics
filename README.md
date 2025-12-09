# Price Analytics & Elasticity Measurement

This project performs data analytics on insurance contracts and claims data to understand customer retention drivers and estimate the price elasticity of demand.

The analysis includes data cleaning, feature engineering, and predictive modeling using **Random Forest** (for feature importance and retention prediction) and **Logistic Regression** (historically used for elasticity estimation).

## Project Structure

```
Price-Analytics/
├── Analysis/
│   ├── data/
│   │   ├── claims.csv       # Insurance claims raw data
│   │   └── contracts.csv    # Customer contracts raw data
│   └── analysis.ipynb       # Main Jupyter Notebook for analysis
├── requirements.txt         # Python dependencies
└── README.md                # Project documentation
```

## Features

- **Data Cleaning**: Parses mixed date formats, cleans currency strings, and standardizes categorical variables.
- **Feature Engineering**: Aggregates claims data (frequency and severity) at the contract level.
- **Modeling**:
    - **Random Forest Classifier**: Optimized using `RandomizedSearchCV` to predict customer retention.
    - **Feature Importance**: Identifies key drivers of churn (e.g., Annual Premium, Client Age).
- **Visualization**: Interactive plots using Plotly.

## Installation

1. Clone the repository.
2. Install the required dependencies:

```bash
pip install -r requirements.txt
```

## Usage

1. Navigate to the `Analysis` directory or open the project in your preferred IDE (VS Code, JupyterLab).
2. Open `Analysis/analysis.ipynb`.
3. Run the notebook cells sequentially to execute the data pipeline and generate model results.

## Data Description

- **contracts.csv**: Contains policy details like `start_date`, `annual_premium`, `client_age`, `product_type`, etc.
- **claims.csv**: Contains claim events linked to contracts via `contract_id`.

## Results

The latest model iteration uses a tuned Random Forest to achieve better generalization on the test set. Key insights include the high sensitivity of retention to **Annual Premium** and **Customer Age**.