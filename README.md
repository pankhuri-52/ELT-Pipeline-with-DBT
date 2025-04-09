# 🧊 ELT Pipeline with DBT, Snowflake & Airflow

This repository contains a modern **ELT pipeline** setup using **DBT**, **Snowflake**, and **Airflow** to transform and load TPCH-style data. It includes DBT model definitions, data quality tests, and orchestration using Airflow.

---

## 🚀 Overview

This project follows a modular, scalable ELT architecture:

- **Extract & Load**: Data is loaded into Snowflake staging tables.
- **Transform**: DBT transforms raw data into dimensional models (`stg_`, `fct_`, `dim_`).
- **Test**: Data quality is enforced via DBT schema tests.
- **Orchestrate**: Apache Airflow schedules and monitors the pipeline runs.

---

## 🧱 Tech Stack

| Tool      | Purpose                              |
|-----------|--------------------------------------|
| **Snowflake** | Cloud data warehouse for storage and compute |
| **DBT**   | SQL-based transformation framework with testing |
| **Airflow** | Workflow orchestration and scheduling tool |

---

## 🗂️ Project Structure


