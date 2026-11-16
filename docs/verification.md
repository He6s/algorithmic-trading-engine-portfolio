# Verification summary

**Evidence labels:** “Verified” below means the statement is recorded in the project's independently reviewed M1/M2 reports. Those reports and raw packets are not included in this portfolio. Readers cannot inspect the underlying artifacts or rerun the checks from this repository.

## M1 — fixed synthetic demonstration

**Verified:** the Issue #28 final audit recorded a scoped technical PASS for one frozen synthetic daily-bar path. It checked causal signal visibility and next-open fills, an external Decimal ledger, no-trade and buy-and-hold controls, named input-boundary cases, and offline execution evidence. The audited run had 12 cases, 50 marked sessions per case, and 600 native position/equity checkpoints.

**Limit:** this was one authored fixture, not a general framework qualification. The top-level capture wrapper's exit code was unrecorded; QA accepted the two complete evaluation-child process records under the frozen contract. Some malformed-input branches were source-inspected only. Native corporate-action and native partial-fill/liquidity handling were unsupported.

## M2 — bounded synthetic generalization

**Verified:** the Issue #45 independent final audit recorded a scoped technical PASS. Across five synthetic datasets it reported:

- 120 case/environment comparisons;
- 208 malformed-input controls;
- 9,864 raw native checkpoint reconciliations;
- 238 denied TCP-connect probes; and
- matching canonical outputs in two independently prepared fresh environments.

Both environments used CPython 3.14.0 on macOS 26.5.2 arm64. Cross-platform behavior remains untested. Both QA-sealed holdouts were consumed during the audit and are not available as unseen holdouts.

## Independent review and source references

The private source project records M1 final QA in `docs/m1/QA_FINAL.md` and M2 final QA in `docs/m2/QA_FINAL.md`. The historical project identities are M1 integrated audit base `31b5f6eff37b6a22e2c01ecf7a4747ae60f3f327` and M2 audited base `f090fe54638ad400046b5341d2c3aecd8fac7425`. M2 implementation/evidence was accepted through project PRs #49 and #50; M1 final audit is recorded in PR #41. These references are provided for provenance only; access may require permission to the private project.

## What this evidence does not show

It does not show real-market-data correctness, profitability, a trading edge, broad engine correctness, production readiness, live/paper safety, data rights, or cross-OS behavior. See [limitations](limitations.md).
