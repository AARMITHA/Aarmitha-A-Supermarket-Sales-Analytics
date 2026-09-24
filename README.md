# Supermarket Sales Analytics

**AICTE – IBM SkillsBuild Data Analytics Internship Project**  
**Author:** Aarmitha  
**Project Title:** Supermarket Sales Analytics  
**Domain:** Retail Analytics & Business Intelligence  

---

## 1. Project Description
The **Supermarket Sales Analytics** project provides an end-to-end, data-driven analysis of customer transactions across multiple regional supermarket branches in New York City (Brooklyn, Queens, Manhattan) for the entire calendar year 2024.

Operating in a high-volume, low-margin retail environment, supermarket management must continuously balance inventory procurement, regional assortment preferences, promotional strategies, and checkout operational efficiency. This project analyzes **5,053 historical customer transactions** to:
1. Establish baseline retail **Key Performance Indicators (KPIs)**.
2. Uncover regional branch behavioral profiles and product line demand dynamics.
3. Quantify the financial value of customer loyalty memberships.
4. Diagnose seasonal sales volatility and peak-season operational bottlenecks.
5. Translate empirical findings into practical, actionable business strategies using the structured framework:
   $$\text{Fact} \longrightarrow \text{Insight} \longrightarrow \text{Recommended Action}$$

---

## 2. Dataset Description
The analysis is conducted on the official transaction record file `Supermarket Sales 2.csv`.

* **Total Records:** 5,053 completed retail sales transactions
* **Time Horizon:** January 1, 2024 – December 31, 2024 (12 Full Months)
* **Geographical Scope:** 3 New York City Regional Branches (Brooklyn, Queens, Manhattan)
* **Attribute Schema:**

| Column Name | Data Type | Description | Values / Range |
| :--- | :--- | :--- | :--- |
| `Date` | `object` &rarr; `datetime64[ns]` | Transaction timestamp (MM/DD/YYYY) | 01/01/2024 to 12/31/2024 |
| `Branch` | `object` (Categorical) | Supermarket branch location | Brooklyn, Queens, Manhattan |
| `Customer type` | `object` (Categorical) | Loyalty membership status | Member, Normal |
| `Gender` | `object` (Categorical) | Customer demographic identification | Female, Male |
| `Product line` | `object` (Categorical) | Merchandise product category | 6 lines (Food, Electronics, etc.) |
| `Unit price` | `float64` | Price per single unit in USD ($) | $2.01 to $99.96 |
| `Quantity` | `int64` | Physical units purchased per order | 1 to 10 items |
| `Payment` | `object` (Categorical) | Settlement payment tender | Ewallet, Credit card, Cash |
| `Rating` | `float64` | Customer checkout satisfaction score | 3.0 to 10.0 scale |

* **Engineered Features:**
  * `Total`: Transaction Gross Sales ($\text{Unit price} \times \text{Quantity}$)
  * `Month`: Temporal period (`YYYY-MM`)
  * `Month_Name`: Full calendar month (`January` to `December`)
  * `DayOfWeek`: Day of week (`Monday` to `Sunday`)
  * `Quarter`: Business quarter (`Q1`, `Q2`, `Q3`, `Q4`)

---

## 3. Dataset Source & Attribution
* **Dataset File:** `Supermarket Sales 2.csv`
* **Source/Context:** IBM SkillsBuild & AICTE Internship Program — Retail Analytics Capstone.
* **Reference Data Source:** Based on standardized supermarket retail point-of-sale (POS) transactional records (Kaggle Supermarket Sales benchmark dataset format).

---

## 4. Technologies Used
* **Core Language:** Python 3.10+
* **Data Processing & Manipulation:** `pandas` (v2.3+), `numpy` (v2.2+)
* **Data Visualization & Plotting:** `matplotlib` (v3.10+), `seaborn` (v0.13+)
* **Interactive Notebook Environment:** `jupyter`, `ipykernel`, `nbformat`, `nbclient`
* **Automated Executive Reporting:** `python-docx` (v1.2+)

---

## 5. Setup Instructions

### Prerequisites
* Python 3.10 or higher installed on your system.
* A terminal / command prompt (PowerShell, Bash, or Command Prompt).

### Installation Steps
1. **Clone or Navigate to the Project Directory:**
   ```bash
   cd c:\Users\Aarmitha\Pictures\AICTE_ibm_internship
   ```

2. **(Optional but Recommended) Create a Virtual Environment:**
   ```bash
   python -m venv .venv
   # Windows PowerShell:
   .venv\Scripts\Activate.ps1
   # macOS/Linux:
   source .venv/bin/activate
   ```

3. **Install Dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

---

## 6. How to Run

### Method 1: Open and Run the Jupyter Notebook
Launch Jupyter Notebook or open it directly in VS Code / JupyterLab:
```bash
jupyter notebook Aarmitha_SupermarketSalesAnalytics.ipynb
```
Select **"Run All Cells"** from the menu. The notebook will sequentially execute data loading, cleaning, KPI calculation, visualization rendering, and business synthesis.

### Method 2: Regenerate Charts and Reports via Scripts
If you wish to re-generate the visual assets and the Microsoft Word project report from scratch:
```bash
# 1. Generate high-resolution chart PNGs
python generate_assets.py

# 2. Build and execute the Jupyter Notebook
python build_notebook.py

# 3. Generate the comprehensive Word report
python generate_report.py
```

---

## 7. Key Performance Indicators (KPIs)

Calculated across all **5,053 transactions** in FY 2024:

| Key Performance Indicator | Actual Metric Value | Strategic Definition |
| :--- | :--- | :--- |
| **Total Revenue** | **$942,544.85** | Gross sales generated across all 3 branches |
| **Total Sales / Transactions** | **5,053 orders** | Total completed customer checkouts |
| **Average Transaction Value (ATV)** | **$186.53** | Mean financial expenditure per customer basket |
| **Total Quantity Sold** | **23,211 units** | Total physical merchandise units purchased (4.59 items/order) |
| **Average Customer Rating** | **6.88 / 10.0** | Customer checkout satisfaction score (Median: 7.0) |

---

## 8. Key Findings: Fact &rarr; Insight &rarr; Recommended Action

### 1. Customer Loyalty Monetization Opportunity
* **FACT:** Registered **Members** generate an Average Transaction Value of **$209.29**, delivering a **+22.7% spend premium** over **Normal** walk-in shoppers (**$170.54**). Members buy both higher-priced items ($41.99 vs $38.08) and larger quantities (4.84 vs 4.42 units). However, **58.74% of checkouts (2,968 transactions)** remain non-members.
* **INSIGHT:** The loyalty program effectively cultivates higher-spending behavior, but the supermarket suffers from an under-penetrated onboarding funnel at the register.
* **RECOMMENDED ACTION:** Deploy a 10-second instant POS enrollment prompt offering $5 off the current basket. Converting just 20% of Normal shoppers (594 orders) to Member spend yields **+$23,020 in incremental annual gross revenue** with zero customer acquisition ad spend.

### 2. Category Footfall Anchor vs Basket Value
* **FACT:** **Food & Beverages** generates the highest footfall (**1,670 orders, 33.05% of all store visits**) and the highest customer rating (**7.08/10**), but has the lowest ATV at **$90.63** (less than half the storewide average). Conversely, **Home & Lifestyle** drives the highest revenue (**$197,260.56, 20.93% share**, ATV $278.62).
* **INSIGHT:** Food & Beverages is the primary traffic anchor, but customers treat it as an isolated grocery run without browsing high-margin discretionary aisles.
* **RECOMMENDED ACTION:** Restructure store layouts to place high-margin cookware, storage tools, and wellness supplements on end-cap displays directly inside grocery aisles.

### 3. Severe Summer Seasonal Revenue Slump
* **FACT:** Monthly revenue plunged **85.3%** from April (**$132,084**) to August (**$19,440**). Transaction volume stayed relatively resilient (dropping only from 447 to 363), but average unit price dropped from $57.49 to $21.80 and quantity halved from 5.20 to 2.69, causing ATV to collapse to $53.55.
* **INSIGHT:** Footfall remains steady in summer, but customers stop buying high-ticket discretionary goods (Electronics, Sports, Lifestyle) and restrict purchases exclusively to low-priced grocery essentials.
* **RECOMMENDED ACTION:** Launch a dedicated "Summer Living & Travel" promotional campaign starting in May, stocking portable coolers, camping gear, outdoor audio, and BBQ kits to defend basket size above $150.

### 4. Regional Branch Specialization (Queens vs Brooklyn vs Manhattan)
* **FACT:** Total revenue is evenly split across boroughs (~$310K–$320K each), but **Queens** achieves the highest ATV (**$201.19**) from the lowest transaction count (1,555), while **Brooklyn** captures the highest footfall (**1,793 orders**) at an ATV of $178.31. **Manhattan** achieves the highest satisfaction rating (**6.91/10**).
* **INSIGHT:** Queens serves suburban family shoppers making planned bulk purchases; Brooklyn functions as an urban high-density convenience hub for frequent small visits; Manhattan serves service-sensitive urban professionals.
* **RECOMMENDED ACTION:**
  * *Queens:* Introduce multi-buy volume discounts and family-sized bulk merchandise packs.
  * *Brooklyn:* Expand self-checkout lanes and grab-and-go convenience displays.
  * *Manhattan:* Enhance premium product curation and express digital checkout.

### 5. Peak-Season Service Paradox (Q4 Bottleneck)
* **FACT:** Customer ratings reached annual highs during the low-volume summer (**7.54/10 in June**), but collapsed to annual lows during peak holiday footfall (**6.32/10 in November, 6.53/10 in December**), precisely when transactions peaked at 557 and 568.
* **INSIGHT:** Operational capacity breaks down under peak holiday crowds due to checkout register queues, shelf stockouts, and understaffing.
* **RECOMMENDED ACTION:** Hire seasonal staff for Q4, deploy mobile tablet-based line-busting cashiers during rush hours, and transition restocking to overnight shifts.

### 6. Fashion & Accessories Underperformance
* **FACT:** Fashion & Accessories generated the lowest revenue (**$101,843.91, 10.81% share**) and the lowest customer rating (**6.70/10**).
* **INSIGHT:** The fashion assortment suffers from weak product-market fit, uncompetitive pricing, and poor customer perception.
* **RECOMMENDED ACTION:** Conduct an immediate SKU rationalization audit, liquidate slow inventory via a 30% markdown, and shift floor space to high-turnover everyday basics and home goods.

---

## 9. Deliverables Directory Structure

```
c:\Users\Aarmitha\Pictures\AICTE_ibm_internship\
│
├── Aarmitha_SupermarketSalesAnalytics.ipynb  # Primary Jupyter Notebook (Fully Executed with all outputs & plots)
├── Aarmitha_ProjectReport.docx               # Comprehensive Professional Word Report (Tables, Charts, Insights)
├── README.md                                 # Complete Project Documentation & Overview
├── requirements.txt                          # Project Python Dependencies Specification
├── Supermarket Sales 2.csv                   # Original Source Dataset (5,053 transactions)
│
├── charts/                                   # High-Resolution Publication-Quality Visualizations (DPI=300)
    ├── 01_kpi_dashboard.png
    ├── 02_monthly_trend.png
    ├── 03_branch_performance.png
    ├── 04_product_line_performance.png
    ├── 05_customer_type_analysis.png
    ├── 06_rating_vs_traffic.png
    └── 07_payment_and_gender.png

```

---

## 10. Conclusion
This project demonstrates that supermarket profitability can be substantially expanded through targeted, data-backed operational adjustments. By converting non-member footfall into loyalty members, cross-merchandising high-margin categories into grocery aisles, buffering against summer sales slumps, and solving holiday checkout bottlenecks, supermarket leadership can secure sustainable revenue growth and elevated customer retention.
