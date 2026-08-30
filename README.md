-> Automated Stock Price Forecaster

A Machine Learning project that started as a manual stock-price
prediction workflow and was later converted into a reusable automated
forecasting system.

The original project was built step by step using HDFC Bank historical
stock data. After understanding and testing each stage of the ML
workflow, I converted the process into a Streamlit application so a user
can upload a new stock dataset and run the forecasting pipeline without
manually executing every step.

Goal: Upload historical stock data → clean and process it → create
features → train the model → evaluate it → predict the next trading
day's closing price.

-> Project Evolution

Version 1 --- Original ML Workflow

I first built the project manually:

Data Collection
      ↓
Data Cleaning
      ↓
EDA
      ↓
Feature Engineering
      ↓
Train/Test Split
      ↓
Model Training
      ↓
Model Evaluation
      ↓
Time-Series Cross Validation
      ↓
Next-Day Prediction

The repository keeps this original implementation because it shows how I
learned and developed the project step by step.

Version 2 --- Automated ML System

I then converted the workflow into a Streamlit application:

Upload Dataset
      ↓
Data Processing
      ↓
EDA
      ↓
Feature Engineering
      ↓
Model Training
      ↓
Evaluation
      ↓
Next-Day Prediction

The main idea is to make the workflow reusable for different stock
datasets instead of rebuilding the pipeline from scratch each time.

-> What the Project Does

The system uses historical OHLCV stock data to create time-series
features and forecast the next closing price.

The target is created as:

df["Target"] = df["Close"].shift(-1)

Therefore, the model learns to predict the next trading day's closing
price from information available in the historical data.

Expected input columns

Date
Open
High
Low
Close
Adj Close
Volume

-> Data Cleaning

The project checks and prepares the stock data before modelling.

Checks include:

Date conversion

Chronological sorting

Missing values

Duplicate rows

Date range

OHLC consistency

Negative volume

Chronological ordering

The cleaned dataset is then passed to feature engineering.

-> Exploratory Data Analysis

The EDA stage was used to understand the stock data before modelling.

It includes:

Closing price over time

Open vs Close

High vs Low

Trading volume

Closing-price distribution

Closing-price boxplot

Daily returns

Return distribution

Correlation analysis

Correlation heatmap

-> Feature Engineering

I created several features from historical price and volume information.

Lag Features

Close_Lag1
Close_Lag2
Close_Lag3
Close_Lag4
Close_Lag5

Moving Averages

MA_5
MA_10
MA_20

Returns and Volatility

Daily_Return
Volatility_5
Volatility_10

Price Features

Price_Range
Open_Close_Diff

Volume Features

Volume_MA_5
Volume_Ratio

Calendar Feature

Day_of_Week

-> Models Tested

I experimented with several regression approaches.

Baseline

The current closing price was used as a simple baseline.

Linear Regression

Used as the first machine-learning regression model.

Ridge Regression

Used to test a regularized linear approach.

Ridge + StandardScaler

Ridge Regression was also tested after standardizing the features.

Random Forest

Random Forest was tested as a non-linear tree-based model.

Interestingly, Random Forest did not outperform Ridge in the current
experiment. I kept the experiment because model comparison is an
important part of the ML workflow.

-> Model Evaluation

The project uses:

MAE --- Mean Absolute Error

RMSE --- Root Mean Squared Error

R² Score

For MAE and RMSE, lower values are better. For R², higher values are
better.

-> Time-Series Cross Validation

Because stock prices are time-dependent, I used:

TimeSeriesSplit(n_splits=5)

instead of randomly shuffling the observations.

The Random Forest experiment produced:

Fold 1 MAE: 64.11
Fold 2 MAE: 40.32
Fold 3 MAE: 13.79
Fold 4 MAE: 10.09
Fold 5 MAE: 61.55

Average MAE: 37.97

The current best result from my experiments was Ridge Regression with an
average Time-Series CV MAE of approximately:

7.269

These results are specific to this dataset and feature setup.

-> Automated Streamlit Application

The final step was turning the manually executed workflow into an
interactive application.

The intended user flow is:

1. Upload historical stock CSV
            ↓
2. Process and clean data
            ↓
3. Create features
            ↓
4. Train forecasting model
            ↓
5. Evaluate the model
            ↓
6. Generate next-day prediction

The goal is to make the ML workflow easier to reuse without requiring
the user to manually run every stage.

-> Project Structure

business_forcast/
│
├── data/
│   ├── raw stock data
│   ├── cleaned data
│   ├── feature data
│   └── train/test datasets
│
├── src/
│   ├── original ML workflow
│   └── automated_stock_forecasterrrr/
│       └── automation_forcast_sp.py
│
├── model/
│   └── model experiments
│
├── notebooks/
│
├── outputs/
│   └── EDA visualizations
│
├── .gitignore
├── requirements.txt
└── README.md

-> Technologies Used

Python

Pandas

NumPy

Scikit-learn

yfinance

Matplotlib

Seaborn

Streamlit

-> How to Run??

1. Clone the repository

git clone <your-github-repository-url>
cd business_forcast

2. Create a virtual environment

python -m venv .venv

3. Activate it on Windows

.venv\Scripts\activate

4. Install dependencies

pip install -r requirements.txt

5. Run the Streamlit application

python -m streamlit run "src\automated_stock_forecasterrrr\automation_forcast_sp.py"

The application will normally be available at:

http://localhost:8501

-> What I Learned??

This project taught me that building an ML project is more than training
a model.

The biggest learning was the transition from:

"I can build a prediction model."

to:

"I can build a reusable ML pipeline around that model."

I worked with:

Real-world financial time-series data

Data cleaning

Exploratory Data Analysis

Feature engineering

Regression models

Regularization

Feature scaling

Time-series cross validation

Model comparison

Model evaluation

Streamlit

ML pipeline automation

-> Future Improvements

Some improvements I would like to explore:

Automatic model selection

Hyperparameter tuning

More advanced time-series models

Additional technical indicators

More robust input validation

Model persistence

Automated data fetching

Better prediction uncertainty information

Deployment of the Streamlit application

-> Disclaimer!!!

This project is for educational and machine-learning experimentation
purposes.

Stock prices are influenced by many factors that are not represented in
this model. The predictions should not be considered financial advice or
a guarantee of future performance.

-> Project Journey....

This project started with a simple question:

Can I predict tomorrow's stock price using historical data?

It eventually became a bigger question:

Can I turn the entire ML workflow into something reusable that
another person can actually use?

That transition --- from a model to an automated system --- is the part
of this project I found most valuable
