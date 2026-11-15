# Design decisions

| # | Date | Decision | Alternative considered | Why |
|---|------|----------|------------------------|-----|
| 1 | 2026-11-15 | Dedicated `olist` catalog | Default `workspace` catalog | to avoid collisions with other projects |
| 2 | 2026-11-15 | Table naming: English snake_case, no `olist_` prefix, `fact_`/`dim_` in gold | Original CSV file names | To improve readability, simplify querying, and prevent name collisions|
| 3 | 2026-11-15 | Raw CSV volume inside `bronze` | Separate `raw` schema | TBD (P1-02) |
| 4 | 2026-11-15 | One branch per ticket + squash and merge | Commits straight to `main` | To protect the main branch stability and maintain a clean git history|