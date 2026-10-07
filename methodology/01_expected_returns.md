# 01 · Expected returns

*As of model built 2026-10-04. Horizon 12 years; annual, nominal, US-dollar terms; US inflation 2.4%.*

## Equities: building blocks

```
expected return(λ) = dividend yield + net buyback yield + real earnings growth
                     + inflation + λ × valuation reversion

valuation reversion = (fair valuation ÷ current valuation)^(1/12) − 1
```

Valuation reversion is the annual return that a full move of the valuation metric (CAPE or
trailing P/E) from today's level to its fair level over 12 years would add or subtract.
λ = 0 assumes no reversion and λ = 1 full reversion; the base case is λ = 0.5.

| Market | Dividend yield | Net buyback | Real growth | Inflation | Metric | Now | Fair | Full reversion / yr | λ = 0 | λ = 0.5 (base) | λ = 1 |
|---|---:|---:|---:|---:|---|---:|---:|---:|---:|---:|---:|
| US LargeCap | 1.20% | 1.70% | 2.50% | 2.40% | CAPE | 40.49 | 26.00 | −3.62% | 7.80% | 5.99% | 4.18% |
| US SmallCap | 1.30% | 0.50% | 2.50% | 2.40% | P/E | 19.00 | 18.00 | −0.45% | 6.70% | 6.48% | 6.25% |
| Mexico Eq | 3.20% | 0.00% | 1.80% | 2.40% | P/E | 13.00 | 15.00 | 1.20% | 7.40% | 8.00% | 8.60% |
| Brazil Eq | 4.50% | 0.00% | 2.00% | 2.40% | P/E | 11.80 | 11.50 | −0.21% | 8.90% | 8.79% | 8.69% |
| China Eq | 2.20% | 0.50% | 3.00% | 2.40% | CAPE | 17.70 | 15.00 | −1.37% | 8.10% | 7.42% | 6.73% |
| Japan Eq | 2.20% | 1.00% | 1.50% | 2.40% | CAPE | 29.40 | 25.00 | −1.34% | 7.10% | 6.43% | 5.76% |
| UK Eq | 3.80% | 0.50% | 1.30% | 2.40% | CAPE | 20.20 | 16.00 | −1.92% | 8.00% | 7.04% | 6.08% |
| France Eq | 3.00% | 0.50% | 1.50% | 2.40% | CAPE | 21.00 | 20.00 | −0.41% | 7.40% | 7.20% | 6.99% |
| EM Eq | 2.80% | 0.00% | 2.80% | 2.40% | CAPE | 16.00 | 16.00 | 0.00% | 8.00% | 8.00% | 8.00% |
| DM exUS Eq | 3.20% | 0.40% | 1.50% | 2.40% | CAPE | 18.00 | 19.00 | 0.45% | 7.50% | 7.73% | 7.95% |

The largest valuation bet is **US LargeCap**: full reversion would move its expected return by
−3.62% a year, so its λ = 0 and λ = 1 returns are
3.62 percentage points
apart. Its CAPE of 40.49 (quarter-end 2026-06-30, from the public Shiller data) sits against a fair level of 26.00.

## Fixed income and real assets

These start from a yield or income anchor rather than the building-block sum. The basis shown
is the note published with each number.

| Asset | Class | Expected return | Basis (as published) |
|---|---|---:|---|
| US Cash TBill | Fixed Income | 3.30% | avg(3.7% spot, ~3.0% equilibrium cash rate) |
| US Treas Interm | Fixed Income | 4.50% | YTM ~4.5% (7-10y), slight normalization gain |
| US Treas Long | Fixed Income | 4.80% | YTM ~4.9% (20y+), duration/normalization |
| US TIPS | Fixed Income | 4.50% | 10y real yield 2.1% + US inflation 2.4% |
| US IG Corp | Fixed Income | 5.00% | YTM ~5.3% - ~0.2% loss - tight-spread drag |
| US HighYield | Fixed Income | 5.00% | YTM ~7.5% - ~2.3% credit loss - tight-OAS drag |
| EM USD Sov | Fixed Income | 6.00% | EMBI YTM ~7.0% - ~0.9% sovereign loss |
| EM Local Debt | Fixed Income | 4.80% | local yield ~6.3% - ~1.5% EM FX depreciation |
| Global Agg exUS | Fixed Income | 3.80% | BNDX USD-hedged: hedged yield ~3.8% |
| Mexico Govt Local | Fixed Income | 6.30% | Mbono 10y 8.88% - ~2.5% MXN depreciation vs USD |
| US REITs | Real Asset | 6.30% | income ~3.8% + real growth ~2% + inflation |
| Global REITs exUS | Real Asset | 6.40% | income ~4.2% + growth ~1.5% + inflation |
| Commodities | Real Asset | 3.50% | collateral ~3.3% + ~0% real spot + roll |
| Gold | Real Asset | 3.30% | inflation 2.4% + ~1% long-run real return |
