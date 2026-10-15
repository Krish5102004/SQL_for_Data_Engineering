# 📊 SQL for Data Engineering & Analytical Modeling

![SQL](https://img.shields.io/badge/Language-SQL-blue?style=for-the-badge&logo=postgresql)
![DuckDB](https://img.shields.io/badge/Engine-DuckDB%20%7C%20MotherDuck-FFF000?style=for-the-badge&logo=duckdb&logoColor=black)
![Data Engineering](https://img.shields.io/badge/Focus-Data%20Engineering-orange?style=for-the-badge)

## 🚀 Overview
This repository contains an end-to-end Data Engineering portfolio utilizing **DuckDB** and **MotherDuck**. It demonstrates the complete lifecycle of analytical data engineering—from **Exploratory Data Analysis (EDA)** on tech job market datasets to building an automated **Data Warehouse (DW) & Analytical Data Marts** pipeline.

## 🛠️ Tech Stack & Tools
* **Databases & OLAP Engines:** DuckDB, MotherDuck (Cloud OLAP), SQL
* **Development Environment:** VS Code, Git/GitHub, PowerShell CLI
* **Core Competencies:** Dimensional Data Modeling (Star Schema & Data Marts), ELT Pipeline Orchestration, Idempotent DDL/DML Scripting, Analytical Querying

## 🧠 Key SQL Engineering Concepts Demonstrated
* **Data Warehouse & Mart Architecture:** Designing core fact/dimension schemas and building specialized analytical marts (`flat_mart`, `skills_mart`, `priority_mart`, `company_mart`).
* **Pipeline Automation:** Executing multi-step SQL build scripts (`build_marts.sql`) for automated table creation, schema ingestion, and incremental updates.
* **Advanced Querying & Aggregations:** Modular Common Table Expressions (CTEs), complex joins across bridge tables, and multi-dimensional aggregations.
* **Data Cleaning & DML Operations:** Handling `NULL` values, type casting, deduplication, and performing targeted `UPDATE` / `MERGE` operations on priority tables.

## 📂 Repository Structure
```text
📦 SQL_for_Data_Engineering
 ┣ 📂 Project/
 ┃ ┣ 📂 1_EDA_Project/                  # Exploratory Data Analysis on Tech Job Postings
 ┃ ┃ ┣ 📂 resources/                    # Supporting assets & query outputs
 ┃ ┃ ┣ 📜 1_top_demanded_skills.sql     # Identifies highest-demand skills across roles
 ┃ ┃ ┣ 📜 2_top_paying_skills.sql       # Analyzes salary benchmarks by technical skill
 ┃ ┃ ┣ 📜 3_optimal_skills.sql          # Combines demand & compensation to find optimal skills
 ┃ ┃ ┗ 📜 Readme.md                     # Detailed EDA documentation & insights
 ┃ ┣ 📂 2_DW_Mart_Build/                # End-to-End Data Warehouse & Mart Pipeline
 ┃ ┃ ┣ 📂 resources/                    # Architecture diagrams & data warehouse assets
 ┃ ┃ ┣ 📜 01_create_tables_dw.sql       # DDL scripts for core warehouse fact & dimension tables
 ┃ ┃ ┣ 📜 02_load_schema_dw.sql         # Data ingestion from raw sources into warehouse schema
 ┃ ┃ ┣ 📜 03_create_flat_mart.sql       # Denormalized wide table (OBT) for fast BI reporting
 ┃ ┃ ┣ 📜 04_create_skills_mart.sql     # Specialized mart for skill-level demand & trend analysis
 ┃ ┃ ┣ 📜 05_create_priority_mart.sql   # Mart targeting high-priority roles and benchmarks
 ┃ ┃ ┣ 📜 06_update_priority_mart.sql   # DML script for incremental updates to priority mart
 ┃ ┃ ┣ 📜 07_create_company_mart.sql    # Company-level hiring metrics and aggregations
 ┃ ┃ ┣ 📜 build_marts.sql               # Master orchestration script to build the entire DW pipeline
 ┃ ┃ ┗ 📜 README.md                     # Data Warehouse architecture & pipeline documentation
 ┃ ┗ 📜 README.md                       # Project overview
 ┣ 📜 .gitignore
 ┗ 📜 README.md
```
## 📈 Featured Modules
### 1️⃣ Exploratory Data Analysis (1_EDA_Project)
* **Objective:** Analyze thousands of real-world Data Engineering job postings to uncover actionable career and market insights.

* **Key Deliverables:**

   * **1_top_demanded_skills.sql:** Aggregates job postings to rank the most frequently requested technical skills.

   * **2_top_paying_skills.sql:** Calculates average and median compensation tied to specific tools and cloud platforms.

   * **3_optimal_skills.sql:** Evaluates the intersection of high market demand and high salary return using CTEs.

### 2️⃣ Data Warehouse & Mart Pipeline (2_DW_Mart_Build)
* **Objective:** Transform raw operational job market data into a structured, query-optimized Data Warehouse with dedicated downstream Data Marts.

* **Pipeline Workflow:**

   1. Schema Initialization & Ingestion (01 & 02): Defines normalized Fact and Dimension tables and ingests raw source files into DuckDB.

   2. One Big Table / Flat Mart (03): Denormalizes core entities into a wide analytical table (flat_mart) for zero-join BI querying.

   3. Domain-Specific Marts (04 – 07): Constructs dedicated marts for Skills, Priority Roles (including incremental DML updates), and Companies.
   4. End-to-End Orchestration (build_marts.sql): Executes the complete pipeline sequentially in a single command.
      
## ⚙️ How to Run Locally
1. **Clone the repository:**

```bash
git clone [https://github.com/Krish5102004/SQL_for_Data_Engineering.git](https://github.com/Krish5102004/SQL_for_Data_Engineering.git)
cd SQL_for_Data_Engineering
```
2. **Run the Automated Data Warehouse Build via DuckDB CLI:**

```bash
duckdb < Project/2_DW_Mart_Build/build_marts.sql
```
3. **Run Individual EDA Queries:**
   Open any script inside `Project/1_EDA_Project/` using VS Code or execute directly in DuckDB:

```bash
duckdb < Project/1_EDA_Project/1_top_demanded_skills.sql
```
```bash
duckdb < Project/1_EDA_Project/2_top_paying_skills.sql
```
```bash
duckdb < Project/1_EDA_Project/3_optimal_skills.sql
```
