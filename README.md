# 📈 NIFTY 50 Valuation Report: DCF (Gordon Growth Model)

> **Assessing fair value. Powering informed decisions.**

An equity research project that estimates the **intrinsic value of the NIFTY 50 index** as of **12 July 2026** using a Discounted Cash Flow (Gordon Growth / dividend discount) framework, and compares it with the prevailing market level to judge whether the index looks undervalued, fairly valued or overvalued.

**Author:** Utkarsh Malra  |  **Report date:** July 2026  |  **Valuation date:** 12 July 2026

📄 **Full report:** [`nifty_50_valuation.pdf`](Nifty_50_Valuation.pdf)

---

## 🔎 Headline Result

| Metric | Value |
|---|---|
| Current index level (12 Jul 2026) | **₹24,207** |
| DCF intrinsic value (base case) | **≈ ₹17,292** |
| Gap to market | Intrinsic value is **~28.6% below** the market level (market trades ~40% above intrinsic value) |
| Implied P/E at intrinsic value | ~14.9x (vs. 20.9x current trailing P/E) |
| Conclusion | NIFTY 50 appears **overvalued** under base-case assumptions |

> ⚠️ The result is highly sensitive to the cost of equity and terminal growth rate.

---

## 📚 Table of Contents

1. [Project Overview](#-project-overview)
2. [Market Snapshot](#-market-snapshot)
3. [Index Composition](#-index-composition)
4. [Methodology](#-methodology)
5. [Key Inputs & How They Were Derived](#-key-inputs--how-they-were-derived)
6. [DCF Valuation](#-dcf-valuation)
7. [Sensitivity Analysis](#-sensitivity-analysis)
8. [Investment Thesis](#-investment-thesis)
9. [Model Notes & Limitations](#-model-notes--limitations)
10. [Repository Structure](#-repository-structure)
11. [Disclaimer](#-disclaimer)

---

## 🧭 Project Overview

The NIFTY 50 is India's benchmark equity index, covering 50 large-cap, highly liquid companies listed on the NSE across 13+ sectors. It is free-float market-cap weighted, reviewed semi-annually, and underpins mutual funds, ETFs, index funds and F&O contracts.

**Objective:** estimate the index's fair value with a DCF built on:

- expected cash distributions (dividends),
- earnings growth,
- the risk-free rate (India 10-year G-Sec yield),
- an equity risk premium (ERP),
- a terminal growth rate anchored to long-term GDP growth.

**Context (July 2026):** the index trades near 24,000, broadly stable despite geopolitical tension in the Middle East and crude oil volatility. Domestic institutional and retail flows (including strong SIP inflows) have offset foreign outflows, and sentiment is cautiously optimistic on growth, easing inflation and earnings.

---

## 📊 Market Snapshot

| Metric | Value |
|---|---|
| Market capitalisation | ₹1,95,55,622 Cr |
| Current level | 24,207 |
| 52-week high / low | 26,373 / 22,183 |
| P/E | 20.9 |
| Price-to-book | 3.15 |
| Dividend yield | 1.23% |
| Price CAGR: 1Y / 5Y / 10Y | -4.97% / 9.05% / 11.1% |

---

## 🏢 Index Composition

**Top 10 constituents (by rank in the report)**

| Rank | Company | Business |
|---|---|---|
| 1 | Reliance Industries | Diversified conglomerate: retail, telecom (Jio), digital services |
| 2 | HDFC Bank | Universal banking: retail, corporate, SME |
| 3 | ICICI Bank | Universal banking, corporate lending, asset management |
| 4 | Bharti Airtel | Mobile, broadband, digital services |
| 5 | Infosys | IT consulting, digital transformation, cloud, AI |
| 6 | Tata Consultancy Services | IT services, consulting, cloud, AI, BPO |
| 7 | Larsen & Toubro | EPC, infrastructure, defence, technology |
| 8 | State Bank of India | India's largest commercial bank |
| 9 | Axis Bank | Retail and corporate banking, payments, wealth |
| 10 | Mahindra & Mahindra | SUVs, tractors, commercial vehicles, financial services |

**Approximate sector weights**

| Sector | Weight | Sector | Weight |
|---|---|---|---|
| Financial Services | 35–37% | Healthcare | 4–5% |
| Oil, Gas & Consumable Fuels | 10–11% | Metals & Mining | 4% |
| Information Technology | 9–10% | Capital Goods & Services | 3–4% |
| Automobile & Auto Components | 6–7% | Power | 3% |
| FMCG | 6% | Construction Materials | 2–3% |
| Telecommunication | 5% | Consumer Durables | 2–3% |

**Takeaways**

- Financial Services alone is roughly **one-third or more** of the index, so banking drives index performance.
- Financials + Oil & Gas + IT together exceed **50%** of the weight, a high degree of concentration.
- The index blends growth sectors (IT, consumer discretionary) with defensives (FMCG, healthcare, utilities).

---

## 🛠 Methodology

The valuation follows a two-stage dividend discount (Gordon Growth) approach on the index:

```
Cost of Equity (Ke)  = Rf + Beta × ERP
Dividend (year t)    = DPS_2026 × (1 + g_explicit)^t              (explicit stage, 2027E–2030E)
Terminal Value       = DPS_2030 × (1 + g_terminal) / (Ke − g_terminal)
Intrinsic Value      = Σ PV(dividends) + PV(Terminal Value)
Over/Under-valuation = Intrinsic Value vs. market level on 12-Jul-2026
```

**Workflow**

1. Infer index EPS from price and P/E (`EPS = Index level ÷ P/E`).
2. Estimate earnings growth from 1, 3, 5 and 10-year EPS CAGRs.
3. Set the risk-free rate from the 10-year Government of India bond yield.
4. Estimate the ERP (three approaches compared; implied-market-return approach selected).
5. Anchor terminal growth to the median historical GDP growth rate.
6. Assume beta = 1.0 (the index *is* the market portfolio).
7. Project dividends, discount, add terminal value, compare with market.
8. Stress-test with a cost-of-equity × terminal-growth sensitivity grid.

All assumptions use historical data over the **preceding 10 years**, and market data is as of **July 2026** (NSE, RBI and market-risk-premia sources).

---

## 🧮 Key Inputs & How They Were Derived

### 1. Earnings growth: **11%**

EPS is implied from index level ÷ P/E (yearly average P/E used to dampen short-term noise).

| Date | Index | P/E | Implied EPS |
|---|---|---|---|
| Jul-26 | 24,207 | 20.9 | 1,158.2 |
| Jul-25 | 25,355 | 22.8 | 1,111.1 |
| Jul-23 | 19,439 | 22.7 | 858.2 |
| Jul-21 | 15,692 | 28.2 | 556.3 |
| Jul-16 | 8,523 | 23.4 | 364.5 |

| Horizon | 1 yr | 3 yr | 5 yr | 10 yr |
|---|---|---|---|---|
| EPS CAGR | 4.24% | 10.51% | 15.79% | 12.25% |

The average of the four CAGRs is about 10.7%, rounded to **11%** as the base-case growth rate.

### 2. Risk-free rate: **6.72%**

Current 10-year Government of India bond yield (source: RBI), consistent with Damodaran's guidance of using a local-currency government bond for the risk-free rate.

| Tenor | Yield | Min | Max |
|---|---|---|---|
| Current | 6.72% | 6.60% | 7.13% |
| 1-year avg | 6.59% | 6.18% | 6.96% |
| 3-year avg | 7.18% | 6.96% | 7.46% |
| 5-year avg | 6.45% | 5.85% | 6.48% |
| 10-year avg | 6.52% | 6.19% | 7.87% |

### 3. Equity risk premium: **2.29%**

Three approaches were compared:

| Approach | ERP |
|---|---|
| Damodaran implied ERP | 7.08% |
| Sovereign CDS spread approach | 5.23% |
| **Implied market return approach (selected)** | **2.29%** |

The selected approach derives ERP as implied market return minus the 10-year G-Sec yield. Historical series (2015–2026) ranged from 1.39% to 2.63%, with a one-off spike to 6.73% in 2022. Source: market risk premia.

### 4. Terminal growth rate: **7.1%**

Set to the **median** of historical GDP growth rates (2016–2026), chosen over the mean (5.95%) to limit distortion from the COVID-19 contraction and rebound. The logic: a broad index's aggregate earnings cannot outgrow the economy indefinitely.

### 5. Beta: **1.0**

The NIFTY 50 represents the benchmark market portfolio, so beta is 1 by definition under CAPM.

### 6. Cost of equity: **9.01%**

```
Ke = 6.72% + (1.0 × 2.29%) = 9.01%
```

---

## 💰 DCF Valuation

**Dividend projection (₹ per index unit)**

| | 2026A | 2027E | 2028E | 2029E | 2030E |
|---|---|---|---|---|---|
| Dividend per share | 297.7 | 330.5 | 366.8 | 407.2 | 452.0 |

Base dividend = 1.23% yield × 24,207 ≈ 297.7, grown at 11% p.a.

**Valuation summary (as of 12-Jul-2026)**

| Item | Value (₹) |
|---|---|
| PV of explicit-period dividends | 1,406.17 |
| Terminal value at 2030E (undiscounted) | 24,454.10 |
| PV of terminal value (≈ 24,454.10 ÷ 1.0901⁵) | ≈ 15,886 |
| **Intrinsic value** | **≈ 17,292** |
| Current market level | 24,207 |
| Implied downside to intrinsic value | ≈ -28.6% |

---

## 🌡 Sensitivity Analysis

Intrinsic value of the index (₹) for different **terminal growth rates (rows)** and **cost of equity (columns)**. The base case (7.10% growth, 9.01% cost of equity) is **17,292**.

| Terminal growth ↓ / Cost of equity → | 8.01% | 8.51% | 9.01% | 9.51% | 10.01% |
|---|---|---|---|---|---|
| **6.10%** | 17,769 | 14,067 | 11,637 | 9,919 | 8,642 |
| **6.60%** | 23,769 | 17,529 | 13,878 | 11,482 | 9,789 |
| **7.10%** | 36,362 | 23,446 | **17,292** | 13,692 | 11,330 |
| **7.35%** | 49,813 | 28,317 | 19,771 | 15,181 | 12,317 |
| **7.90%** | 294,630 | 53,090 | 29,154 | 20,085 | 15,315 |

**What it shows**

- **Extreme sensitivity:** small moves in cost of equity or terminal growth change the value dramatically (the 7.90% / 8.01% cell blows up because Ke − g is only ~0.1%).
- **Lower discount rate means higher value**, and vice versa.
- Only **6 of 25** scenarios produce a value above the current 24,207, all of them with a very thin spread between cost of equity and terminal growth.

---

## 🧾 Investment Thesis

- The DCF puts intrinsic value at **₹17,292** versus a market level of about **₹24,200**, i.e. the index looks **overvalued** under base-case assumptions.
- Base case rests on **11% earnings growth**, a **9.01% cost of equity** and **7.1% terminal growth**.
- The conclusion is sensitive to the discount rate and terminal growth, so the output should be read as an **analytical estimate, not a precise forecast**.

---

## 🔬 Model Notes & Limitations

**Stated limitations (from the report)**

- Valuation is highly sensitive to the cost of equity and terminal growth rate.
- Actual earnings growth, dividends and macro conditions may differ from the assumptions.
- DCF captures long-term cash flows only; it ignores short-term sentiment, flows and technical factors.

**Additional modelling notes for readers**

- **Dividend-only cash flows.** The model discounts dividends (about a 26% payout of EPS). Buybacks are cited as a cash-return driver but are not separately modelled, which tends to understate distributable cash versus a free-cash-flow-to-equity approach.
- **Abrupt growth step-down.** Growth drops from 11% (2027E–2030E) straight to 7.1% in perpetuity, with no fade period.
- **Low ERP selection.** The selected 2.29% ERP is well below the Damodaran (7.08%) and CDS-based (5.23%) estimates. Using either of those would lower intrinsic value substantially.
- **Terminal growth vs. risk-free rate.** The 7.1% terminal growth sits above the 6.72% risk-free rate, which is typically treated as a ceiling for perpetual growth in a same-currency valuation.
- **Implied market return is partly circular.** An ERP derived from the market's own implied return reflects the cash-flow assumptions behind that calculation, so differences to the market price may partly reflect assumption mismatch rather than mispricing.
- **Cross-check.** Intrinsic value of ~17,292 equates to a P/E of about 14.9x on current EPS, below the 20.9x–28.2x range seen in the historical table.
- **Reading the sensitivity table.** Rows are terminal growth rates and columns are cost of equity (the model values equity cash flows, so the discount rate is cost of equity rather than WACC).

---

## ⚠️ Disclaimer

This project provides an independent NIFTY 50 valuation using publicly available data and a DCF approach, based on assumptions that may differ from actual future outcomes. It is intended **only for educational and research purposes** and must not be treated as investment, financial, legal or tax advice, or as a recommendation to buy, sell or hold any security. 
---

## 🤝 Connect

If you found this useful, ⭐ star the repo, share your feedback, or open an issue. *"The best investment you can make is an informed decision."*

**Prepared by Utkarsh Singh Malra · July 2026**
