# Execution Quality in Order Flow Auctions

**Paper:** "Execution Quality in Order Flow Auctions: Evidence from CoW Protocol and 1inch Fusion"
**Author:** Shehzad Ahmed (First Author)
**Status:** Revised & resubmitted to *Journal of Financial Markets* (following peer review)

---

## What This Research Is About

How do different crypto exchange aggregator mechanisms affect execution quality for retail traders? We ran live trades through two competing systems simultaneously:

- **CoW Protocol** — Batch auction model. All trades in a batch execute at a single clearing price. No MEV possible within a batch.
- **1inch Fusion** — Request-for-Quote (RFQ) model. Traders get a price quote from professional market makers. Execution is instant but MEV is possible.

**69,661 trades over 32 days (Summer 2025). BTC, ETH, and major altcoins.**

---

## Why This Matters

Order flow is the most valuable commodity in markets. When you trade on a DEX aggregator, you are selling your order flow. The mechanism that receives your order determines:

1. **Who profits from your trade information** — batch auctions share it equally; RFQ models let market makers profit
2. **How much MEV you suffer** — batch auctions neutralize MEV; RFQ passes it through
3. **Whether retail gets price improvement** — CoW's Coincidence of Wants mechanism can match orders without crossing the spread

The aggregator you choose is not a UX decision. It's a financial decision worth real money.

---

## Key Findings

### Batch Auctions Outperform for Retail Orders

CoW Protocol's batch auction model provides superior execution for retail-sized orders because:

- **Coincidence of Wants:** When two traders want opposite sides, they match directly — zero spread cost
- **No MEV within batches:** The batch clearing price is set before MEV can be extracted
- **Price improvement:** Retail orders matched against each other get fills inside the spread

### MEV Capture Differs Substantially

The RFQ model (1inch) passes MEV opportunities to market makers. The types of MEV observed:
- Sandwich attacks on large orders
- Latency arbitrage between venues
- Toxicity from informed trading flow

### Price Improvement Rates Are Market-Condition Dependent

Under calm market conditions, CoW's price improvement is ~2-4x better than RFQ.
Under volatile conditions, both mechanisms suffer — but CoW's losses are more predictable.

---

## Academic Context

This paper extends the MEV literature (Daian et al. Flash Boys 2.0) to the retail aggregator layer, and applies order flow auction theory (SEC Trade Through Rule, batch trading proposals) to DEX design.

**Citations:**
- Daian, P. et al. (2019). Flash Boys 2.0: Frontrunning, Transaction Reordering, and Consensus Instability in Decentralized Exchanges. *arXiv.*
- SEC (2020). Proposed Rule on Exchange Act Rule 615 (Regulation Best Execution).
- Batch trading framework: Budish, Cramton & Shim (2015). The High-Frequency Trading Arms Race. *QJE.*

---

## Methodology

### Data Collection

```
Orders routed through both aggregators simultaneously:
- CoW Protocol SDK → batch auction execution
- 1inch Fusion API → RFQ execution
- Both platforms queried at the same millisecond
- Execution prices recorded vs VWAP and TWAP benchmarks
```

### Analysis

- Price improvement measured as: (execution price - benchmark price) / benchmark price
- Negative = better execution (you got a better price than the benchmark)
- Stratified by: order size, market condition, asset, time of day
- MEV extraction identified via transaction-level analysis on-chain

---

## Contents

| File | Description |
|------|-------------|
| `OFA_COMPREHENSIVE_PAPER.tex` | Full LaTeX paper — revised & resubmitted |
| `OFA_COMPREHENSIVE_PAPER.pdf` | Compiled PDF |
| `ofa_analysis_documentation.tex` | Analysis methodology (detailed) |
| `ofa_analysis_documentation.pdf` | Compiled methodology doc |
| `production_ofa_collector.py` | Live data collection bot (automated) |

---

## Dataset

| Metric | Value |
|--------|-------|
| Total trades | 69,661 |
| Observation window | 32 days (Summer 2025) |
| Aggregators | CoW Protocol, 1inch Fusion |
| Assets | BTC, ETH, and major altcoins |
| Order size range | Retail (<\$10K equivalent) |
| Collection method | Simultaneous dual-routing |

---

## Implications

### For Traders
Choose batch auction aggregators (CoW Protocol) for retail-sized orders. The Coincidence of Wants mechanism means you might trade against someone on the other side of the market — for free, with no spread, no MEV.

### For DEX Design
The aggregator mechanism is not a UX detail. It determines who captures value from order flow. Batch auctions redistribute value to traders; RFQ redistributes it to market makers.

### For Researchers
The retail aggregator layer is an underexplored source of execution quality variation. MEV at the DEX routing layer is distinct from MEV within individual DEXes.

---

## Status

**Revised & resubmitted** to *Journal of Financial Markets* following peer review. First round reviewers requested:
- Additional robustness checks on price improvement under extreme volatility
- Deeper analysis of MEV extraction patterns by asset

Both addressed in the revised submission.

---

## Citation

```
Ahmed, S. (2026). Execution Quality in Order Flow Auctions: Evidence from
CoW Protocol and 1inch Fusion. [Revise & Resubmit] Journal of Financial Markets.
```

---
**Author:** Shehzad Ahmed  |  **Contact:** shehzad0002@gmail.com
**GitHub:** github.com/shehzadahmed-xx/arcus-ofa-research
