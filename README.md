# Surprisal Task — Bitcoin Price Prediction

This repository contains the code and experiment for a data-mining analytics task performed with the professor as a personal training exercise. The goal is to **predict the daily direction of the Bitcoin closing price** (up/down) in a daily timeframe using historical price data and technical indicators.

## Task Overview
- **Task:** Binary classification of Bitcoin daily price movement.
- **Timeframe:** Daily candles (`daily`).
- **Input data:** OHLCV daily candles plus engineered features (returns, range, close/open ratio, volume change, RSI, MACD, Bollinger Bands width/position, ATR, etc.).
- **Target:** A binary label (`target`) representing the direction of the next day's price movement (up/down).

## Repository Structure
```
surprisal-task/
├── btc_daily.csv          # Raw daily OHLCV price data
├── btc_train.csv          # Training set with engineered features + target
├── btc_test.csv           # Test set with engineered features + target
├── btc_prepared.csv       # Final preprocessed dataset ready for modeling
├── business_and_data_understanding.ipynb
├── data_prepration.ipynb
├── modeling.ipynb
├── README.md
├── requirements.txt
└── .gitignore
```

## Notebooks
| Notebook | Purpose |
|---|---|
| `business_and_data_understanding.ipynb` | Business understanding, data overview, and exploratory data analysis (EDA) |
| `data_prepration.ipynb` | Data cleaning, feature engineering (using the `ta` library), preprocessing |
| `modeling.ipynb` | Model training and evaluation with scikit-learn (linear and ensemble models) |

## Requirements
See `requirements.txt` for the Python packages used.

## How to Run
1. Create a virtual environment:
   ```bash
   python -m venv .venv
   .\.venv\Scripts\activate
   ```
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Run the notebooks in order:
   ```bash
   business_and_data_understanding.ipynb
   data_prepration.ipynb
   modeling.ipynb
   ```

## Data Description
| File | Description |
|---|---|
| `btc_daily.csv` | Raw daily candles: `time`, `open`, `high`, `low`, `close`, `Volume` |
| `btc_train.csv` | Training set with features (`return_1`..`return_6`, `candle_range`, `close_open`, `volume_change`, `rsi_14`, `macd`, `macd_signal`, `macd_diff`, `bb_width`, `bb_position`, `atr_14`, `time`, `close`) and `target` |
| `btc_test.csv` | Same schema as the training set |
| `btc_prepared.csv` | Final cleaned/preprocessed dataset used for modeling |

## Notes
- All forecasting/prediction is done on a **daily** timeframe.
- The `target` column is a binarized label; `1` typically means the next day's price moved up, `0` means it moved down.
- The `.venv` folder is intentionally excluded from version control via `.gitignore`.

## License
Add your own license here.
