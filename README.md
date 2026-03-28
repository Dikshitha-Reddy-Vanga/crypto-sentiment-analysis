# Crypto Sentiment vs Trader Behavior Analysis

## Overview

This project analyzes the relationship between Bitcoin market sentiment (Fear/Greed index) and trader behavior on Hyperliquid. The objective is to identify patterns in trading performance and behavior across different market conditions and derive actionable insights for improving trading strategies.

The analysis combines sentiment data with historical trade data to evaluate profitability, trading patterns, and behavioral shifts under varying sentiment regimes.

---

## Dataset Description

### 1. Market Sentiment Dataset

* Fields: timestamp, value, classification, date
* Description: Contains daily Bitcoin Fear/Greed index classification.

### 2. Hyperliquid Trade Dataset

* Fields include:

  * Account
  * Coin
  * Execution Price
  * Size USD
  * Side
  * Timestamp
  * Closed PnL
  * Fee
  * Trade ID
* Description: Contains historical trading activity of users.

---

## Methodology

### Data Preparation

* Loaded both datasets and performed initial inspection
* Checked for missing values and duplicates
* Converted timestamps to datetime format
* Aligned both datasets at a daily level
* Merged datasets on date

### Feature Engineering

* Created profitability indicator (`win`)
* Computed:

  * Daily PnL
  * Win rate
  * Trade frequency
  * Long/Short ratio
* Encoded categorical variables (sentiment and trade direction)

### Analysis

* Compared performance metrics across sentiment categories
* Analyzed behavioral changes:

  * Trade frequency
  * Position bias (long vs short)
* Performed segmentation:

  * Frequent vs infrequent traders
  * Consistent winners vs others

### Modeling (Optional)

* Built a logistic regression model to predict trade profitability
* Features used:

  * Market sentiment
  * Trade size
  * Trade direction
* Addressed class imbalance using class weighting
* Evaluated model using accuracy and classification metrics

---

## Key Insights

* Trading performance varies across sentiment regimes, with higher average profits observed during Greed periods
* Extreme sentiment phases show different trade consistency compared to moderate conditions
* Traders exhibit behavioral shifts such as increased short positions during Greed
* Higher trading frequency is associated with lower profitability
* Sentiment and trade features provide moderate predictive power for profitability

---

## Repository Structure

crypto-sentiment-analysis/
│
├── notebook.ipynb
├── README.md
├── WRITEUP.pdf
│
├── data/
│   ├── fear_greed.csv
│   └── trader_data.csv
│
├── outputs/
│   ├── pnl_by_sentiment.png
│   ├── trades_per_day.png
│   └── long_short.png

---

## Setup Instructions

1. Clone the repository:
   git clone https://github.com/Dikshitha-Reddy-Vanga/crypto-sentiment-analysis.git

2. Navigate to the project directory:
   cd crypto-sentiment-analysis

3. Install required dependencies:
   pip install pandas numpy matplotlib seaborn scikit-learn

---

## How to Run

1. Place the datasets inside the `data/` directory:

   * fear_greed.csv
   * trader_data.csv

2. Open the notebook:
   jupyter notebook notebook.ipynb

3. Run all cells sequentially to:

   * Clean and merge data
   * Generate analysis and visualizations
   * Train and evaluate the model

4. Output charts will be generated and can be saved in the `outputs/` folder.

---

## Output

* Visualizations showing sentiment vs performance and behavior
* Segmentation analysis tables
* Model performance metrics
* Detailed report available in `WRITEUP.pdf`

---

## Reproducibility

All steps from data preprocessing to modeling are included in the notebook. Running the notebook end-to-end will reproduce all results.

---

## Author

Dikshitha Reddy Vanga
