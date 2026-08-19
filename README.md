# Portfolio

A collection of personal projects I build to learn, experiment, and practice software
and data engineering end-to-end — from small proofs of concept to more complete, deliberately
concrete reference implementations.

Each project lives in its own repository and is included here as a Git submodule, so this
repo acts as a single entry point to browse everything in one place.

## Projects

| Project | Description | Stack |
|---|---|---|
| [Batch-Ingestion-Pipeline](https://github.com/dandobjim/Batch-Ingestion-Pipeline) | A batch ELT pipeline that pulls issues from the GitHub REST API, validates them against a strict schema, lands them in a partitioned raw Parquet layer, loads them into Postgres, and transforms them with dbt into a clean, typed staging layer — all orchestrated end-to-end by Apache Airflow and reproducible with a single `docker compose up`. | Python, Airflow, dbt, PostgreSQL, DuckDB, Docker |

## Cloning with submodules

```bash
git clone --recurse-submodules git@github.com:dandobjim/Portfolio.git
```

If you've already cloned the repo without that flag:

```bash
git submodule update --init --recursive
```

## Contact

- GitHub: [@dandobjim](https://github.com/dandobjim)