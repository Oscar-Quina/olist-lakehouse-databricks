# Design decisions

| # | Date | Decision | Alternative considered | Why |
|---|------|----------|------------------------|-----|
| 1 | 2026-11-15 | Dedicated `olist` catalog | Default `workspace` catalog | To avoid name collisions with other projects, allow single-command cleanup (`DROP CATALOG ... CASCADE`), and isolate project permissions |
| 2 | 2026-11-15 | Table naming: English `snake_case`, no `olist_` prefix, `fact_`/`dim_` in gold | Original CSV file names | To improve readability, simplify querying, and prevent name collisions |
| 3 | 2026-11-16 | Raw CSV volume inside `bronze` (`olist.bronze.raw_data`) | Separate `raw` or landing schema | To keep a clean 3-layer Medallion architecture since `bronze` already represents raw data as it arrives, and to co-locate source files with their target tables for clear lineage (Trade-off: in production, a separate landing zone enables stricter permissions and independent retention policies) |
| 4 | 2026-11-15 | One branch per ticket + squash and merge | Commits straight to `main` | To protect the `main` branch stability and maintain a clean Git history |
| 5 | 2026-11-16 | Create `raw_data` volume inside `00_setup` | Separate setup notebook for volumes | To ensure a single idempotent notebook provisions all required project containers (catalog, schemas, and volumes) |
| 6 | 2026-11-16 | Manual CSV upload to volume (excluded from GitHub via `.gitignore`) | Committing raw CSV datasets to the repository | To prevent bloating the Git repository with large static files while keeping raw ingestion isolated in Databricks (reproducibility for external users will be addressed with sample data in P1-17) |