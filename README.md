# Opening Range Breakout (ORB) Strategy on QQQ ETF

This repository provides a complete Python implementation and backtest of the Opening Range Breakout (ORB) intraday trading strategy applied to the **QQQ ETF** (Nasdaq-100).  
The implementation is inspired by the academic research paper:

> **Can Day Trading Really Be Profitable?**  
> Carlo Zarattini & Andrew Aziz, 2024  
> SSRN ID: [4416622](https://ssrn.com/abstract=4416622)

---

## Project Objectives

- Implement the ORB strategy on minute-level data for QQQ (2016–2024)
- Simulate long/short positions based on early session price action
- Evaluate strategy performance against a buy-and-hold benchmark
- Explore risk-adjusted returns using metrics such as Sharpe and Sortino Ratios
- Compare base QQQ strategy with a leveraged version using TQQQ

---

## Strategy Description

The ORB strategy (Opening Range Breakout) is a popular day trading method based on early price movements:

- The trading signal is generated using the **first 5-minute candle** after market open.
- **If bullish**: a **long position** is opened at the second candle’s open.
- **If bearish**: a **short position** is opened instead.
- A **stop loss** is placed at the high (short) or low (long) of the first candle.
- A **profit target** of **10× the risk (10R)** is used, or the position is closed at end of day (EoD).
- The strategy includes basic risk management: **1% risk per trade**, **4x leverage**, and **$0.0005/share** in commissions.

This approach captures early volatility and follows directional momentum intraday.
