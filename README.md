# NQ Futures — ORB Scale-Out Strategy

## 📊 Strategy Overview

This repository contains a backtest of an **Opening Range Breakout (ORB) strategy** with a 3‑stage scale‑out mechanism, applied to **E‑mini Nasdaq‑100 (NQ) futures** hourly data.

### Trade Lifecycle

| Stage | Trigger | Action |
|-------|---------|--------|
| **Entry** | 15:00 UTC close breaks above/below 14:00 UTC ORB close | Enter full position |
| **Scale 1** | Unrealised profit ≥ 1× ATR14 | Close 33% → Move SL to breakeven |
| **Scale 2** | Unrealised profit ≥ 2× ATR14 | Close another 33% |
| **Remainder** | Profit ≥ `risk_reward × ATR14` | Final 34% exits at full TP |
| **Stop Loss** | Initial SL = `sl_atr_mult × ATR14` | Moves to breakeven after Scale 1 |

---

## 📁 Repository Structure
├── NQ_ORB_v4.ipynb # Main backtest notebook

├── README.md # This file

└── (output) NQ_1H_720D.csv # Downloaded data (generated on run)
