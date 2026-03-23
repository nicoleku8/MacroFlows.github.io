---
title: 'Equity Index and Fixed Income Derivatives I'
date: 2026-03-20
permalink: /posts/2026/03/equity-index-and-fixed-income-derivatives/
tags:
  - Stock Index
  - Options Trading
  - Central Bank Policy
---

This project started from background reading in *Stock Index & Futures* by Gidel, *The Volatility Edge in Options Trading* by Jeff Augen, and *The Option Trader Handbook* from Jabbour Budwich. The basic framework for choosing indices and the option position framework was driven by the methodologies introduced in these texts.

### **The Primary Motivation**
The primary motivation to construct this project is to study the historical patterns of the U.S. equity market (indexes), fixed income markets, and U.S. central bank policies. The premise comes from the following:

1. The objective of central bank policy is inflation and unemployment. The primary way to control the Fed Funds rate has an enormous impact on the Fixed Income market with every release. However, equity indices provide great proxies for how the market is performing by sectors. Can we read the state of the market as the FOMC reads it with equity index data and leverage that information in fixed income market instruments and derivatives? Furthermore, can we have a good grasp of macro volatility estimation? 

### **Why Stock Index?**
Index option prices and index figures are highly accessible. They capture the state of the market by sectors and countries, which is vital for recognizing the **Macro Flow**. Connecting back to my central theme: *How is the big flow of the market going?* While all components are inseparable, the stock market (equities) provides the single most beneficial piece of information on how the market is actually performing. 

* **Central Banks:** Control inflation and unemployment.
* **Fixed Income:** Source to fund the government and control capital flow.
* **FX:** Handles currency conversion for trade negotiations.
* **Commodities:** The basic building blocks of production.
* **Equities:** The real-time pulse of market performance.

Consequently, I want to explore and implement basic systematic strategies (e.g., trend following, cross-asset correlation, and carry trades). This requires understanding different option positions and how those positions change as the underlying price moves and expiration approaches. I want to connect option pricing theories to the realities of the market measured by equity indices and central bank policies, while accounting for known risks like bid-ask spreads, volatility swings, put-call parity violations, and liquidity risks. The framework to explore different kinds of option positions was adopted by *The Volatility Edge in Options Trading*. 

---

### **Steps to Finish This Project**

**1. Building the Dataset**
* **Central Bank Policy & Macro:** Use the **FRED (St. Louis Fed) API** to pull the Effective Federal Funds Rate (`FEDFUNDS`), CPI (`CPIAUCSL`), and Unemployment (`UNRATE`) directly into Python.
* **Fixed Income Proxies:** Since OTC bond data is difficult to access, liquid Bond ETFs (like **TLT** for 20+ Year Treasuries or **LQD** for Investment Grade Corporates) will serve as proxies.
* **Equities & Futures:** **Yahoo Finance (`yfinance`)** provides `ES=F` (S&P 500 E-mini) and `ZN=F` (10-Year Note) historical data. 

**2. Asset Correlation and Fundamental Insights**
* Explore the dataset and perform statistical analysis on cross-asset relationships.
* Rather than a pure relative value (RV) approach focused on statistical arbitrage, the systematic strategies here will be built upon **market speculation** using popular strategies: **Trend Following, Carry Trade, and Momentum.**

**3. Practical Application**
* Review the basics of option theories and trading strategies.
* Determine which strategies to deploy and establish a transparent backtesting process.
* Evaluate if the resulting strategy is a relative value play or a market speculation.

**4. Evaluation (Risk & Expected Return)**
* Drawing from *Value and Momentum Everywhere* and *Expected Returns* by Ilmanen.
* Explore how an asset can be valued in its "book" compared to its current market value and what that implies for the strategy's expected return.

---

### **Striking the Balance: Practicality vs. Theory**

While planning for the project, some concerns were having a realistic expectation on the result. It is impossible to construct a whole regime-switching model with harvesting factors from different datasets as I don’t have enough data infrastructure and time. Even if my project doesn’t have a conclusion like *Value and Momentum Everywhere* that was able to quantify exact risk premiums, my goal is to construct strategies to gain experience in managing complex positions (e.g., sizing, identifying drawdowns, timing). 

Moreover, I learned on a trading floor that there is no time for months of research to find a perfect correlation. That is often the job of a dedicated research team. What matters most in execution was: **Can you accurately quantify the risk in your strategy quickly?**

* **Time:** Build a process that shortens the research loop for risks and returns and implementation of the strategy.
* **Risk:** Quantifying liquidity risk and internal institutional trading risks in a short window.

---

### **Resources**
* [*The Volatility Edge in Options Trading*](https://www.amazon.com/Volatility-Edge-Options-Trading-Strategies/dp/0133925404) by Jeff Augen
* [*Cross-Asset Correlation Shifts in Crisis Periods: A Framework for Portfolio Hedging*](file:///Users/nicoleku/Downloads/Cross-Asset+Correlation+Shifts+in+Crisis+Periods_+A+Framework+for+Portfolio+Hedging++(1)%20(1).pdf) by Kapil Kumar
* [*Value and Momentum Everywhere*](https://w4.stern.nyu.edu/facdir/lpederse/papers/ValMomEverywhere.pdf) by Asness, Moskowitz, and Pedersen
* [*Expected Returns on Major Asset Classes*](https://www.aqr.com/Insights/Research/Book/Expected-Returns-on-Major-Asset-Classes) by Antti Ilmanen
* [*Fundamental Edge*](https://docs.google.com/presentation/d/1t-oMRNqkCltU5bHC7ndfn_gUi9CTesempKkPPHZdjNM/edit?slide=id.g2f4a3aeb994_0_63#slide=id.g2f4a3aeb994_0_63) by Giuseppe Paleologo
* [*New Research into stock-bond correlation shows when they correlate and when they don’t*](https://www.robeco.com/en-uk/insights/2024/05/new-research-into-the-stock-bond-correlation-shows-when-they-correlate-and-when-they-don-t)
* [*Seizing Opportunities with Active Fixed Income ETFs*](https://am.gs.com/en-fi/institutions/insights/article/2025/seizing-potential-opportunities-with-active-fixed-income)
* [*Cross-asset Time Series Momentum Strategy: A new perspective*](https://research-repository.griffith.edu.au/server/api/core/bitstreams/9b856f22-f0e0-4b36-99e5-5db189686428/content)
