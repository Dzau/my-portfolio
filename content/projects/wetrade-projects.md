---
title: "WeTrade: AI-Powered Automated Stock Trading"
date: 2025-05-26
draft: false
summary: "An automated stock trading system using an LSTM neural network that combines technical analysis and news sentiment to democratize long-term investing."
tags: ["Python", "PyTorch", "AI", "LSTM", "Sentiment Analysis", "Financial Technology"]
---

## Overview

**WeTrade** is an automated stock trading system designed to make profitable, long-term investing accessible to everyone, especially those without extensive financial expertise or resources. The project addresses the significant inequality in stock market participation by providing a tool that automates complex trading decisions.

The core of WeTrade is a **Long Short-Term Memory (LSTM) neural network** that predicts stock price movements. Unlike traditional trading bots, our model integrates three key data sources for a more holistic analysis:
1.  **Historical Market Data:** Daily price and volume data for all NASDAQ, S&P 500, and NYSE companies since 2000.
2.  **Technical Indicators:** Four widely used metrics (MACD, RSI, OBV, and SMA) are calculated to identify market trends and momentum.
3.  **News Sentiment Analysis:** We developed a sophisticated web scraper to analyze over 4 million financial news articles from Yahoo Finance, assigning a sentiment score to each one.

During its first week of live trading, the system achieved a **4% profit**. The project also includes a user-facing website that provides a personalized interface for monitoring investments and fostering financial literacy.

## Technical Deep Dive

### Data Collection & Sentiment Analysis
A major challenge was scraping and processing the vast amount of news data required to train the model. After initial attempts with sources like Forbes and The Wall Street Journal proved insufficient, we pivoted to Yahoo Finance for its extensive archives.

To overcome Yahoo's request rate-limiting, we engineered a novel solution using a **free /48 IPv6 subnet** from Hurricane Electric and low-level socket programming in Python. This allowed us to bypass the rate limit and increase our scraping speed from ~400 articles per minute to over **50,000 requests per minute**, enabling us to build our historical sentiment database efficiently.

### The Predictive Model
The final, compiled dataset combines daily stock prices, the four technical indicators, and our calculated sentiment scores. This rich, sequential data was used to train a **PyTorch-based LSTM neural network**. The model was designed to predict the next day's closing price based on the previous 30 days of data. Backtesting over a 5-year period showed a **62% accuracy** in predicting market direction, outperforming traditional models.

## Links

* [**View Source Code on GitHub**](https://github.com/Dzau/wetrade)