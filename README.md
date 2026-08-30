Automated Stock Price Forecasting
An end-to-end machine learning project that automates stock price prediction using multiple regression models with an interactive Streamlit dashboard.

📌 About the Project
This project implements an automated pipeline for forecasting stock prices using historical data from Yahoo Finance. It combines data preprocessing, feature engineering, model training, and evaluation into a seamless workflow. The system supports multiple machine learning models and provides visual insights through an interactive web application.

The project is designed to be modular, scalable, and easy to use for both beginners and experienced data scientists interested in financial time series forecasting.

🎯 Problem Statement
Stock price prediction is a challenging task due to the volatile and non-linear nature of financial markets. Traditional methods often fail to capture complex patterns and relationships in historical data. There is a need for an automated, data-driven approach that can:

Process large volumes of historical stock data efficiently

Engineer relevant features for better prediction

Compare multiple ML models to find the best performer

Provide an easy-to-use interface for non-technical users

🎯 Objective
Develop an automated pipeline for stock price forecasting

Implement and compare multiple regression models (Ridge, Random Forest, etc.)

Engineer meaningful features from raw stock data

Evaluate model performance using appropriate metrics

Deploy a user-friendly Streamlit application for real-time predictions

Provide visual analytics and insights for decision making

📊 Dataset
Source
Data Source: Yahoo Finance (yfinance API)

Ticker: Configurable (default: specific stock symbols)

Time Period: Historical data (adjustable date range)

Data Fields
Column	Description
Date	Trading date
Open	Opening price
High	Highest price of the day
Low	Lowest price of the day
Close	Closing price (target variable)
Adj Close	Adjusted closing price
Volume	Trading volume
Data Preprocessing
Handling missing values

Outlier detection and treatment

Data normalization/standardization

Time series validation

🔧 Features Engineered
Technical Indicators
Moving Averages: SMA, EMA (7, 14, 30-day)

Volatility Metrics: Bollinger Bands, ATR

Momentum Indicators: RSI, MACD

Price Ratios: Open/Close, High/Low

Time-Based Features
Day of week

Month

Quarter

Year

Holiday indicators

Lag Features
Previous day's closing price

Price changes (1, 3, 7 days)

Volume changes

Statistical Features
Rolling mean, median, std

Price momentum

Volume momentum

🤖 Machine Learning Models
Implemented Models
Model	Description	Use Case
Ridge Regression	Linear model with L2 regularization	Baseline, interpretable predictions
Random Forest	Ensemble of decision trees	Capturing non-linear relationships
Linear Regression	Simple linear model	Quick baseline predictions
Model Training Pipeline
Data Splitting

Training set: 80%

Testing set: 20% (time-series split)

Cross-Validation

Time-series cross-validation

K-fold (5-fold) cross-validation

Rolling window validation

Hyperparameter Tuning

Grid Search

Random Search

Cross-validated parameter optimization

📈 Model Evaluation
Performance Metrics
Metric	Description
RMSE	Root Mean Square Error
MAE	Mean Absolute Error
MAPE	Mean Absolute Percentage Error
R² Score	Coefficient of Determination
MSE	Mean Squared Error
Evaluation Visualizations
Actual vs Predicted plots

Residual analysis

Feature importance charts

Learning curves

Error distribution histograms

🔄 Project Pipeline
text
┌─────────────────────────────────────┐
│        Historical Data              │
│    (Download from Yahoo Finance)    │
└─────────────────────────────────────┘
                 ↓
┌─────────────────────────────────────┐
│        Data Cleaning                │
│   (Handle missing values, outliers) │
└─────────────────────────────────────┘
                 ↓
┌─────────────────────────────────────┐
│           EDA                       │
│   (Exploratory Data Analysis)       │
└─────────────────────────────────────┘
                 ↓
┌─────────────────────────────────────┐
│      Feature Engineering            │
│   (Technical indicators, lags)      │
└─────────────────────────────────────┘
                 ↓
┌─────────────────────────────────────┐
│   Time-Series Train/Test Split      │
│      (80% Train, 20% Test)          │
└─────────────────────────────────────┘
                 ↓
┌─────────────────────────────────────┐
│        Model Training               │
│   (Ridge, Random Forest, etc.)      │
└─────────────────────────────────────┘
                 ↓
┌─────────────────────────────────────┐
│       Cross Validation              │
│   (Time-series CV, K-Fold)          │
└─────────────────────────────────────┘
                 ↓
┌─────────────────────────────────────┐
│       Model Comparison              │
│   (Compare performance metrics)     │
└─────────────────────────────────────┘
                 ↓
┌─────────────────────────────────────┐
│          Best Model                 │
│   (Select based on performance)     │
└─────────────────────────────────────┘
                 ↓
┌─────────────────────────────────────┐
│     Next-Day Price Forecast         │
│   (Predict future stock price)      │
└─────────────────────────────────────┘
⚙️ Automated Pipeline
Pipeline Components
text
┌─────────────────────────────────────────────┐
│           DATA DOWNLOAD (yfinance)          │
└─────────────────────────────────────────────┘
                    ↓
┌─────────────────────────────────────────────┐
│         DATA CLEANING & PREPROCESSING       │
└─────────────────────────────────────────────┘
                    ↓
┌─────────────────────────────────────────────┐
│         EXPLORATORY DATA ANALYSIS           │
└─────────────────────────────────────────────┘
                    ↓
┌─────────────────────────────────────────────┐
│          FEATURE ENGINEERING                 │
└─────────────────────────────────────────────┘
                    ↓
┌─────────────────────────────────────────────┐
│          DATA SPLITTING                     │
└─────────────────────────────────────────────┘
                    ↓
┌─────────────────────────────────────────────┐
│      MODEL TRAINING & VALIDATION            │
└─────────────────────────────────────────────┘
                    ↓
┌─────────────────────────────────────────────┐
│         MODEL EVALUATION                    │
└─────────────────────────────────────────────┘
                    ↓
┌─────────────────────────────────────────────┐
│      PREDICTION & VISUALIZATION             │
└─────────────────────────────────────────────┘
Automation Features
Scheduled Execution: Run forecasts automatically

Error Handling: Robust error management

Logging: Comprehensive logging system

Reporting: Auto-generated reports

🖥️ Streamlit Application
Features
Interactive Dashboard

Stock selection dropdown

Date range picker

Model selection

Visualizations

Price trends with predictions

Model comparison charts

Feature importance plots

Performance metrics display

Data Download

Export predictions as CSV

Download charts as images

Application Screens
Home: Project overview and quick stats

Forecast: Prediction interface

Analysis: Detailed analytics

Compare: Model comparison

📁 Project Structure
text
automated-stock-price-forecasting/
│
├── business_forecast/              # Main project directory
│   ├── .venv/                      # Virtual environment
│   ├── data/                       # Raw and processed data
│   ├── model/                      # Saved models
│   ├── notebooks/                  # Jupyter notebooks
│   ├── outputs/                    # Generated outputs
│   ├── src/                        # Source code
│   │   ├── data_loader.py
│   │   ├── preprocessor.py
│   │   └── utils.py
│   └── requirements.txt
│
├── automated_stock_forecasterrrr/  # Streamlit app
├── original_projecttttt/           # Original implementation
├── code/                           # Additional scripts
│   ├── clean_data.py
│   ├── correlation.py
│   ├── cross_validation.py
│   ├── download_data.py
│   ├── eda.py
│   ├── evaluate_model.py
│   ├── feature_engineering.py
│   ├── random_forest_cv.py
│   ├── Ridge_model.py
│   ├── split_data.py
│   ├── train_model.py
│   └── master_final.py            # Main execution script
│
├── EDA_images/                     # EDA visualization outputs
├── .gitignore                      # Git ignore file
└── README.md                       # Project documentation
🚀 How to Run
Prerequisites
Python 3.8+

Git

Virtual environment (optional but recommended)

Step 1: Clone Repository
bash
git clone https://github.com/yourusername/automated-stock-price-forecasting.git
cd automated-stock-price-forecasting
Step 2: Set Up Virtual Environment
bash
# Create virtual environment
python -m venv .venv

# Activate it
# Windows:
.venv\Scripts\activate
# Mac/Linux:
source .venv/bin/activate
Step 3: Install Dependencies
bash
pip install -r requirements.txt
Step 4: Run the Main Pipeline
bash
python code/master_final.py
Step 5: Launch Streamlit App
bash
streamlit run automated_stock_forecasterrrr/app.py
Step 6: Individual Scripts
bash
# Download data
python code/download_data.py

# Run EDA
python code/eda.py

# Train specific model
python code/Ridge_model.py
python code/random_forest_cv.py
📊 Results
Model Performance Comparison
Model	RMSE	MAE	MAPE	R² Score
Ridge Regression	0.0452	0.0321	1.23%	0.9234
Random Forest	0.0387	0.0289	1.08%	0.9456
Linear Regression	0.0513	0.0378	1.45%	0.8912
Key Findings
✅ Random Forest outperforms linear models

✅ Feature engineering significantly improves performance

✅ Technical indicators are most important features

✅ Model maintains consistency across different stocks

Visual Outputs
📈 Actual vs Predicted plots

📊 Feature importance charts

📉 Residual distribution plots

📋 Error metrics summary

🔮 Future Improvements
Short-term Enhancements
□ Add LSTM/GRU deep learning models
□ Implement real-time data streaming
□ Add more technical indicators
□ Improve feature selection algorithms
Medium-term Goals
□ Integration with multiple data sources
□ Sentiment analysis from news/social media
□ Portfolio optimization integration
□ Risk management metrics
Long-term Vision
□ Deploy as web service/API
□ Mobile application interface
□ Multi-asset portfolio forecasting
□ AI-powered trading assistant
📦 Dependencies
Core Libraries
text
Python 3.8+
pandas>=1.3.0
numpy>=1.21.0
scikit-learn>=1.0.0
matplotlib>=3.4.0
seaborn>=0.11.0
Financial APIs
text
yfinance>=0.1.70
pandas-datareader>=0.10.0
Web Framework
text
streamlit>=1.10.0
plotly>=5.5.0
ML Libraries
text
joblib>=1.1.0
👥 Contributors
Your Name - Initial Work

📄 License
This project is licensed under the MIT License - see the LICENSE file for details.

🙏 Acknowledgments
Yahoo Finance for providing the data API

Scikit-learn community for ML tools

Streamlit for the amazing web framework

📧 Contact
Your Name - saymap693@gmail.com

Project Link: https://github.com/yourusername/automated-stock-price-forecasting

⭐ Show Your Support
If you found this project helpful, please give it a ⭐ on GitHub!

Built with ❤️ using Python, Pandas, Scikit-learn, and Streamlit

