# rulespec-de

RuleSpec encodings of Germany's federal tax-benefit law — the first **dual-oracle**
lane: every encoded instrument is validated per-case against both
**EUROMOD** (the official EU tax-benefit model, systems DE_2007–DE_2025) and
**GETTSIM** (the German Taxes and Transfers SIMulator, date-parameterized,
pure Python). Where the two oracles disagree, the statute print adjudicates.

- **Validation year:** 2025 — rules in force 30 June 2025 (EUROMOD `DE_2025`
  snapshot; GETTSIM `policy_date 2025-06-30`).
- **Sources:** consolidated federal law as official juris XML from
  [gesetze-im-internet.de](https://www.gesetze-im-internet.de) (EStG, SolzG 1995,
  SGB III/IV/V/VI/XI, SGB II, BKGG, WoGG, BEEG, UhVorschG, and the annual
  Rechengrößen-/Regelbedarfs instruments), captured with full provenance in
  axiom-corpus.
- **Surface + oracle wiring:** `data/coverage/tax-benefit-source-map.json` and
  `data/oracles/oracle-index.json`.
- **Tracking issue:** [#1](https://github.com/TheAxiomFoundation/rulespec-de/issues/1).

## Provenance regime

This repository follows the canonical-provenance regime (org issue
TheAxiomFoundation/.github#39): it will bind exactly one immutable signed
corpus release in `.axiom/toolchain.toml` once the first German ingest wave is
cut, and all content arrives through the supervised encoder with signed apply
manifests. The bootstrap toolchain pins are interim scaffolding until that
release exists.

## Listing gates

`.axiom/registry.toml` keeps this repo `experimental` (hidden from the
axiom-foundation.org app surfaces) until: the release binding is live, the
first instruments pass both oracles or carry dispositioned findings, and the
findings ledger exists.
