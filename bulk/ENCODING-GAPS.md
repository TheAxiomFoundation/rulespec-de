# Encoding gaps — rulespec-de

Values that differ between the bound 2026-consolidation corpus release
(`de-rulespec-2026-07-16`) and the 2025 validation snapshot, or that the cited
statutory text does not carry because a delegated Rechtsverordnung /
administrative announcement / tabular annex (not in this release) supplies the
operative figure, or that a grounding-tool limitation blocks.

Per the lane's 2025-vs-2026 discipline, each module encodes **exactly what the
cited text states with the effective dating the text states**. The rows below
record values that are **awaiting a later corpus capture** or a tooling fix;
they are NOT encoded (except where noted the current-text value IS encoded and
only the 2025 counterpart is deferred).

> Location note: this ledger lives in `bulk/` (not `docs/`) because the
> repository layout gate (`tests/test_repository_layout.py`,
> `.axiom/repository-structure.yaml`) does not permit a root `docs/` directory.

## A. 2025-vs-2026 value splits (current text encoded; 2025 value deferred)

| Instrument | Parameter | Encoded (2026-consolidation text) | 2025 value awaiting capture | Source not in release |
|---|---|---|---|---|
| Solidaritätszuschlag | Freigrenze (SolzG §3(3)) | €20.350 / €40.700 | €19.950 / €39.900 | BGBl amending act (2025) |
| Einkommensteuer | §32a Grundfreibetrag | €12.348 (`ab VZ 2026`) | €12.096 | BGBl amending act (2025 §32a) |
| Kindergeld | monthly amount (EStG §66(1)) | €259 | €255 | BGBl amending act (2025) |
| Unterhaltsvorschuss | Mindestunterhalt (MinUhV §1) | both 2025 AND 2026 encoded (482/486, 554/558, 649/653) | — (text carries both, dated) | — |

## B. Operative figures set by delegated Verordnung / announcement (not encoded)

| Instrument | Parameter | Encoded instead | Operative value awaiting capture | Governing instrument |
|---|---|---|---|---|
| Pflegeversicherung | base Beitragssatz (SGB XI §55(1)) | 3,4 % statutory | 3,6 % operative from 2025-01-01 | Rechtsverordnung §55(1a) |
| Rentenversicherung | Beitragssatz (SGB VI) | 18,6 % §287 floor | 18,6 % as *set* value | Beitragssatzverordnung §160 |
| Krankenversicherung | durchschnittl. Zusatzbeitrag (SGB V §242a) | not encoded (mechanism only) | 2,5 % (2025) | BMG Bekanntmachung §242a(2) |
| Minijob | Geringfügigkeitsgrenze (SGB IV §8(1a)) | multiplier 130 | €556/month (2025) | BMAS Bekanntmachung; Mindestlohn not captured |
| Midijob | Übergangsbereich factor F (SGB IV §20(2a)) | 28 % numerator | annual F value | BMAS Bekanntmachung |
| Bürgergeld | Regelbedarfsstufen (SGB II §20, RBEG §8) | RBEG §8 2021 base (446 € RBS1 …) | €563 RBS1 (2025) | Regelbedarfsstufen-Fortschreibungsverordnung 2025 (RBSFV) |
| Kinderzuschlag | monthly Höchstbetrag (BKGG §6a(2)) | not encoded (Existenzminimum-coupled) | ≈ €297 (2025) | annual sächliches Existenzminimum / MinUhV linkage |

## C. Complex-formula / annex components deferred (encoded partial)

| Instrument | Encoded | Deferred component | Reason |
|---|---|---|---|
| Wohngeld | §19 factor 1,15 + 65 € 13th-member increment | a, b, c formula coefficients | live in Anlage 2 WoGG (tabular annex, not §19 body) |
| Einkommensteuer | §32a Grundfreibetrag + zone bounds | full progressive tariff (additive constants 1 400 / 2 397 / 1 034,87 / 11 135,63 / 19 470,38; marginal rates 0,42 / 0,45) | **tooling limitation, not a source gap** — the numeric-grounding extractor mis-parses German space-thousands separators and "•" bullet multiplication in formula context (`"1 400"` → `400`, `"0,42"` → `42`); the values are present verbatim but cannot pass `find_ungrounded_numeric_issues`. Candidate axiom-encode grounding fix. |
