# 02 · Risk model

*As of model built 2026-11-01.*

## Volatility: two estimates

| Estimate | How it is built | Column |
|---|---|---|
| 15-year | Standard deviation of the last 15 years of monthly log returns, annualised (× √12). | `volatility_15y_pct` |
| Blended | Volatility from a Ledoit-Wolf-shrunk covariance of monthly returns, blended 50/50 in variance with a long-history volatility for the 11 assets that have one; the other 13 use the shrunk estimate alone. | `volatility_blended_pct` |

The base-case Sharpe ratio in `capital_market_assumptions.csv` is (base-case expected return −
the cash expected return of 3.30%) ÷ the 15-year volatility.

| Asset | 15-year | Blended | Long history blended in |
|---|---:|---:|:---:|
| US LargeCap | 13.97% | 13.34% | yes |
| US SmallCap | 19.10% | 19.24% | no |
| Mexico Eq | 22.71% | 21.90% | no |
| Brazil Eq | 31.96% | 31.13% | no |
| China Eq | 22.66% | 22.82% | no |
| Japan Eq | 13.86% | 16.46% | yes |
| UK Eq | 15.35% | 16.10% | yes |
| France Eq | 17.86% | 17.30% | yes |
| EM Eq | 17.39% | 18.75% | yes |
| DM exUS Eq | 14.51% | 15.38% | yes |
| US Cash TBill | 0.56% | 3.40% | yes |
| US Treas Interm | 6.24% | 7.54% | yes |
| US Treas Long | 13.06% | 15.17% | yes |
| US TIPS | 5.04% | 6.02% | no |
| US IG Corp | 7.51% | 7.94% | yes |
| US HighYield | 7.30% | 7.71% | no |
| EM USD Sov | 9.39% | 9.71% | no |
| EM Local Debt | 10.97% | 10.88% | no |
| Global Agg exUS | 4.05% | 5.37% | no |
| Mexico Govt Local | 15.10% | 14.76% | no |
| US REITs | 17.05% | 16.95% | no |
| Global REITs exUS | 16.19% | 15.52% | no |
| Commodities | 17.03% | 17.02% | no |
| Gold | 16.24% | 18.85% | yes |

## Correlation: two matrices

- **`correlation_ledoit_wolf.csv`**: the correlation implied by a Ledoit-Wolf-shrunk covariance
  of monthly returns over the window in which all 24 assets have data. Shrinkage
  pulls noisy pairwise estimates toward a structured target and keeps the matrix
  well-conditioned.
- **`correlation_sample_15y.csv`**: the plain sample correlation of the same 15 years of monthly
  log returns used for the 15-year volatility.

Both are published to two decimals.
