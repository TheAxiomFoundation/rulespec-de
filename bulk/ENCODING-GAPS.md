# Encoding gaps — rulespec-de

Values that differ between the bound 2026-consolidation corpus release
(`de-rulespec-2026-07-16`) and the 2025 validation snapshot, or that the cited
statutory text does not carry because a delegated Rechtsverordnung /
administrative announcement (not in this release) sets the operative figure.

Per the lane's 2025-vs-2026 discipline, each module encodes **exactly what the
cited text states with the effective dating the text states**. The rows below
record the operative/2025 values that are **awaiting a BGBl amending-instrument
or annual-Verordnung capture** in a later corpus release; they are NOT encoded.

> Location note: this ledger lives in `bulk/` (not `docs/`) because the
> repository layout gate (`tests/test_repository_layout.py`,
> `.axiom/repository-structure.yaml`) does not permit a root `docs/` directory.

| Instrument | Parameter | Encoded (2026-consolidation text) | Operative/2025 value awaiting capture | Governing instrument not in release |
|---|---|---|---|---|
| Pflegeversicherung | base Beitragssatz (SGB XI §55(1)) | 3,4 % (statutory, `durch Gesetz festgesetzt`) | 3,6 % operative from 2025-01-01 | Rechtsverordnung under §55(1a) (Pflege­beitragssatz-Anpassung) |
| Rentenversicherung | Beitragssatz (SGB VI) | 18,6 % — §287 statutory floor `bis zum Jahr 2025` | 18,6 % operative rate as *set* value (equals the floor for 2025) | Beitragssatzverordnung under §160 SGB VI |
| Krankenversicherung | durchschnittlicher Zusatzbeitragssatz (SGB V §242a) | not encoded — §242a states only the computation mechanism, no value | 2,5 % (2025, BMG announcement) | BMG Bekanntmachung under §242a(2) (Bundesanzeiger) |
| Solidaritätszuschlag | Freigrenze (SolzG §3(3)) | €20.350 single / €40.700 splitting (current text) | €19.950 / €39.900 (2025) | BGBl amending act (2025 Freigrenze) — instrument 2 |
| Einkommensteuer | §32a tariff constants | 2026 zone constants; Grundfreibetrag €12.348 (`ab dem Veranlagungszeitraum 2026`) | 2025 constants; Grundfreibetrag €12.096 | BGBl amending act (2025 §32a) — instrument 4 |
| Kindergeld | monthly amount (EStG §66(1)) | €259 (current text) | €255 (2025) | BGBl amending act (2025 Kindergeld) — instrument 5 |
| Minijob | Geringfügigkeitsgrenze (SGB IV §8(1a)) | formula only (Mindestlohn × 130 / 3, aufgerundet) | €556/month (2025 announced value) | BMAS Bekanntmachung (Bundesanzeiger); Mindestlohn not captured — instrument 3 |
