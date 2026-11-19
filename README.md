# SQL Server Medallion Architecture Data Warehouse
A comprehensive data warehousing and analytics solution.

A data warehouse built from scratch in SQL Server that consolidates data from two
source systems, a CRM and an ERP, into a single, analytics-ready model using the
medallion architecture.

## Objective
Build an SQL-based analytics to deliver detailed insights into the following in order to empower stakeholders with key business metrics
- **Sales Trends
- **Consumer Patterns
- **Product Adoption /User Engagement 

## Architecture

- **Bronze layer:** Raw data ingested as-is from the CRM and ERP source files (CSV)
  using bulk loads, with no transformations, preserving full lineage.
- **Silver layer:** Cleansed and standardised data. Includes deduplication,
  null handling, data type corrections, value normalisation, and integration
  of the two source systems.
- **Gold layer:** Business-ready star schema (fact and dimension views) designed
  for reporting and analytics.

## Key Features

- Full ETL process written in T-SQL (stored procedures for each layer load)
- Adopts SCD Type 1; Focus is on latest dataset only, historization not required 
- Data quality checks and cleansing rules in the Silver layer
- Integration of overlapping CRM and ERP data (customers, products, sales)
- Dimensional modelling with surrogate keys and a star schema
- Documented data catalog, naming conventions, and data architecture diagrams

## Repository Structure

- `datasets/`: source CRM and ERP files
- `scripts/bronze/`, `scripts/silver/`, `scripts/gold/`: layer DDL and ETL scripts
- `tests/`: data quality checks
- `docs/`: architecture diagrams, data catalog, naming conventions
