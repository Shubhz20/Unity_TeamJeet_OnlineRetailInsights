# Unity_TeamJeet_OnlineRetailInsights

> **Newton School of Technology | Data Visualization & Analytics**
> A 2-week industry simulation capstone using Python, GitHub, and Tableau to convert raw data into actionable business intelligence.

| Field | Details |
|---|---|
| **Project Title** | Online Retail Insights |
| **Sector** | Retail / E-commerce |
| **Team ID** | TeamJeet |
| **Section** | Unity |
| **Faculty Mentor** | _To be filled by team_ |
| **Institute** | Newton School of Technology |
| **Submission Date** | _To be filled by team_ |

| Role | Name | GitHub Username |
|---|---|---|
| Project Lead | Shibaditya | `github-handle` |
| Data Lead | Harshit Agrawal | `github-handle` |
| ETL Lead | Harshit Agrawal | `github-handle` |
| Analysis Lead | Jeet Shrivastav | `github-handle` |
| Visualization Lead | Jay Patil | `github-handle` |
| Strategy Lead | Arohi Jadhav | `github-handle` |
| PPT and Quality Lead | Shibaditya | `github-handle` |

---

## Business Problem
For a mid-market UK e-commerce retailer operating across ~40 countries, the core challenge is to identify revenue-driving customer segments, at-risk repeat buyers, and product-level profitability to ultimately recommend where the retailer should reallocate retention and promotional spend.

**Core Business Question**
> What are the key customer segments and product categories that drive the top 20% of revenue, and what are the drivers of churn in the repeat-purchase base?

**Decision Supported**
> Reallocation of retention and promotional budget that protects the revenue-concentration base while recovering at-risk customers.

---

## Dataset
| Attribute | Details |
|---|---|
| **Source Name** | Online Retail II (UCI Machine Learning Repository) |
| **Direct Access Link** | [UCI Dataset](https://archive.ics.uci.edu/dataset/502/online+retail+ii) |
| **Row Count** | ~1,067,000 |
| **Column Count** | 8 raw columns (16 engineered) |
| **Time Period Covered** | 01-Dec-2009 to 09-Dec-2011 |
| **Format** | Excel (.xlsx) converted to CSV |

**Key Columns Used**

| Column Name | Description | Role in Analysis |
|---|---|---|
| Invoice | Invoice number (C prefix for returns) | Order tracking & returns |
| StockCode | 5-digit product code | Product analysis |
| Description | Free-text product name | Category parsing |
| Quantity | Units sold (negative for returns) | Volume metrics |
| InvoiceDate | Timestamp of invoice | Time series analysis |
| Price | Unit price in GBP (£) | Value metrics |
| Customer ID | Unique identifier for each customer | Customer segmentation |
| Country | Country of customer | Geographic split |

For full column definitions, see [`docs/data_dictionary.md`](docs/data_dictionary.md).

---

## KPI Framework
| KPI | Definition | Formula / Computation |
|---|---|---|
| **Net Revenue** | Revenue after returns — the primary P&L metric | `Σ(LineRevenue where not IsReturn) − Σ(|LineRevenue| where IsReturn)` |
| **Return Rate** | Quality signal | `rows(IsReturn) / rows(all)` |
| **Repeat Purchase Rate** | Health of the retention engine | `customers with ≥2 invoices / total registered customers` |
| **Avg Order Value (AOV)** | Pricing + basket composition health | `Net Revenue per invoice` |
| **RFM Score** | Customer segmentation for retention prioritization | Recency, Frequency, Monetary quintiled and concatenated |
| **Top-20% Concentration** | Pareto — measures dependence risk | `rev from top 20% of customers / total rev` |

---

## Tableau Dashboard
| Item | Details |
|---|---|
| **Dashboard URL** | _[To be published to Tableau Public]_ |
| **Executive View** | **Revenue Overview** — Net revenue by month, country, top-20% concentration |
| **Operational View** | **Customer Segments** — RFM segments; **Product Performance**; **Retention Health** |
| **Main Filters** | Country, Date range, RFM segment, Registered vs Guest checkout |

---

## Key Insights
_Pending analysis completion. To be updated post-EDA._

---

## Recommendations
_Pending analysis completion. To be updated post-EDA._

---

## Repository Structure
```text
Unity_TeamJeet_OnlineRetailInsights/
|
|-- README.md
|
|-- data/
|   |-- raw/                         # Original dataset (never edited)
|   `-- processed/                   # Cleaned output from ETL pipeline
|
|-- notebooks/
|   |-- 01_extraction.ipynb
|   |-- 02_cleaning.ipynb
|   |-- 03_eda.ipynb
|   |-- 04_statistical_analysis.ipynb
|   `-- 05_final_load_prep.ipynb
|
|-- scripts/
|   `-- etl_pipeline.py
|
|-- tableau/
|   |-- screenshots/
|   `-- dashboard_links.md
|
|-- reports/
|   |-- README.md
|   |-- project_report_template.md
|   `-- presentation_outline.md
|
|-- docs/
|   `-- data_dictionary.md
|
|-- DVA-oriented-Resume/
`-- DVA-focused-Portfolio/
```

---

## Analytical Pipeline
The project follows a structured 7-step workflow:

1. **Define** - Sector selected, problem statement scoped, mentor approval obtained.
2. **Extract** - Raw dataset sourced and committed to `data/raw/`; data dictionary drafted.
3. **Clean and Transform** - Cleaning pipeline built in `notebooks/02_cleaning.ipynb` and optionally `scripts/etl_pipeline.py`.
4. **Analyze** - EDA and statistical analysis performed in notebooks `03` and `04`.
5. **Visualize** - Interactive Tableau dashboard built and published on Tableau Public.
6. **Recommend** - 3-5 data-backed business recommendations delivered.
7. **Report** - Final project report and presentation deck completed and exported to PDF in `reports/`.

---

## Tech Stack
| Tool | Purpose |
|---|---|
| Python + Jupyter Notebooks | ETL, cleaning, analysis, and KPI computation |
| Google Colab | Cloud notebook execution environment |
| Tableau Public | Dashboard design, publishing, and sharing |
| GitHub | Version control, collaboration, contribution audit |
| SQL | Initial data extraction only, if documented |

**Python libraries:** `pandas`, `numpy`, `matplotlib`, `seaborn`, `scipy`, `statsmodels`

---

## Contribution Matrix
| Team Member | Dataset and Sourcing | ETL and Cleaning | EDA and Analysis | Statistical Analysis | Tableau Dashboard | Report Writing | PPT and Viva |
|---|---|---|---|---|---|---|---|
| Harshit Agrawal | Owner | Owner | Support | Support | Support | Support | Support |
| Jeet Shrivastav | Support | Support | Owner | Owner | Support | Support | Support |
| Arohi Jadhav | Support | Support | Support | Support | Owner | Support | Support |
| Jay Patil | Support | Support | Support | Support | Owner | Support | Support |
| Shibaditya | Support | Support | Support | Support | Support | Owner | Owner |

---

*Newton School of Technology - Data Visualization & Analytics | Capstone 2*
