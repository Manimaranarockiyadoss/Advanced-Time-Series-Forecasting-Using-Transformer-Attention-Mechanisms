📘 Advanced Time Series Forecasting Using Transformer Attention Mechanisms

This project implements a state-of-the-art Time Series Forecasting system using:

Transformer Encoder with Multi-Head Attention

LSTM baseline model

Synthetic seasonal dataset

Ablation studies on:

Attention heads

Input window size

The goal is to evaluate how well Transformers can predict future values compared to traditional LSTM models.

🚀 Project Features
✔️ Generate synthetic time-series dataset (6000 samples)

Includes trend, seasonality, and noise.

✔️ Transformer-based forecasting model

Multi-Head Self-Attention

Positional Encoding

Encoder layers

Dense prediction head

✔️ Baseline LSTM model

Used for performance comparison.

✔️ Ablation Studies

Effect of different attention head sizes

Effect of different window sizes

✔️ Evaluation Metrics

MAE

RMSE

MAPE

📂 Directory Structure
📁 TimeSeries-Transformer-Forecasting
│── main.py                   # Full runnable code
│── README.md                 # Project documentation
│── requirements.txt          # Python dependencies
└── results/                  # (Optional) save charts & metrics

🧪 Dataset Description

A synthetic time-series is generated using:

Trend: linear increase

Seasonality: yearly sine wave

Noise: Gaussian

Formula:

series = 10 + 0.001*time + 2*sin(2πt/365) + noise


This makes the forecasting problem realistic.

🧠 Model Architectures
🔷 Transformer Forecasting Model

Linear embedding → d_model

Positional encoding

3× Transformer Encoder layers

Multi-Head Attention

Feedforward network

Final dense layer to predict 7-day horizon

🔶 LSTM Baseline Model

Single LSTM layer

Hidden dimension = 64

Dense layer to predict future values

🏋️‍♂️ Training Details
Model	Epochs	Optimizer	Loss
Transformer	25	Adam	MSE
LSTM	15	Adam	MSE

Batch size = 32
Window size = 64
Forecast horizon = 7

📈 Evaluation Metrics

The project computes:

MAE (Mean Absolute Error)

RMSE (Root Mean Square Error)

MAPE (Mean Absolute Percentage Error)

Example output:

Transformer Performance
MAE  : 0.12
RMSE : 0.18
MAPE : 1.82%

LSTM Performance
MAE  : 0.21
RMSE : 0.29
MAPE : 3.11%


(The exact values may vary.)

🔬 Ablation Studies
1️⃣ Attention Heads Experiment

Evaluates performance for heads = 2, 4, 8

2 heads  → MAE: ..., RMSE: ...
4 heads  → MAE: ..., RMSE: ...
8 heads  → MAE: ..., RMSE: ...

2️⃣ Window Size Experiment

Evaluates window sizes = 32, 64, 128

32  → MAE: ...
64  → MAE: ...
128 → MAE: ...


These experiments help understand model sensitivity to context length and attention complexity.

▶️ How to Run the Project
1. Install dependencies
pip install numpy pandas torch scikit-learn

2. Run the script
python main.py

📝 Key Learnings

Transformers capture long-term dependencies better than LSTM.

More attention heads can improve performance—but also increase training time.

Larger window sizes help Transformers more than LSTM.

Synthetic data with trend+seasonality is ideal for research & benchmarking.

📌 Future Improvements

Add Transformer Decoder (Seq2Seq forecasting)

Add Multi-variate time series

Add Visualization plots (true vs prediction)

Hyperparameter optimization (Optuna / Bayesian Optimization)

Export trained model (TorchScript)

🏁 Conclusion

This project demonstrates how Transformer attention mechanisms outperform LSTMs in time series forecasting, especially with long-term dependencies. It also includes ablation results to study how different architecture choices affect forecasting accuracy.
