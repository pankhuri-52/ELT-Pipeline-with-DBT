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
data_pipeline - contains the code for DBT transformation on the TPCH sample data by snowflake and data quality checks
astro_projects - contains the code for DBT-DAG and how to orchestrate through airflow.

## STEPS THAT YOU NEED TO FOLLOW

📦 Step 1: Set Up DBT with Snowflake
Install the required DBT packages:
pip install --user dbt-core dbt-snowflake
Initialize a new DBT project:
dbt init

Follow the prompts:
Enter your project name
Choose Snowflake as the adapter
Provide your Snowflake account details:
Account Locator (from Snowflake UI)
Warehouse
Database
Schema
Role
Username and Password or Key Pair

⚙️ Step 2: Configure dbt_project.yml and packages.yml
You can check the code and make changes accordingly

🗃️ Step 3: Create Source and Staging Tables
You will find the code in
data_pipeline -> models -> staging and marts folder.
Please copy paste from there.

📊 Step 4: Create Transformed Models (Fact Tables)
Created one fact table under marts folder fct_orders.sql
Similarly, you can create many

🔁 Step 5: Create Reusable Macros
Refer to the pricing.sql file under data_pipeline->macros folder

🧪 Step 6: Add Generic & Singular Tests
Singular Tests - under tests folder
Generic Tests - yaml file under marts and staging folder
Run dbt test for running the tests

🌬️ Step 7: Orchestrate with Airflow
Use Astronomer CLI to set up local Airflow.
astro dev init
astro dev start
You will find the code for the DAG in the astro_projects-> dags-> dbt_dag.py file
Trigger and monitor jobs from the Airflow UI at http://localhost:8080

📺 Demo Video
Watch the full walkthrough of the ELT pipeline setup: https://www.loom.com/share/ef81eb0498da40fda7f685a05bdb0735?sid=3b34f1e8-ac8a-488e-8bd8-5bc0ccb3d498
 








