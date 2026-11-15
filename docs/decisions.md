Date: Nov 15, 2026 (Sunday, one day before Week 1)
Ticket(s) worked on: P1-01, P1-04 (Part 1)
Completed tasks:
- P1-01 closed: Olist catalog + bronze/silver/gold schemas (00_setup, idempotent)
- SQL formatter configured (.dbsql-formatter-config.json, keywords in uppercase)
- Public repo created: Oscar-Quina/olist-lakehouse-databricks (README, Python .gitignore, MIT license)
- Git folder connected using a fine-grained PAT (1 repo, read/write access) + no-reply email
- PR #1 merged via squash: notebooks/00_setup
Pending tasks:
- P1-02: Justify the volume in the bronze layer with a specific rationale + define the volume name
- docs/decisions.md (dedicated catalog, naming convention, bronze layer volume)
- Download the Olist dataset from Kaggle
- P1-04 Part 2 (README skeleton + diagram)
Blockers: None (resolved: GitHub App permissions and GH007 error related to private email)
Assessment notes: Volumes 5/10 · Commit messages 20/30
Next step: P1-02 — upload the 8 CSV files to the volume and read them from a notebook

Decisions made:
- Nov 15: Dedicated Olist catalog (for isolation, single DROP operation, and catalog-level permissions)
- Nov 15: Tables in English using `snake_case`, without the `olist_` prefix; consistent naming across bronze and silver layers fact_/dim_ in the Gold layer
- Nov 15: CSV volume within the Bronze layer (justification pending)
- Nov 15: One branch per ticket, "squash and merge" strategy, commit messages in the format "P1-XX: <verb> <what>"

Progress table:
- Databricks: Started (catalog, schemas, Git folder)
- Project 1: 1 out of 18 tickets (P1-04 in progress)
- GitHub: Repository created