<sub>**DuiArte** · quantitative research · [methodology](https://github.com/DuiArte/ltcma-methodology) · [strategies](https://github.com/DuiArte/static-drift-weight) · [framework](https://github.com/DuiArte/signallib-framework)</sub>

# LTCMA Methodology

**The published assumption set and allocation framework behind the LTCMA research site — the reasoning, in plain English.**

![status](https://img.shields.io/badge/status-stable-blue) ![license](https://img.shields.io/badge/license-CC--BY--NC--4.0-green) ![updated](https://img.shields.io/badge/updated-2026--06-lightgrey)

---

This repository documents *how* the long-term capital-market assumptions (LTCMA)
behind [duiarte.github.io/ltcma](https://duiarte.github.io/ltcma) are formed and
*how* they translate into an allocation. It publishes the framework and the
published assumption table — not the spreadsheet that derives them, and not any
live position.

## What's here

- **`methodology/`** — the framework in prose: assumptions, allocation logic,
  rebalancing rules.
- **`assumptions/capital_market_assumptions.csv`** — the published expected
  return / volatility / correlation table (the same numbers the public site shows).
- **`figures/`** — supporting charts.

## What's deliberately *not* here

The derivation spreadsheets, any account-scaled ("real numbers") figures, and any
tilt that maps to a live position. The methodology is published so it can be
learned from and cited; the operating specifics stay private. See
[`_MANIFEST.md`](_MANIFEST.md) for the full include/exclude list.

## License

[CC BY-NC 4.0](LICENSE) — share and adapt for non-commercial use, with attribution.

## Related

Part of the DuiArte quantitative-research family ·
[static-drift-weight](https://github.com/DuiArte/static-drift-weight) ·
[signallib-framework](https://github.com/DuiArte/signallib-framework) ·
[backtests-archive](https://github.com/DuiArte/backtests-archive)
