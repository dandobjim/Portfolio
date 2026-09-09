# Portfolio

A collection of personal projects I build to learn, experiment, and practice software
and data engineering end-to-end — from small proofs of concept to more complete, deliberately
concrete reference implementations.

Each project lives in its own repository and is included here as a Git submodule, so this
repo acts as a single entry point to browse everything in one place.

## Projects

| Project | Description | Stack |
|---|---|---|
| [de-toolbox](https://github.com/dandobjim/de-toolbox) | The baseline every other data engineering project here builds on: a reproducible local environment brought up with a single command — a Dockerised PostgreSQL seeded with a realistic dataset, a strict `uv`-managed Python skeleton with `ruff`, `mypy` and `sqlfluff` enforced on every commit, and analytical SQL exercises committed alongside their `EXPLAIN ANALYZE` plans. | Python, uv, PostgreSQL, Docker, SQL, pre-commit |
| [Batch-Ingestion-Pipeline](https://github.com/dandobjim/Batch-Ingestion-Pipeline) | A batch ELT pipeline that pulls issues from the GitHub REST API, validates them against a strict schema, lands them in a partitioned raw Parquet layer, loads them into Postgres, and transforms them with dbt into a clean, typed staging layer — all orchestrated end-to-end by Apache Airflow and reproducible with a single `docker compose up`. | Python, Airflow, dbt, PostgreSQL, DuckDB, Docker |

## Cloning with submodules

```bash
git clone --recurse-submodules git@github.com:dandobjim/Portfolio.git
```

If you've already cloned the repo without that flag:

```bash
git submodule update --init --recursive
```

## Updating the submodules

Submodules track the default branch (`HEAD`) of their upstream repository, so they can
always be fast-forwarded to the latest published commit:

```bash
# Pull this repo, then bring every submodule up to its upstream HEAD
git pull
git submodule update --init --recursive --remote --merge
```

To pull a single project instead of all of them:

```bash
git submodule update --remote --merge de-toolbox
```

After updating, the new submodule commits show up as changes in this repo. Commit them to
record which versions the portfolio points at:

```bash
git add de-toolbox Batch-Ingestion-Pipeline
git commit -m "chore: bump submodules to upstream HEAD"
```

Optionally, make Git recurse into submodules automatically on every `pull` and `checkout`:

```bash
git config --local submodule.recurse true
```

## Contact

- GitHub: [@dandobjim](https://github.com/dandobjim)
