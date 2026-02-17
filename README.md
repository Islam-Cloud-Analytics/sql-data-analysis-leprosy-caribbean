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
| Metric | Detail |
| :--- | :--- |
| **Success Rate Range** | Treatment efficiency varies from 20% (Guyana) to 59.4% (The Bahamas) across the region. |
| **Top Performers** | The Bahamas (59.4%), Barbados (58.8%), and Grenada (56.3%) demonstrate highest success rates. |
| **Overall Regional Rate** | Aggregate success rate stands at 49% (98 successful treatments out of 200 total cases). |

### 2. Provider & Demographic Performance
| Metric | Detail |
| :--- | :--- |
| **Public vs Private** | Public facilities achieve significantly higher success rates (26.2%) compared to private providers (11.1%). |
| **Gender Distribution** | Patient distribution shows 51.5% Male (103 patients) and 48.5% Female (97 patients). |
| **Treatment Adherence** | MDT-PB regimen shows 80.1% adherence while MDT-MB maintains 79.65% adherence. |

### 3. Detection Methods & Case Registration
| Metric | Detail |
| :--- | :--- |
| **Primary Detection** | Transfer-In cases represent 40% (36/90) of registrations, followed by New Cases at 34.4% (31/90). |
| **Most Effective Method** | Active Screening and Household Contact tracing identify majority of cases across all registration types. |
| **Case Severity** | Grade 0 disability accounts for 90 cases, Grade 1 for 55 cases, and Grade 2 for 55 cases at detection. |

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
* `📂 Gold Layer (permanent Views)/` - SQL ETL scripts for Gold layer transformation.
* `📂 Silver Layer (Denormalized tables)/` - Tables ready to be worked on for further enrichment and insights.
* `📂 Power BI report/` - .pbix file (Note: Requires Databricks connection).
* `📂 Power BI Dashboards/` - High-res screenshots and project documentation.
* `📂 docs/` - High-res screenshots and project documentation.
---
