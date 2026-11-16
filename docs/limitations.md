# Limitations and non-claims

## What is not implemented or qualified

- No real-market data, data ingestion, account, API, broker adapter, paper/live order route, deployment, or trading service.
- No market-performance or profitability claim. The results are correctness evidence from artificial data.
- No native split/dividend lifecycle qualification, partial fills, queue position, liquidity, or market impact model.
- No native insufficient-cash order lifecycle qualification.
- No cross-operating-system or multi-version Python qualification. The audited target was CPython 3.14.0 on macOS 26.5.2 arm64.
- No unseen M2 holdout remains; both holdouts were consumed during the final audit.
- No public source, QA oracle, fixture, raw report, package lock, or complete reproduction bundle is included. The public reader cannot independently reproduce the reported checks.

## Interpretation

The strategy is a fixed long-or-cash 20/50 moving-average example over authored synthetic daily bars. Next-listed-session-open fills, integer share quantities, zero interest/tax and simplified one-way adverse costs are engineering conventions. They do not model the full market, actual execution, or a user's investment decisions.

Gate 0 remains open. A future engineering milestone, real-data path, framework change, or trading-related capability requires separate authorization and independent acceptance criteria. The existence of this portfolio does not approve M3.

## Licensing limitation

The private engine pins and imports `backtesting.py==0.6.6` in-process. Its exact upstream [license](https://github.com/kernc/backtesting.py/blob/0.6.6/LICENSE.md) is GNU AGPLv3. Whether the integrated engine forms a covered combined work and what repository-wide license applies is unresolved and requires qualified legal review before a runnable source release. This documentation portfolio does not clear those questions for the engine.
