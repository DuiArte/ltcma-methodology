# 02 · Risk model

*As of model built 2026-11-18.*

## Volatility: two estimates

| Estimate | How it is built | Column |
|---|---|---|
| 15-year | Standard deviation of the last 15 years of monthly log returns, annualised (× √12). | `volatility_15y_pct` |
| Blended | Volatility from a Ledoit-Wolf-shrunk covariance of monthly returns, blended 50/50 in variance with a long-history volatility for the 11 assets that have one; the other 13 use the shrunk estimate alone. | `volatility_blended_pct` |

The base-case Sharpe ratio in `capital_market_assumptions.csv` is (base-case expected return −
the cash expected return of 3.30%) ÷ the 15-year volatility.

| Asset | 15-year | Blended | Long history blended in |
|---|---:|---:|:---:|
| US LargeCap | 13.81% | 13.34% | yes |
| US SmallCap | 18.83% | 19.22% | no |
| Mexico Eq | 22.50% | 21.84% | no |
| Brazil Eq | 31.67% | 31.09% | no |
| China Eq | 22.36% | 22.76% | no |
| Japan Eq | 13.93% | 16.47% | yes |
| UK Eq | 15.09% | 16.09% | yes |
| France Eq | 17.62% | 17.28% | yes |
| EM Eq | 17.02% | 18.75% | yes |
| DM exUS Eq | 14.38% | 15.38% | yes |
| US Cash TBill | 0.55% | 3.39% | yes |
| US Treas Interm | 6.24% | 7.54% | yes |
| US Treas Long | 13.03% | 15.16% | yes |
| US TIPS | 5.03% | 6.02% | no |
| US IG Corp | 7.49% | 7.93% | yes |
| US HighYield | 7.02% | 7.69% | no |
| EM USD Sov | 9.32% | 9.69% | no |
| EM Local Debt | 10.88% | 10.85% | no |
| Global Agg exUS | 4.03% | 5.35% | no |
| Mexico Govt Local | 15.09% | 14.73% | no |
| US REITs | 16.73% | 16.90% | no |
| Global REITs exUS | 15.98% | 15.47% | no |
| Commodities | 17.27% | 17.29% | no |
| Gold | 16.19% | 18.83% | yes |

## Correlation: two matrices

- **`correlation_ledoit_wolf.csv`**: the correlation implied by a Ledoit-Wolf-shrunk covariance
  of monthly returns over the window in which all 24 assets have data. Shrinkage
  pulls noisy pairwise estimates toward a structured target and keeps the matrix
  well-conditioned.
- **`correlation_sample_15y.csv`**: the plain sample correlation of the same 15 years of monthly
  log returns used for the 15-year volatility.

Both are published to two decimals.
