# OFA Research: Execution Quality in Order Flow Auctions

**Paper:** "Execution Quality in Order Flow Auctions: Evidence from CoW Protocol and 1inch Fusion"
**Author:** Shehzad Ahmed (First Author)
**Status:** Revised & resubmitted to *Journal of Financial Markets*

## What This Research Is About

How do different crypto exchange aggregators affect execution quality? We analyzed 69,661 trades over 32 days (Summer 2025) comparing CoW Protocol's batch auction model against 1inch Fusion's RFQ model.

## Key Findings

- Batch auctions (CoW Protocol) provide superior execution for retail-sized orders
- Price improvement rates vary significantly by aggregator and market condition
- MEV capture differs substantially between auction and RFQ mechanisms
- Results have implications for DEX design and order flow payment structures

## Contents

| File | Description |
|------|-------------|
| `OFA_COMPREHENSIVE_PAPER.tex` | Full LaTeX paper (revised & resubmitted) |
| `OFA_COMPREHENSIVE_PAPER.pdf` | Compiled PDF |
| `ofa_analysis_documentation.tex` | Analysis methodology |
| `ofa_analysis_documentation.pdf` | Compiled methodology doc |
| `production_ofa_collector.py` | Data collection script (live trading bot) |

## Dataset

- 69,661 trades
- 32-day observation window
- Two aggregators: CoW Protocol, 1inch Fusion
- Asset coverage: BTC, ETH, and major altcoins

## Methodology

Orders routed through both aggregators simultaneously. Execution prices compared against VWAP and TWAP benchmarks. Statistical analysis of price improvement, fill rates, and MEV extraction.

## Status

Revised and resubmitted to *Journal of Financial Markets* following peer review.

---
**Author:** Shehzad Ahmed  |  **Contact:** shehzad0002@gmail.com
