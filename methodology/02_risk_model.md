# 02 · Risk model

*As of model built 2026-10-19.*

## Volatility: two estimates

| Estimate | How it is built | Column |
|---|---|---|
| 15-year | Standard deviation of the last 15 years of monthly log returns, annualised (× √12). | `volatility_15y_pct` |
| Blended | Volatility from a Ledoit-Wolf-shrunk covariance of monthly returns, blended 50/50 in variance with a long-history volatility for the 11 assets that have one; the other 13 use the shrunk estimate alone. | `volatility_blended_pct` |

The base-case Sharpe ratio in `capital_market_assumptions.csv` is (base-case expected return −
the cash expected return of 3.30%) ÷ the 15-year volatility.

| Asset | 15-year | Blended | Long history blended in |
|---|---:|---:|:---:|
| US LargeCap | 13.96% | 13.33% | yes |
| US SmallCap | 19.11% | 19.26% | no |
| Mexico Eq | 22.72% | 21.92% | no |
| Brazil Eq | 31.90% | 31.08% | no |
| China Eq | 22.61% | 22.76% | no |
| Japan Eq | 13.82% | 16.45% | yes |
| UK Eq | 15.34% | 16.09% | yes |
| France Eq | 17.88% | 17.31% | yes |
| EM Eq | 17.28% | 18.71% | yes |
| DM exUS Eq | 14.51% | 15.38% | yes |
| US Cash TBill | 0.55% | 3.39% | yes |
| US Treas Interm | 6.20% | 7.52% | yes |
| US Treas Long | 13.00% | 15.14% | yes |
| US TIPS | 5.01% | 6.00% | no |
| US IG Corp | 7.49% | 7.93% | yes |
| US HighYield | 7.30% | 7.71% | no |
| EM USD Sov | 9.38% | 9.70% | no |
| EM Local Debt | 10.97% | 10.88% | no |
| Global Agg exUS | 4.04% | 5.37% | no |
| Mexico Govt Local | 15.10% | 14.76% | no |
| US REITs | 17.02% | 16.91% | no |
| Global REITs exUS | 16.19% | 15.52% | no |
| Commodities | 17.04% | 17.02% | no |
| Gold | 16.13% | 18.80% | yes |

## Correlation: two matrices

- **`correlation_ledoit_wolf.csv`**: the correlation implied by a Ledoit-Wolf-shrunk covariance
  of monthly returns over the window in which all 24 assets have data. Shrinkage
  pulls noisy pairwise estimates toward a structured target and keeps the matrix
  well-conditioned.
- **`correlation_sample_15y.csv`**: the plain sample correlation of the same 15 years of monthly
  log returns used for the 15-year volatility.

Both are published to two decimals.
