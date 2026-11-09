# 02 · Risk model

*As of model built 2026-11-08.*

## Volatility: two estimates

| Estimate | How it is built | Column |
|---|---|---|
| 15-year | Standard deviation of the last 15 years of monthly log returns, annualised (× √12). | `volatility_15y_pct` |
| Blended | Volatility from a Ledoit-Wolf-shrunk covariance of monthly returns, blended 50/50 in variance with a long-history volatility for the 11 assets that have one; the other 13 use the shrunk estimate alone. | `volatility_blended_pct` |

The base-case Sharpe ratio in `capital_market_assumptions.csv` is (base-case expected return −
the cash expected return of 3.30%) ÷ the 15-year volatility.

| Asset | 15-year | Blended | Long history blended in |
|---|---:|---:|:---:|
| US LargeCap | 13.81% | 13.33% | yes |
| US SmallCap | 18.80% | 19.20% | no |
| Mexico Eq | 22.51% | 21.84% | no |
| Brazil Eq | 31.62% | 31.04% | no |
| China Eq | 22.39% | 22.79% | no |
| Japan Eq | 13.94% | 16.47% | yes |
| UK Eq | 15.06% | 16.08% | yes |
| France Eq | 17.62% | 17.28% | yes |
| EM Eq | 17.00% | 18.74% | yes |
| DM exUS Eq | 14.35% | 15.37% | yes |
| US Cash TBill | 0.56% | 3.39% | yes |
| US Treas Interm | 6.23% | 7.53% | yes |
| US Treas Long | 13.02% | 15.15% | yes |
| US TIPS | 5.02% | 6.01% | no |
| US IG Corp | 7.49% | 7.93% | yes |
| US HighYield | 7.02% | 7.69% | no |
| EM USD Sov | 9.31% | 9.68% | no |
| EM Local Debt | 10.87% | 10.85% | no |
| Global Agg exUS | 4.03% | 5.36% | no |
| Mexico Govt Local | 15.12% | 14.71% | no |
| US REITs | 16.74% | 16.90% | no |
| Global REITs exUS | 15.98% | 15.48% | no |
| Commodities | 17.02% | 17.06% | no |
| Gold | 16.22% | 18.84% | yes |

## Correlation: two matrices

- **`correlation_ledoit_wolf.csv`**: the correlation implied by a Ledoit-Wolf-shrunk covariance
  of monthly returns over the window in which all 24 assets have data. Shrinkage
  pulls noisy pairwise estimates toward a structured target and keeps the matrix
  well-conditioned.
- **`correlation_sample_15y.csv`**: the plain sample correlation of the same 15 years of monthly
  log returns used for the 15-year volatility.

Both are published to two decimals.
