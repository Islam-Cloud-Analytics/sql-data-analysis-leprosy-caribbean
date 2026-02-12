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

![Dashboard Overview](Power%20BI%20Dashboards/Average%20of%20Treatment%20Adherence.png)
*Figure 1: Average of Treatment Adherence*

![Demographics](Power%20BI%20Dashboards/Patients%20Distribution%20by%20Gender.png)
*Figure 2: Gender and Country Distribution Analysis*

![Detection Methods](Power%20BI%20Dashboards/Detection%20Methods%20Performance.png)
*Figure 3: Detection Methods Performance*

![Success Rate](Power%20BI%20Dashboards/Hospitals%20Succcess%20Rate.png)
*Figure 4: Hospitals Treatment Success Rate (Public vs Private)*

![Treatment Efficiency](Power%20BI%20Dashboards/Treatment%20Efficiency%20Perentage%20by%20Country.png)
*Figure 5: Treatment Efficiency Percentage by Country*

---

## 📁 Repository Structure
* `📂 notebooks/` - SQL ETL scripts for Gold layer transformation.
* `📂 pbi_report/` - .pbix file (Note: Requires Databricks connection).
* `📂 docs/` - High-res screenshots and project documentation.

---

**Would you like me to help you write the SQL `CREATE TABLE` statements for your Gold layer based on your Power BI field list?**
