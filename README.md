# Miguel Palanca

[![Website](https://img.shields.io/badge/miguelpalanca.com-0B1F3A?style=for-the-badge&logo=googlechrome&logoColor=white)](https://miguelpalanca.com)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/miguelpalanca)
[![Meridian](https://img.shields.io/badge/Meridian_dashboard-0066CC?style=for-the-badge&logo=googlechrome&logoColor=white)](https://dash.mpholdings.co/Meridian)
[![Email](https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:contactme@miguelpalanca.com)

## Finance and technology

I work where markets and engineering meet, and my two degrees cover both sides:

- **MSc Applied Finance**, Singapore Management University
- **Master in Business Analytics and Data Science: Advanced AI**, IE University, Madrid (Advanced Tech Track, finishing 2027)

Finance: I interned on ING's Strategic Equity Transactions desk in Singapore, working on total return swap and margin loan deals, pricing swaps with the traders and writing credit packs with the coverage and Risk Management teams. Before that I worked at Natixis Investment Managers, Brown Brothers Harriman and Arrowstreet Capital in Boston, and Chinabank Capital in Manila.

Technology: I have run Linux servers since 2017 and written Python trading code on QuantConnect since 2020. That turned into a systematic equities platform I run on my own Kubernetes clusters.

---

## The platform

Vendor data comes in at one end and broker orders go out at the other. The public repos are cut-down copies of private codebases: the code, without the data, the book or the strategies.

| Project | What it does | Stack |
| --- | --- | --- |
| [Lean Data Platform](https://github.com/Smiggus/lean-data-platform) | Point-in-time market data: vendor ingestion, fundamentals keyed on filing date, split- and dividend-adjusted returns, a survivorship-free universe, a quarantine gate and about 80 data-quality checks. Publishes to Parquet and Iceberg. | Dagster, PostgreSQL / TimescaleDB, Iceberg, k3s |
| [Meridian](https://github.com/Smiggus/meridian-factor-platform) | Daily factor scores for US equities, served over a read-only API. Uses statistical and ML models, including a factor risk model (market, 10 sectors, 7 styles) that blends EWMA with per-stock GARCH(1,1) specific variance. | Python, FastAPI, Dagster, DuckDB |
| [Argus](https://github.com/Smiggus/argus-execution) | Turns strategy targets into orders: nets sleeves into one book, applies risk limits last, sends orders through safety checks and reconciles fills with the broker. Runs on a paper account. | Python, PostgreSQL, Interactive Brokers, LEAN |
| PortDash (private) | Dashboard for the platform: NAV, factor scores, backtests and risk. | React, TypeScript, FastAPI |
| Cluster (private) | Started as one Ubuntu box, now k3s clusters on my own hardware, deployed from a self-hosted GitLab. | Proxmox, k3s, ArgoCD, GitLab CI |

More detail on [miguelpalanca.com/projects](https://miguelpalanca.com/projects/).

---

## IE projects

- [Margin Loan Monitor](https://github.com/Smiggus/Margin-Loan-Monitor): my own extension of our Modern Data Architectures II group project, a NiFi, Kafka and Spark streaming pipeline that sized haircuts from volatility over an ADV-based exit period, floored at Basel minimums, and tracked seven loans through an LTV ladder. The extension maps real share pledges from SEC filings as a graph in Spark GraphFrames (540 pledges, $251bn, 361 issuers, 47 lenders in 2024-2025 filings).
- [Rebalancing MLOps](https://github.com/IE-MBDS-Group-2/2.6-ML-Ops) (group project): a classifier that decides each week whether to rebalance a five-ETF portfolio after costs. Releases are gated on drawdown, and tests run in GitHub Actions on every pull request. The model has not passed the gate yet.
- [Margin Call Early Warning](https://github.com/Smiggus/margin-call-early-warning) (in progress): my own add-on to the MLOps course. Predicts the chance that each margin loan is called within five trading days, and only ships if it clears a recall and precision threshold on unseen data.
- [Rider Weather App](https://github.com/IE-MBDS-Group-2/2.2_PDA_GA) (Advanced Tech Track, in progress): builds on our Python for Data Analytics weather app. Adding a rain radar and features for motorcycle trips in the city, packaged in Docker with Dagster and SQL Server, with releases versioned automatically by CI/CD.

---

## In progress

- **Stressed credit case and IC memo**: takes public filings and builds an Excel model (base, downside and stress cases, liquidity runway, covenant headroom, recovery by tranche) and an investment committee memo. Set up so that adding a company means a new config file. First company: Aston Martin Lagonda.
- **Structured equity pricer**: preferred equity and PIK holdco notes in a sponsor-backed company, with MOIC and IRR across scenarios next to common equity and senior debt.
- **Stressed-company screener**: Dagster and DuckDB pipeline on company filings that flags leverage, interest cover, maturity walls and going-concern notes. UK (Companies House) first, then EU filings.

---

## Earlier work

- [Meridian_QuantConnect](https://github.com/Smiggus/Meridian_QuantConnect): a Meridian strategy on QuantConnect.
- [LEAN_External_DataVendors](https://github.com/Smiggus/LEAN_External_DataVendors): connects QuantConnect LEAN to outside data vendors.
- [PairsTrading](https://github.com/Smiggus/PairsTrading): pairs trading backtester from SMU coursework.
- [OptionsAnalyzer](https://github.com/Smiggus/OptionsAnalyzer), [XGBoost](https://github.com/Smiggus/XGBoost), [EMA crossover with put hedge](https://github.com/Smiggus/200-to-50-EMA-Cross-Over-V4-PutHedge): early strategy and modelling work.

---

## Stack

**Languages:** Python, SQL, TypeScript
**Data and ML:** pandas, NumPy, scikit-learn, XGBoost, PyTorch, DuckDB, Spark, Kafka, NiFi
**Orchestration and storage:** Dagster, PostgreSQL / TimescaleDB, Iceberg, Parquet
**Infrastructure:** Linux, Docker, Kubernetes (k3s), ArgoCD, GitLab CI, GitHub Actions, Proxmox
**Markets:** QuantConnect LEAN, Interactive Brokers API, FastAPI
