# rulespec-de — agent notes

Germany federal tax-benefit encodings, dual-validated against EUROMOD (DE_2025)
and GETTSIM (policy_date 2025-06-30). Read the org regime first:
`gh issue view 39 --repo TheAxiomFoundation/.github`.

## Rules that bite

- **Canonical-provenance regime** (.github#39): never touch
  `.axiom/toolchain.toml`, workflow pins, or CODEOWNERS in a feature PR;
  content changes carry supervised-encoder apply manifests; proof excerpts are
  verbatim substrings of the resolved provision text; numeric literals ground
  per-anchored-atom; waivers are decrement-only.
- **Citations**: encode only against provisions in the bound immutable release
  (`de/statute/<gesetz-slug>/…` paths from the gesetze-im-internet juris-XML
  converter). New citations → batch a corpus ingest + release re-cut; record
  interim gaps in `data/coverage/awaiting-source-recovery.json`.
- **Dual-oracle discipline**: encode the statute, never an oracle's behavior.
  Oracle-vs-oracle disagreements are findings against the losing model
  (ledger + upstream issue), adjudicated by the print.
- **German text**: statute bodies are German; keep proof excerpts in the
  original German (verbatim), with English notes only outside excerpt fields.
  Umlauts/ß are preserved exactly — never transliterate inside excerpts.
- **Amounts change annually** (Grundfreibetrag, Regelbedarfe, ceilings,
  Kindergeld): every amount is effective-dated to its amending act or the
  annual Verordnung; the 2025 validation snapshot is 30 June 2025.

## Oracles

- EUROMOD: `~/Downloads/EUROMOD_J2.0/EUROMOD_RELEASES_J2.0+`, run via
  axiom-oracles `EuromodPlatformRunner`, dataset `DE_2024_b1_2015_03_e2` +
  `template_dataset DE_training_data` (readiness matrix entry DE). Take-up
  randomness: pin take-up constants via `euromod_constant_overrides`.
- GETTSIM: `uv pip install gettsim` (1.2.1 verified); inputs discovered via
  `MainTarget.templates.input_data_dtypes.tree`, nested mapper, add-until-clean.
  Verified 2025 employee SSC legs match statute exactly.
