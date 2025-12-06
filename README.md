# Smart Investment Agent

A Python + FastAPI project for **analyzing stocks in US and Israeli (TASE) markets**, generating data-driven investment signals, rankings, and automated alerts. Integrated with n8n for workflow automation.

---

## Features

- Pulls stock data from Yahoo Finance (US & TASE)
- Computes technical indicators: SMA, RSI, Momentum
- Supports fundamental indicators: P/E, Revenue Growth, etc.
- Generates signal per stock: BUY / HOLD / SELL + confidence score
- Works with both US and Israeli markets
- Optional automated alerts via n8n (Google Sheets, Telegram, Slack)
- Backtesting support via notebooks

---

## Structure

smart-invest-agent/
├─ README.md
├─ .gitignore
├─ docker-compose.yml
├─ app/
│ ├─ main.py # FastAPI backend
│ ├─ requirements.txt
│ └─ modules/ # Custom modules for indicators, scoring
└─ notebooks/
└─ backtest.ipynb # Jupyter notebooks for testing strategies

---

## Installation

### 1. Clone the repo
```bash
git clone https://github.com/Tombh6/smart-invest-agent.git
cd smart-invest-agent
