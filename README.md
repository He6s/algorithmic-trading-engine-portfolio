# Algorithmic Trading Engine — engineering portfolio

This portfolio summarizes the completed M1 and M2 engineering demonstrators for an algorithmic trading system. It focuses on causal event handling, accounting invariants, input validation, reproducibility, independent review, and known limits.

**This is a documentation portfolio.** It does not include the runnable engine, test code, test fixtures, QA oracle, dependency lock, raw process records, or raw evidence packets. The source and detailed evidence remain in a separate private project repository. Nothing in this repository can reproduce or independently verify those runs.

## What was built

- A fixed synthetic daily-bar example using a 20/50 simple moving-average rule, with no-trade and buy-and-hold controls.
- Decisions based on completed bars and fills at the next listed session's open.
- Framework event capture paired with a separate Decimal cash/share/fee ledger.
- Fail-closed input/provenance checks, canonical reports, hashes, offline execution controls, and independent audits.

M1 qualified one frozen synthetic input. M2 applied the frozen evaluation contract to five synthetic datasets and checked reproducibility across two fresh local environments. Both milestones received scoped independent QA passes. The numeric outcomes below describe the size and scope of those engineering checks; they are not investment returns or evidence of a market edge.

## Architecture

See [architecture and event lifecycle](docs/architecture.md).

## Evidence at a glance

| Milestone | Independently reviewed engineering evidence | Boundary |
| --- | --- | --- |
| M1 | Scoped independent QA PASS for the frozen synthetic path; 12 cases, causal next-open timing, and ledger checks. | One authored fixture. Some schema branches were source-inspected, not separately executed. |
| M2 | 120 case/environment comparisons; 208 malformed-input controls; 9,864 raw native checkpoint reconciliations; 238 denied TCP probes; matching canonical results in two fresh environments. | Five synthetic datasets on one macOS arm64 platform. Two holdouts are spent. |

Full claim labels, source-report references, and limits are in [verification summary](docs/verification.md) and [limitations](docs/limitations.md).

## Reproducibility status

The recorded runs used CPython 3.14.0 and macOS 26.5.2 arm64 with `backtesting.py==0.6.6`. This repository does not contain the inputs, code, lock file, raw reports, or QA oracles needed to rerun or reproduce those results. Cross-platform behavior is untested. The evidence summaries are not a reproducibility package.

## Safety and scope

All M1/M2 inputs were synthetic and offline. No market prices, vendor data, account, API key, broker connection, paper/live order, deployment, or paid service was used. Gate 0 remains open. The demonstrator has no live-trading capability and makes no profitability, investment, or production-readiness claim.

## Licensing and source access

The engine integrates `backtesting.py==0.6.6`, whose exact upstream tag is licensed under GNU AGPL version 3 ([tagged license](https://github.com/kernc/backtesting.py/blob/0.6.6/LICENSE.md), observed 2026-11-16). The engine's combined-work and repository-wide licensing questions have not received qualified legal review. The runnable project is not included here or released by this portfolio. This portfolio contains no license file; no software reuse permission is granted by this repository.

## Contents

- [Architecture and event lifecycle](docs/architecture.md)
- [Verification summary](docs/verification.md)
- [Limitations and non-claims](docs/limitations.md)
- [Provenance and privacy review](docs/provenance.md)
