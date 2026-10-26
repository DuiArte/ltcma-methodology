# 02 · Risk model

*As of model built 2026-10-25.*

## Volatility: two estimates

| Estimate | How it is built | Column |
|---|---|---|
| 15-year | Standard deviation of the last 15 years of monthly log returns, annualised (× √12). | `volatility_15y_pct` |
| Blended | Volatility from a Ledoit-Wolf-shrunk covariance of monthly returns, blended 50/50 in variance with a long-history volatility for the 11 assets that have one; the other 13 use the shrunk estimate alone. | `volatility_blended_pct` |

The base-case Sharpe ratio in `capital_market_assumptions.csv` is (base-case expected return −
the cash expected return of 3.30%) ÷ the 15-year volatility.

| Asset | 15-year | Blended | Long history blended in |
|---|---:|---:|:---:|
| US LargeCap | 13.97% | 13.33% | yes |
| US SmallCap | 19.10% | 19.25% | no |
| Mexico Eq | 22.72% | 21.92% | no |
| Brazil Eq | 31.94% | 31.13% | no |
| China Eq | 22.66% | 22.82% | no |
| Japan Eq | 13.83% | 16.46% | yes |
| UK Eq | 15.34% | 16.09% | yes |
| France Eq | 17.88% | 17.31% | yes |
| EM Eq | 17.34% | 18.74% | yes |
| DM exUS Eq | 14.51% | 15.39% | yes |
| US Cash TBill | 0.55% | 3.40% | yes |
| US Treas Interm | 6.22% | 7.53% | yes |
| US Treas Long | 13.04% | 15.16% | yes |
| US TIPS | 5.03% | 6.02% | no |
| US IG Corp | 7.50% | 7.94% | yes |
| US HighYield | 7.30% | 7.71% | no |
| EM USD Sov | 9.38% | 9.71% | no |
| EM Local Debt | 10.97% | 10.88% | no |
| Global Agg exUS | 4.04% | 5.37% | no |
| Mexico Govt Local | 15.10% | 14.76% | no |
| US REITs | 17.03% | 16.93% | no |
| Global REITs exUS | 16.19% | 15.52% | no |
| Commodities | 17.06% | 17.05% | no |
| Gold | 16.17% | 18.81% | yes |

## Correlation: two matrices

- **`correlation_ledoit_wolf.csv`**: the correlation implied by a Ledoit-Wolf-shrunk covariance
  of monthly returns over the window in which all 24 assets have data. Shrinkage
  pulls noisy pairwise estimates toward a structured target and keeps the matrix
  well-conditioned.
- **`correlation_sample_15y.csv`**: the plain sample correlation of the same 15 years of monthly
  log returns used for the 15-year volatility.

Both are published to two decimals.
