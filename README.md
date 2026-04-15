# IMF World Economic Outlook ELT Pipeline | DuckDB, BigQuery

**Stack:** IMF API -> S3 raw zone -> DuckDB -> BigQuery -> Airflow

## Key Metrics
- 50,000 records/run (8 indicators x 190+ countries x 25 years)
- DuckDB reads S3 Parquet directly via httpfs, no data movement needed
- Raw data always preserved in S3, full reprocessing anytime
- Idempotent: DELETE + INSERT by batch_date

## ELT vs ETL
| | ETL | ELT (this project) |
|---|---|---|
| Transform where | Before loading via Spark | After loading via DuckDB SQL |
| Infrastructure | Spark cluster needed | DuckDB runs on any laptop |
| Raw data retained | No | Yes, S3 Parquet |

## Tech Stack
Python, Amazon S3, DuckDB, Google BigQuery, Apache Airflow, Pandas, PyArrow

## Author
Ahmad Zulham Hamdan | https://linkedin.com/in/ahmad-zulham-hamdan-665170279