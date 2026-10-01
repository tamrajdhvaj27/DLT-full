# 📘 DLT-full

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
