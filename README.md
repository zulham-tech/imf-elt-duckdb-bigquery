# IMF World Economic Outlook ELT Pipeline | S3 Â· DuckDB Â· BigQuery

> **Type:** Batch ELT | **Stack:** IMF API â†’ S3 (raw) â†’ DuckDB â†’ BigQuery â†’ Airflow

## Key Metrics
- **50,000 records/run** (8 indicators Ã— 190+ countries Ã— 25 years)
- **DuckDB reads S3 Parquet directly** via httpfs â€” no data movement
- **Raw data preserved** in S3 â€” full reprocessing anytime
- **Idempotent:** DELETE + INSERT by batch_date

## ELT vs ETL
| | ETL | ELT (this project) |
|---|---|---|
| Transform where | Before loading (Spark) | After loading (DuckDB/SQL) |
| Infrastructure | Spark cluster needed | DuckDB â€” any laptop |
| Raw data retained | âŒ | âœ… S3 Parquet |

## Tech Stack
Python Â· Amazon S3 Â· DuckDB Â· Google BigQuery Â· Apache Airflow Â· Pandas Â· PyArrow

## Author
**Ahmad Zulham Hamdan** | [LinkedIn](https://linkedin.com/in/ahmad-zulham-hamdan-665170279) | [GitHub](https://github.com/zulham-tech)
