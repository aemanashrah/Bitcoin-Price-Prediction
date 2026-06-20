Bitcoin Price Prediction & Market Trend Forecasting 📈
An end-to-end machine learning pipeline designed to forecast Bitcoin price trends using historical market data and real-time API integration. This project engineers custom technical indicators, benchmarks multiple predictive models, and deploys the best-performing algorithm to predict next-day price action.
🚀 Project Overview
Predicting cryptocurrency prices is notoriously difficult due to extreme market volatility. This project tackles the challenge by treating Bitcoin's OHLCV (Open, High, Low, Close, Volume) data as a strict time-series problem.
By engineering technical momentum and volatility indicators (SMA, EMA, RSI, Bollinger Bands) and evaluating models ranging from statistical regression to deep neural networks, this pipeline identifies the most effective architecture for short-term (T+1) price extrapolation. Finally, it connects to the Binance API to fetch live data and generate real-time forecasts.
✨ Key Features
Strict Time-Series Preprocessing: Implements sequential dataset splitting (80/20) to prevent look-ahead bias and data leakage.
Advanced Feature Engineering: Calculates dynamic market indicators including 20-day Moving Averages, Relative Strength Index (RSI), and Bollinger Bands.
Multi-Model Benchmarking: Trains and compares 5 distinct machine learning architectures:
Linear Regression (Baseline)
Random Forest & XGBoost (Ensemble Trees)
Support Vector Machines (SVM)
Long Short-Term Memory (LSTM Neural Networks)
Real-Time API Inference: Connects directly to the Binance public API to pull the latest 60-day market k-lines, applies the exact preprocessing scaler, and predicts tomorrow's trend.
🛠️ Tech Stack
Language: Python 3.8+
Data Processing & Feature Engineering: Pandas, NumPy, Scikit-Learn
Machine Learning: Scikit-Learn, XGBoost, TensorFlow / Keras (LSTM)
Data Visualization: Matplotlib, Seaborn
API Integration: requests (Binance API)
📊 Key Insights & Results
Following comprehensive RMSE (Root Mean Squared Error) and R2 evaluation, the project yielded a counter-intuitive but statistically sound conclusion:
Tree-Based Failure: Models like XGBoost and Random Forest struggled significantly. As interpolators, decision trees failed the "extrapolation test" when Bitcoin hit new All-Time Highs in the test set that did not exist in the training data.
Winning Architectures: Linear Regression performed best for immediate next-day price prediction by successfully extrapolating linear momentum, while the LSTM model proved highly resilient in capturing long-term temporal sequences and volatility shocks.

<img width="827" height="438" alt="Screenshot 2026-06-19 201927" src="https://github.com/user-attachments/assets/e216997e-ba7a-4191-b039-c225eae56f8d" />
