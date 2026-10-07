# 00 · Overview

*As of model built 2026-10-04.*

The model gives each of 24 assets (10 equity markets, 10 fixed-income
sectors, 4 real assets) three numbers:

1. an **expected annual return** over a 12-year horizon, nominal and in US-dollar terms, with
   US inflation at 2.4% a year ([01 · Expected returns](01_expected_returns.md));
2. a **volatility**, as two published estimates ([02 · Risk model](02_risk_model.md));
3. its **correlation** with every other asset, as two published matrices
   ([02 · Risk model](02_risk_model.md)).

## The valuation dial

Equity returns depend on how far today's valuations move back to fair value over the horizon.
The model publishes three settings of the dial λ: 0 (valuations stay where they are), 0.5 (the
base case) and 1 (full reversion). Fixed income and real assets do not use the dial; their
expected return is the same under all three settings.

## Checks applied on every sync

Before mirroring the published numbers, the sync re-derives them and stops if any check fails:

- each equity return equals the sum of its building blocks at λ = 0, 0.5 and 1;
- each valuation-reversion term equals (fair ÷ current valuation)^(1/12) − 1;
- every non-equity return is the same under all three dial settings;
- the summary table, the volatility file and the Sharpe ratios agree with each other;
- both correlation matrices are symmetric, with a unit diagonal and no entry above 1 in size.

Figures are published to two decimals.
