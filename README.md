# Smart Investment Agent

**Description:** Smart Investment Agent analyzing US and Israeli (TASE) stocks using technical and fundamental indicators, providing data-driven signals, rankings, and automated alerts via n8n integration.

A Python + FastAPI project for analyzing stocks in US and Israeli (TASE) markets, generating data-driven investment signals, rankings, and optional automated alerts. Integrated with n8n for workflow automation.

Features:
- Pulls stock data from Yahoo Finance (US & TASE)
- Computes technical indicators: SMA, RSI, Momentum
- Supports fundamental indicators: P/E, Revenue Growth, etc.
- Generates signal per stock: BUY / HOLD / SELL + confidence score
- Works with both US and Israeli markets
- Optional automated alerts via n8n (Google Sheets, Telegram, Slack)
- Backtesting support via Jupyter notebooks

Project Structure:
smart-invest-agent/
├─ README.md
├─ .gitignore
├─ docker-compose.yml
├─ app/
│  ├─ main.py
│  ├─ requirements.txt
│  └─ modules/
└─ notebooks/
   └─ backtest.ipynb

.gitignore (for Python):
__pycache__/
*.py[cod]
*$py.class
venv/
.env/
*.log
.DS_Store
.ipynb_checkpoints/

Installation:
1. Clone the repository:
git clone https://github.com/Tombh6/smart-invest-agent.git
cd smart-invest-agent

2. Run with Docker Compose:
docker-compose up --build
This will start the FastAPI server on http://localhost:8000.

Usage:
POST request to get signals:
POST http://localhost:8000/signals
Content-Type: application/json

{
  "tickers_us": ["AAPL", "MSFT", "TSLA"],
  "tickers_ta": ["TEVA.TA", "BANKH.TA", "ICL.TA"]
}

Response example:
[
  {
    "ticker": "AAPL",
    "last_price": 180.5,
    "sma50": 175.2,
    "signal": "BUY",
    "score": 0.88
  },
  {
    "ticker": "TEVA.TA",
    "last_price": 35.1,
    "sma50": 36.0,
    "signal": "SELL",
    "score": 0.65
  }
]

Adding New Stocks:
{
  "tickers_us": ["GOOG", "AMZN"],
  "tickers_ta": ["NICE.TA", "ELAL.TA"]
}

Notes:
- Use a .env file or n8n credentials for API keys (Alpha Vantage, IEX) if needed.
- Keep .gitignore intact to avoid uploading local environments, logs, or cache files.
- MIT License ensures the project is open for contribution, modification, and reuse.

MIT License © 2025 Tom
Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:
The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.
THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
