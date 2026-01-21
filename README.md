# Quantitative Trading Bot

This repository provides a lightweight quantitative trading bot that backtests a
volatility-targeted trend strategy (EMA crossover with position sizing).
It includes risk controls and performance metrics such as Sharpe ratio and max drawdown.

> **Disclaimer**: This project is for research and educational use only. Past
> performance does not guarantee future results. You are responsible for ensuring
> compliance with any applicable regulations and broker requirements.

## Features
- EMA-based trend signal.
- Volatility targeting with leverage caps.
- Transaction cost modeling.
- Performance report (annual return, Sharpe ratio, drawdown).

## Getting Started

### Requirements
```bash
pip install -r requirements.txt
```

### Data Format
Provide a CSV with at least:
- `date` (parseable date)
- `close` (or specify another column via `--price-column`)

Example columns: `date,open,high,low,close,volume`

### Run a Backtest
```bash
python -m src.trading_bot path/to/data.csv --price-column close
```

### Customize Strategy Parameters
```bash
python -m src.trading_bot data.csv \
  --fast-ema 10 \
  --slow-ema 50 \
  --vol-lookback 20 \
  --target-vol 0.12 \
  --max-leverage 1.5 \
  --transaction-cost-bps 2.0
```

## Next Steps
- Integrate live data feeds and order execution (broker APIs).
- Add robust walk-forward validation.
- Expand to multi-asset portfolios and risk parity sizing.

## Project Structure
```
src/
  trading_bot.py   # Strategy, backtest, CLI
```
