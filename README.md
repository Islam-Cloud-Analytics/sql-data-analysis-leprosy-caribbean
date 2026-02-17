# Caribbean Leprosy Data Analysis

**End-to-end data pipeline** analyzing treatment outcomes across 7 Caribbean nations to identify intervention opportunities and support evidence-based public health policy.

> **Challenge:** Fragmented clinical data prevented regional pattern analysis and intervention targeting  
> **Solution:** Scalable constellation schema with automated ETL and real-time dashboards analyzing 200+ cases

---

## 🎯 Key Findings

- **Wide country-level performance gaps:** Success rates range from 20% (Guyana) to 59.4% (The Bahamas) - a 3x variance *[[View Dashboard]](Power%20BI%20Dashboards/Treatment%20Efficiency%20Perentage%20by%20Country.png)*
- **Public facilities significantly outperform private:** Success rates show 26.2% vs 11.1% (2.4x difference) *[[View Dashboard]](Power%20BI%20Dashboards/Hospitals%20Succcess%20Rate.png)*
- **40% of cases detected late (transfers):** High transfer-in rate indicates delayed initial diagnosis *[[View Dashboard]](Power%20BI%20Dashboards/Detection%20Methods%20Performance.png)*
- **Treatment adherence remains strong:** 80% adherence maintained across both MDT regimens *[[View Dashboard]](Power%20BI%20Dashboards/Average%20of%20Treatment%20Adherence.png)*

---

## 🏗️ Architecture

**Medallion Architecture (Bronze → Silver → Gold)**

| Layer | Function | Implementation |
|-------|----------|----------------|
| **Bronze** | Raw data ingestion | CSV imports from clinical systems |
| **Silver** | Data quality | Cleaning, deduplication, schema enforcement |
| **Gold** | Analytics-ready | Constellation schema (6 facts + 7 dimensions) |
| **Consumption** | Visualization | Power BI DirectQuery dashboards |

---

## 📐 Data Model

![Constellation Schema](https://github.com/Islam-Cloud-Analytics/sql-data-analysis-leprosy-caribbean/blob/main/Semantic%20Model.png)

**Constellation Schema (Galaxy Schema):**

**Fact Tables (6):**
- `fact_treatment_episode` - Treatment event details
- `fact_case_registration` - Case registration events  
- `treatment_efficiency_pe...` - Efficiency metrics
- `pblc_vs_prvt_treatment...` - Provider comparisons
- `avg_treatment_adhere...` - Adherence tracking
- `patient_distribution_by...` - Demographics

**Shared Dimensions (7):**
`dim_patients` | `dim_countries` | `dim_facilities` | `dim_dates` | `dim_subnational_unit` | `detection_methods` | `ref_leprosy_classification`

**Design Benefits:**
- Multi-grain analysis (transaction + aggregated views)
- Snowflaked geography (country → subnational drill-down)
- Shared dimensions ensure consistency across fact tables

---

## 📊 Dashboard Insights

### Treatment Outcomes

**Treatment Efficiency by Country** *[[Dashboard]](Power%20BI%20Dashboards/Treatment%20Efficiency%20Perentage%20by%20Country.png)*
- **Top 3:** The Bahamas (59.4%), Barbados (58.8%), Grenada (56.3%)
- **Regional average:** 49% success (98/200 cases)
- **Bottom performer:** Guyana (20%)

**Provider Performance** *[[Dashboard]](Power%20BI%20Dashboards/Hospitals%20Succcess%20Rate.png)*
- **Public facilities:** 26.2% success (151 cases)
- **Private providers:** 11.1% success (49 cases)
- **Key insight:** Public sector 2.4x more effective

### Detection & Demographics

**Detection Methods** *[[Dashboard]](Power%20BI%20Dashboards/Detection%20Methods%20Performance.png)*
- **Transfer-In:** 40% of registrations (36/90) - late detection indicator
- **New Cases:** 34.4% (31/90)
- **Most effective:** Active screening + household contact tracing
- **Disability grades at detection:** Grade 0 (90), Grade 1 (55), Grade 2 (55)

**Patient Distribution** *[[Dashboard]](Power%20BI%20Dashboards/Patients%20Distribution%20by%20Gender.png)*
- **Gender split:** 51.5% Male (103) | 48.5% Female (97)
- **Balanced distribution** across countries

**Treatment Adherence** *[[Dashboard]](Power%20BI%20Dashboards/Average%20of%20Treatment%20Adherence.png)*
- **MDT-PB regimen:** 80.1% adherence
- **MDT-MB regimen:** 79.65% adherence
- **Consistent compliance** across both treatment types

---

## 🚀 Tech Stack

| Component | Technology |
|-----------|------------|
| **Data Platform** | Databricks SQL |
| **ETL** | Spark SQL transformations |
| **Schema** | Constellation (6 facts, 7 dimensions) |
| **Visualization** | Power BI (DirectQuery) |
| **Version Control** | GitHub |

---

## 💡 Technical Highlights

**Data Engineering:**
- Medallion architecture (Bronze/Silver/Gold layers)
- Constellation schema with snowflaked dimensions
- SQL-based data quality (deduplication, validation)
- Multi-fact dimensional modeling

**Analytics:**
- Real-time DirectQuery dashboards
- Cross-country comparative analysis
- Multi-grain metrics (detail + aggregates)
- Healthcare outcome tracking

---

## 📁 Repository Structure
```
sql-data-analysis-leprosy-caribbean/
├── Gold Layer (permanent Views)/     # SQL transformations for fact/dim tables
├── Silver Layer (Denormalized)/      # Cleaned staging tables
├── Power BI report/                  # .pbix file (requires Databricks)
├── Power BI Dashboards/              # Dashboard screenshots (5 files)
│   ├── Treatment Efficiency Perentage by Country.png
│   ├── Hospitals Succcess Rate.png
│   ├── Detection Methods Performance.png
│   ├── Average of Treatment Adherence.png
│   └── Patients Distribution by Gender.png
├── Semantic Model.png                # Constellation schema diagram
├── Project Previews.md               # Detailed analysis documentation
└── README.md
```

---

## 🚀 Quick Start

**Prerequisites:** Databricks workspace + Power BI Desktop
```bash
# 1. Clone repository
git clone https://github.com/Islam-Cloud-Analytics/sql-data-analysis-leprosy-caribbean

# 2. Import SQL to Databricks
# - Upload CSVs to DBFS
# - Run Silver layer transformations
# - Create Gold layer views

# 3. Connect Power BI
# - DirectQuery to Databricks
# - Point to Gold layer tables
# - Open leprosy-analysis.pbix
```

📖 **[Detailed Setup →](Project%20Previews.md)**

---

## 📊 Sample Queries

**Treatment success by country:**
```sql
SELECT country, 
       success_rate_percent,
       total_treatments
FROM treatment_efficiency_per_country
ORDER BY success_rate_percent DESC;
```

**Public vs Private comparison:**
```sql
SELECT facility_type,
       AVG(success_rate_percent) as avg_success_rate,
       COUNT(*) as sample_size
FROM pblc_vs_prvt_treatment
GROUP BY facility_type;
```

---

## 🎯 Business Impact

**Policy Insights:**
- **Guyana intervention needed:** 20% success rate requires investigation and support
- **Investigate public sector best practices:** Identify factors driving 2.4x better outcomes
- **Early detection programs:** 40% transfer-in rate indicates need for improved screening
- **Treatment adherence:** 80% adherence validates current protocols

**Scalability:**
- Schema supports expansion to additional countries
- Real-time dashboards enable ongoing monitoring
- Dimension consistency allows historical trending

---

## ⚠️ Important Notes

- Power BI dashboard requires active Databricks connection
- All patient data is anonymized and aggregated
- Contact for demo access or collaboration

---

## 📫 Contact

Built as part of my data engineering portfolio.

**[LinkedIn](#)** | **[Portfolio](#)** | **[Email](#)**

---

**⭐ Star this repo if you find it helpful!**
