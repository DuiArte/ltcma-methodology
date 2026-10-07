<sub>**DuiArte** · quantitative research · [methodology](https://github.com/DuiArte/ltcma-methodology) · [strategies](https://github.com/DuiArte/static-drift-weight) · [framework](https://github.com/DuiArte/signallib-framework)</sub>

# LTCMA Methodology

**The long-term capital-market assumptions published on the LTCMA research site: every number, and how each one is built.**

![status](https://img.shields.io/badge/status-research-blue) ![license](https://img.shields.io/badge/license-CC--BY--NC--4.0-green) ![model built](https://img.shields.io/badge/model%20built-2026--10--04-lightgrey)

---

**As of model built 2026-10-04.** Expected returns are annual, nominal and in US-dollar terms over
a 12-year horizon. Every figure in this repository is taken from the model outputs that the
[LTCMA research site](https://duiarte.github.io/ltcma/) already publishes; [`SOURCE.md`](SOURCE.md) lists each output
and its version.

## Base case at a glance

| Asset | Class | Expected return (base) | Volatility (15-year) | Sharpe (base)¹ |
|---|---|---:|---:|---:|
| US LargeCap | Equity | 5.99% | 13.96% | 0.19 |
| US SmallCap | Equity | 6.48% | 19.09% | 0.17 |
| Mexico Eq | Equity | 8.00% | 22.68% | 0.21 |
| Brazil Eq | Equity | 8.79% | 31.77% | 0.17 |
| China Eq | Equity | 7.42% | 22.60% | 0.18 |
| Japan Eq | Equity | 6.43% | 13.79% | 0.23 |
| UK Eq | Equity | 7.04% | 15.34% | 0.24 |
| France Eq | Equity | 7.20% | 17.86% | 0.22 |
| EM Eq | Equity | 8.00% | 17.22% | 0.27 |
| DM exUS Eq | Equity | 7.73% | 14.51% | 0.31 |
| US Cash TBill | Fixed Income | 3.30% | 0.55% | n/a |
| US Treas Interm | Fixed Income | 4.50% | 6.20% | 0.19 |
| US Treas Long | Fixed Income | 4.80% | 12.98% | 0.12 |
| US TIPS | Fixed Income | 4.50% | 5.00% | 0.24 |
| US IG Corp | Fixed Income | 5.00% | 7.49% | 0.23 |
| US HighYield | Fixed Income | 5.00% | 7.30% | 0.23 |
| EM USD Sov | Fixed Income | 6.00% | 9.38% | 0.29 |
| EM Local Debt | Fixed Income | 4.80% | 10.97% | 0.14 |
| Global Agg exUS | Fixed Income | 3.80% | 4.03% | 0.12 |
| Mexico Govt Local | Fixed Income | 6.30% | 15.04% | 0.20 |
| US REITs | Real Asset | 6.30% | 17.02% | 0.18 |
| Global REITs exUS | Real Asset | 6.40% | 16.19% | 0.19 |
| Commodities | Real Asset | 3.50% | 17.01% | 0.01 |
| Gold | Real Asset | 3.30% | 16.13% | 0.00 |

¹ (base-case expected return − the cash expected return of 3.30%) ÷ 15-year volatility.

Equity returns depend on a valuation-reversion dial, λ; the base case is λ = 0.5. The full set
(three λ settings, two volatility estimates, two correlation matrices) is in `assumptions/`.

## What's here

- **`assumptions/capital_market_assumptions.csv`**: one row per asset, with expected return at
  λ = 0, 0.5 and 1, both volatility estimates, the base-case Sharpe ratio, and the published
  basis of each non-equity return.
- **`assumptions/equity_building_blocks.csv`**: the components that add up to each equity
  expected return.
- **`assumptions/correlation_ledoit_wolf.csv`**, **`assumptions/correlation_sample_15y.csv`**:
  the two published correlation matrices.
- **`methodology/`**: how each number is built:
  [overview](methodology/00_overview.md) ·
  [expected returns](methodology/01_expected_returns.md) ·
  [risk model](methodology/02_risk_model.md).

## What's deliberately *not* here

Portfolio weights, anything account-specific, and the model code. This repository mirrors the
published assumptions; the site carries the charts and the full written report.

## License

[CC BY-NC 4.0](LICENSE): share and adapt for non-commercial use, with attribution.
Research, not investment advice.

## Related

Part of the DuiArte quantitative-research family · [ltcma-methodology](https://github.com/DuiArte/ltcma-methodology) · [static-drift-weight](https://github.com/DuiArte/static-drift-weight) · [signallib-framework](https://github.com/DuiArte/signallib-framework) · [backtests-archive](https://github.com/DuiArte/backtests-archive)
