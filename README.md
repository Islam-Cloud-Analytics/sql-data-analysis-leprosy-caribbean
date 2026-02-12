# Caribbean Leprosy Data Analysis 🩺

A data engineering and analytics project leveraging **Databricks** for ETL and **Power BI** for real-time reporting via DirectQuery.

---

## 🚀 Tech Stack
* **Data Lakehouse:** Databricks (Delta Lake)
* **ETL/Orchestration:** Spark SQL / Databricks Git Folders
* **Visualization:** Power BI (DirectQuery)
* **Version Control:** GitHub

---

## 🏗️ Data Architecture
1. **Bronze:** Raw clinical data ingestion.
2. **Silver:** Data cleaning, deduplication, and schema enforcement.
3. **Gold:** Business-ready Star Schema (Dimensions & Fact tables).

---

## 📊 Dashboard Insights

### 1. Treatment Efficiency by Country
* **Metric:** Success rate percentage vs. total treatments.
* **Key Finding:** Identifies regional performance gaps across the Caribbean.

### 2. Provider & Demographic Performance
| Metric | Detail |
| :--- | :--- |
| **Public vs Private** | Public facilities show higher success rates (26.2%) than Private (11.1%). |
| **Gender Split** | Analysis shows a nearly even distribution (51.5% Male / 48.5% Female). |
| **Adherence** | Average treatment adherence remains stable around 80% across MDT regimens. |

---

## 🖼️ Project Previews
*Insert your screenshots here using the syntax below:*

![Dashboard Overview](docs/image_e2ca98.png)
*Figure 1: Treatment Efficiency Map & Regional Stats*

![Demographics](docs/image_e2caf8.png)
*Figure 2: Gender and Country Distribution Analysis*

---

## 📁 Repository Structure
* `📂 notebooks/` - SQL ETL scripts for Gold layer transformation.
* `📂 pbi_report/` - .pbix file (Note: Requires Databricks connection).
* `📂 docs/` - High-res screenshots and project documentation.

---

**Would you like me to help you write the SQL `CREATE TABLE` statements for your Gold layer based on your Power BI field list?**
