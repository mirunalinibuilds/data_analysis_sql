# Enterprise Sales Insights: Advanced SQL Data Analytics

A comprehensive analytics suite containing production-ready SQL scripts optimized for analyzing enterprise sales data models. The project transitions from basic database exploration to complex operational analysis, utilizing advanced T-SQL mechanics, analytical window functions, and multi-tier Common Table Expressions (CTEs) to isolate core revenue channels and classify consumer behavior patterns.

## 📊 Business Scenario & Dataset Scale

In an enterprise environment, raw transactional logs are scattered across isolated systems, obscuring critical long-term trends. This repository provides the query layer to transform a structured relational database into actionable business intelligence.

The analysis is executed against a comprehensive relational sales model representing:
* **Total Transactions:** 60,398 comprehensive sales records
* **Customer Base:** 18,484 unique registered consumers
* **Product Catalog:** 295 distinct inventory units across multiple categories
* **Gross Volume:** Over ₹29.4 Million (approx. 29.4M) in total consolidated sales

## 📁 Repository Structure

scripts/
├── 01_init_database.sql           # Database creation, schema initialization, and table definitions
├── 02_bulk_load_data.sql          # Truncate commands and BULK INSERT operations for raw CSV ingestion
├── 03_database_exploration.sql    # Metadata evaluation using INFORMATION_SCHEMA filters
├── 04_dimensions_exploration.sql  # Distinct value exploration across dimensional vectors
├── 05_date_range_exploration.sql  # Temporal boundary identification and outlier/age tracking
├── 06_measures_exploration.sql    # Global aggregate health check reports and metric unions
├── 07_magnitude_analysis.sql      # Group-by dimensional matrices and cross-category revenue calculations
├── 08_ranking_analysis.sql        # Top-performing cohort identification and density-rank metrics
├── 09_change_over_time.sql        # Time-series analysis, temporal distributions, and date truncations
├── 10_cumulative_analysis.sql      # Running totals, partitions by year, and moving average layers
└── 11_performance_analysis.sql     # Multi-tier CTEs for Year-over-Year (YoY) variance computation

## 🛠️ Advanced Analytics Architecture

The analytical suite leverages performance-focused T-SQL workflows to extract deep business metrics:

### 1. Temporal & Year-over-Year (YoY) Growth Patterns
* **Rolling Time-Series Processing:** Combines `LAG()` and `LEAD()` analytical window functions with dynamic date partitioning to contrast historical revenue lines against concurrent monthly intervals.
* **Moving Average Baselines:** Implements precise `ROWS BETWEEN` windows to establish 3-month moving trends, dampening structural seasonal variation across transactional records.
* **Aggregated Accumulation:** Configures ongoing running financial totals partitioned by product segments using unbounded analytical frameworks.

### 2. Micro-Segmented Database Reporting Views
To abstract operational data for BI consumption, two reusable enterprise views were engineered:
* **The Customer Segmentation Engine (`vw_Customer_Segmentation`):** Implements conditions to classify the entire 18,484 consumer registry into structured strategic cohorts:
  * **VIP (1,653 Customers):** High-frequency, high-value purchasers.
  * **Regular (2,200 Customers):** Repeat baseline consumers showing stable patterns.
  * **New (14,629 Customers):** Incipient transactional accounts requiring active retention.
* **The Product Performance Matrix (`vw_Product_Performance`):** Categorizes 130 structural inventory components across performance boundaries: **High (66)**, **Mid (58)**, and **Low (6)** performers based on gross margin contributions.

### 3. Paretean Revenue & Domain Dispositions
* **Concentration Evaluation:** Wrote multi-layered aggregate queries mapping catalog distributions to isolate structural margin dependencies.
* **Core Insight Output:** Isolated that the **Bikes** category structurally anchors enterprise cash flow, generating approximately **96% of all incoming sales revenue**.

## 🧬 SQL Core Concepts Demonstrated

This project serves as a showcase of optimized, enterprise-grade database engineering practices:
* **Common Table Expressions (CTEs):** Multi-layered, readable querying blocks bypassing unnecessary nested subqueries.
* **Window Functions:** Advanced processing using `SUM() OVER`, `ROW_NUMBER()`, `LAG()`, and custom analytical framing.
* **Conditional Case Expressions:** Complex logical branching patterns within high-performance reporting schemas.
* **Schema Abstraction via Views:** Transforming transactional data tables into business-ready analytical structures.
* **Relational Join Performance:** Clean implementation of multiple `INNER JOIN` and `LEFT JOIN` operations across dimension tables while maintaining indexing integrity.

## 📈 Key Insights Derived

1. **Strategic Dependency:** The vast majority of income is derived from a single category (Bikes), showing an operational risk if market dynamics change.
2. **Growth Funnel Challenge:** While the platform successfully hooks entry-level traffic (14.6K New users), the drop-off to the Regular tier indicates a need for optimized loyalty pipelines.
3. **Inventory Streamlining:** By mapping the 6 underperforming products, administrative operations can safely execute catalog liquidation strategies to unlock tied-up capital.

## 💻 Quick Start & Deployment

To execute these queries against your local server instance:
1. Clone the repository workspace:
   ```bash
   git clone https://github.com
   ```
2. Open Microsoft SQL Server Management Studio (SSMS) or Azure Data Studio.
3. Target your configured operational data cluster.
4. Execute scripts sequentially from the `/scripts` directory to observe real-time analytical generation.

**Author:** Mirunalini A. R. A.  
