# Stock Volatility Prediction with LSTM

This project uses a Long Short-Term Memory (LSTM) neural network to predict the rolling volatility of two stock ETFs: QQQ (Invesco QQQ Trust) and SPY (SPDR S&P 500 ETF Trust).

The project consists of two main parts:
1.  **`lstm_final.py`**: The original training script used to gather data, preprocess it, train two separate LSTM models (one for each stock), and save the trained models, scalers, and evaluation metrics.
2.  **`app.py`**: A Streamlit application that provides a user-friendly dashboard. It allows you to select a stock and visualize the model's predicted volatility against the actual volatility for the most recent trading days, along with the model's performance metrics.

## Setup Instructions

1.  **Clone the repository:**
    ```bash
    git clone <your-repo-url>
    cd <your-repo-directory>
    ```

2.  **Create a virtual environment (recommended):**
    ```bash
    python -m venv venv
    source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
    ```

3.  **Install the dependencies:**
    ```bash
    pip install -r requirements.txt
    ```

4.  **Run the training script (initial step):**
    Before running the app, you must first run the original script to train the models and save the necessary files. This script will create `qqq_model.keras`, `spy_model.keras`, `qqq_feature_scaler.pkl`, `qqq_target_scaler.pkl`, `spy_feature_scaler.pkl`, `spy_target_scaler.pkl`, and `model_metrics.json`.
    ```bash
    python lstm_final.py
    ```

5.  **Run the Streamlit application:**
    Once the models and other files are generated, you can launch the dashboard.
    ```bash
    streamlit run app.py
    ```

## Project Files

* `app.py`: The Streamlit dashboard application.
* `requirements.txt`: List of required Python packages.
* `lstm_final.py`: The full training and evaluation script.
* `qqq_model.keras`, `spy_model.keras`: The saved LSTM models for QQQ and SPY.
* `qqq_feature_scaler.pkl`, `qqq_target_scaler.pkl`: The saved `MinMaxScaler` objects for QQQ.
* `spy_feature_scaler.pkl`, `spy_target_scaler.pkl`: The saved `MinMaxScaler` objects for SPY.
* `model_metrics.json`: A JSON file containing the final evaluation metrics.
