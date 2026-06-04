# 01 · Assumptions

The capital-market assumptions are three inputs per asset class:

- **Expected return** — a long-horizon (10-year) annualized estimate, built bottom-up
  from a yield/carry component plus a valuation-reversion component plus expected
  growth. The published values are in
  [`../assumptions/capital_market_assumptions.csv`](../assumptions/capital_market_assumptions.csv).
- **Volatility** — annualized standard deviation, estimated from long-run realized
  history with a shrinkage adjustment toward the cross-asset average.
- **Correlation** — pairwise long-run correlations, also shrunk to avoid
  over-fitting recent regimes.

## What is published vs withheld

| Published | Withheld |
|---|---|
| the final return / vol / corr numbers | the workbook that derives them |
| the *components* named in prose (carry, valuation, growth) | the exact weights on each component |
| the asset-class taxonomy | any account-specific tilt |

The derivation is the edge; the output table is the demonstration. Publishing the
table lets a reader sanity-check the conclusions without handing over the recipe.

> Placeholder draft.
