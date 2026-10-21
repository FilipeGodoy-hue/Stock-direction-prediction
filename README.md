# Stock-direction-prediction

Machine learning project that predicts the next-day direction (up or down) of stocks and ETFs, using Python and scikit-learn. Currently BOVA11 only; a Streamlit app is planned.

## Goal

Predict whether BOVA11 will close higher or lower tomorrow than it did today.

## Data

Daily prices of BOVA11 (ticker BOVA11.SA), downloaded with the yfinance library, from 2015 onwards.

## Method

- Target `y`: 1 if the next day's close is higher than today's, 0 otherwise.
- Features: today's return, yesterday's return, 5-day mean return and 5-day volatility.
- Chronological split: 80% train (until 2024-06-13) and 20% test (from 2024-06-14).
- Model: logistic regression (scikit-learn), compared with a baseline that always guesses the most frequent class.

## Results

The model reached 53.0% accuracy vs. 52.8% for the baseline, which is not a meaningful difference. It predicted "up" on 586 of 587 test days, so it behaves like an "always up" guess. This is not a trading strategy or financial advice.

## How to run

Windows (PowerShell):

```
python -m venv .venv
.\.venv\Scripts\Activate.ps1
pip install -r requirements.txt
```

Then open `notebooks/01_explorar_dados.ipynb`.

## Next steps

Add richer features, try other models, build the Streamlit app and explore volatility prediction.