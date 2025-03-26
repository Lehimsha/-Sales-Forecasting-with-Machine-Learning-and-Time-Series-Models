# -Sales-Forecasting-with-Machine-Learning-and-Time-Series-Models
This project uses multiple forecasting techniques to predict retail sales, using a real-world dataset including sales, oil prices, holidays, and store information. The following models were implemented and compared:

- Naive Forecast (Baseline)
- ARIMA (AutoRegressive Integrated Moving Average)
- LSTM (Long Short-Term Memory Neural Network)
- Random Forest Regressor
- XGBoost Regressor

## Dataset

The dataset includes:
- train.csv: Historical sales data
- stores.csv: Metadata about each store
- oil.csv: Daily oil prices
- holidays_events.csv: Information about national holidays

## Steps to Run Output

1. Clone the repository or download the notebook.
2. Place the dataset files inside a folder named store_forecasting_data/.
3. Open the code.ipynb file in Jupyter Notebook.
4. Run all cells sequentially.

> *Note*: For memory efficiency, only 100,000 rows were used from the training data.

## Requirements

Install the following Python libraries before running the notebook:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn xgboost statsmodels tensorflow

## Output
	•	A comparison of all models using RMSE, MAPE, and R² metrics.
	•	A line plot of actual vs. predicted sales for visual inspection.

Folder Structure
store_forecasting_project/
│
├── code.ipynb             # Main Jupyter Notebook
├── README.md              # Project overview and instructions
└── store_forecasting_data/
    ├── train.csv
    ├── stores.csv
    ├── oil.csv
    └── holidays_events.csv


### *Interpretation and Business Insights*

#### *Which Model Performed Best and Why?*

Based on the evaluation metrics (RMSE, MAPE, R²), the *XGBoost Regressor* showed the best performance across most metrics. This is because:

- It handles non-linearities well.
- Can capture complex feature interactions like holidays, oil price fluctuations, and store-specific behaviors.
- Automatically deals with missing values and handles overfitting through regularization.

The *LSTM* model showed good potential with time-dependent patterns, but required more tuning and more data for long-term memory efficiency.

#### *Impact of External Factors*

- *Holidays:* Spikes in sales were seen during national holidays. Including is_holiday significantly improved model accuracy.
- *Oil Prices:* Affected operational costs and possibly influenced pricing strategies, hence included as a feature.
- *Paydays & Earthquakes:* Notable increase in sales on paydays and a disruption during the 2016 Ecuador earthquake confirmed the value of temporal events.

#### *Business Strategies*

1. *Inventory Planning:*
   - Use the forecast from the best model (XGBoost) to stock inventory per store and product family efficiently.

2. *Targeted Promotions:*
   - Launch promotions just before holidays or paydays to leverage increased customer activity.

3. *Cost Forecasting:*
   - Align marketing budgets and logistics planning with expected sales and external economic indicators like oil price trends.

4. *AI-Driven Restocking:*
   - Automate purchase orders based on model forecasts to reduce both stockouts and overstock situations.

