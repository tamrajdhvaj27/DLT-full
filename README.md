# 📘 DLT-full

## 🔹 How to Create Lakeflow Spark Declarative Pipelines (SDP)?
Lakeflow Spark Declarative Pipelines (SDP) is the **next evolution of Delta Live Tables (DLT)**.  
To create an SDP pipeline:
1. Navigate to **Workflows → Lakeflow Pipelines** in Databricks.
2. Click **Create Pipeline**.
3. Provide:
   - **Source code path** (SQL/Python notebook).
   - **Target schema** (database).
   - **Cluster configuration**.
4. Define tables/views using declarative SQL (`CREATE STREAMING TABLE`, `CREATE MATERIALIZED VIEW`, etc.).
5. Deploy and monitor via the **new Pipeline Editor**.

---

## 🔹 How to Use the New Pipeline Editor in Databricks?
The **Pipeline Editor** is a unified command center:
- Left panel → Your SQL/Python code.
- Right panel → Auto-generated **visual graph** of pipeline dependencies.
- Click any node → Access **Data Preview**, **Performance Metrics**, and **Query Profiling** instantly.
- Eliminates context switching between notebooks and pipeline UI.

---

## 🔹 What Happened to DLT?
- **Delta Live Tables (DLT)** has been **donated to the Apache Foundation** and open-sourced.
- Databricks has rebranded and evolved DLT into **Lakeflow Declarative Pipelines (SDP)**.
- SDP is now the **standard declarative ETL framework**, with broader adoption beyond Databricks.

---

## 🔹 DLT vs SDP

| Feature                  | Delta Live Tables (DLT) | Spark Declarative Pipelines (SDP) |
|---------------------------|--------------------------|-----------------------------------|
| **Status**               | Proprietary Databricks feature | Open-source (Apache Foundation) |
| **UI**                   | Separate notebook + DLT UI | Unified Pipeline Editor |
| **Dependencies**         | Manual `LIVE` keyword | Auto-detected intelligently |
| **Debugging**            | Requires separate queries | Click-to-Debug with live previews |
| **Adoption**             | Limited to Databricks | Designed for industry-wide use |

---

## 🔹 What are Delta Live Tables (DLT) in Databricks?
Delta Live Tables (DLT) is a framework in Databricks for **building reliable, declarative ETL pipelines**.  
It simplifies data ingestion, transformation, and quality enforcement by managing dependencies, monitoring, and error handling automatically.

---

## 🔹 What is a DLT Pipeline?
A **DLT pipeline** is a workflow that:
- Defines tables and views using SQL or Python.
- Automates data ingestion, transformation, and validation.
- Handles orchestration, monitoring, and recovery without manual intervention.

---

## 🔹 What is a Streaming Table in DLT Pipeline?
A **Streaming Table**:
- Continuously ingests data from streaming sources (e.g., Kafka, Event Hubs, cloud storage).
- Appends new records incrementally whenever the pipeline refreshes.
- Is **append-only**; updates/deletes require downstream merges.

---

## 🔹 What is a Materialized View in DLT Pipeline?
A **Materialized View**:
- Stores the results of a query as a physical table.
- Refreshes on demand or on schedule (snapshot-based).
- Useful for aggregations, reporting, and analytics.

---

## 🔹 How to Create a DLT Pipeline?
1. Navigate to **Workflows → Delta Live Tables** in Databricks.
2. Click **Create Pipeline**.
3. Provide:
   - **Source code path** (SQL/Python notebook).
   - **Target schema** (database).
   - **Cluster configuration**.
4. Define tables using `CREATE LIVE TABLE` or `CREATE STREAMING LIVE TABLE`.
5. Deploy and monitor via the Databricks UI.

---

## 🔹 What is the `LIVE` Keyword in DLT Pipeline?
- The `LIVE` keyword declares a table/view inside a pipeline.  
- Example:
  ```sql
  CREATE LIVE TABLE customers_cleaned
  AS SELECT * FROM LIVE.raw_customers WHERE status = 'active';
