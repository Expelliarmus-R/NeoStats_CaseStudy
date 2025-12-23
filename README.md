# NeoStats_CaseStudy


**Technologies:**  
Azure Data Factory | Azure Data Lake Gen2 | Parquet | Power BI | GitHub  

---

##  Project Objective

Build a complete **data engineering + analytics pipeline** to monitor server performance by:
- Ingesting raw server logs
- Cleaning and aggregating data using ADF
- Storing data in Bronze, Silver, and Gold layers
- Creating interactive dashboards in Power BI
- Managing everything using GitHub version control


##  Overall Architecture
1) Raw Server Logs + Metadata  
2) Azure Data Factory (ETL) 
3) Azure Data Lake Storage Gen2  
i).bronze/ (raw data)
ii).silver/ (cleaned & standardized)
iii).gold/ (aggregated KPIs)
4)powerBI DashBoards (UseD the gold Layer tables in PowerBi)




---

##  Tools & Services Used

| Layer | Tool |
|-----|------|
| ETL | Azure Data Factory |
| Storage | ADLS Gen2 |
| File Format | Parquet |
| Analytics | Power BI Desktop |
| Version Control | GitHub |
| Auth | Azure AD (Organizational Account) |

---

##  Data Layers Explained

###  Bronze Layer (Raw)
- Stores data exactly as received
- No transformation
- Format: Parquet

Example fields:
- `server_id`
- `log_timestamp`
- `cpu_utilization`
- `memory_usage`
- `disk_io`
- `uptime_hours`
- `downtime_hours`

---

###  Silver Layer (Cleaned)
Transformations applied:
- Removed null values
- Standardized column names
- Converted timestamps
- Joined server metadata
- Unified multiple sources using UNION

Output:
- Clean, analytics-ready dataset

---

###  Gold Layer (Aggregated)
Aggregations:
- Avg CPU utilization
- Avg memory usage
- Total uptime hours
- Total downtime hours
- Metrics grouped by:
  - server_id
  - server_cluster
  - date

Stored in Parquet for reporting.

---

##  Azure Data Factory – What We Built

### ADF Components
- Pipelines
- Dataflows
- Linked Services
- Datasets
- Triggers

### ETL Flow
1. Source → read raw station logs
2. Select → required columns only
3. Derived Column → clean & standardize
4. Union → merge multiple station inputs
5. Join → enrich with metadata
6. Aggregate → compute KPIs
7. Sink → write to Silver / Gold containers

---

##  GitHub Integration with ADF

All ADF artifacts are stored in GitHub.












