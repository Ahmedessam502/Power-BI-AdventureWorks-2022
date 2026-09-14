# 📊 AdventureWorks 2022 Sales Dashboard (Power BI)

An interactive **multi-page Power BI Business Intelligence project** built using the **AdventureWorks 2022 relational database**.

The project demonstrates an end-to-end BI workflow starting from a **SQL Server database**, importing data into **Microsoft Power BI**, preparing the data with **Power Query**, building a relational **Data Model**, creating reusable **DAX measures**, and designing interactive dashboards for business analysis.

---

# 📷 Dashboard Preview

## 🏠 Main Dashboard

![Main Dashboard](Screenshots/Main%20Page.png)

The Main dashboard provides an executive overview of order activity and includes:

- No. of Orders
- Total Quantity
- Total Freight
- Total Tax
- Total Subtotal
- Orders by Ship Method
- Orders by Month
- Orders by Product
- Orders by SalesPersonID
- Year filtering
- Territory filtering
- KPI Cards
- Interactive navigation and visual filtering

---

## 📦 Product Dashboard

![Product Dashboard](Screenshots/Product%20Page.png)

The Product page focuses on product, salesperson, quota, and sales-related analysis.

It includes:

- Orders by Product
- SalesQuota and Territory analysis
- Sales representative analysis
- Product performance
- Sum of LineTotal by Product
- Product hierarchy
- Product Subcategory analysis
- Product Category analysis
- Territory comparison
- Year filtering
- Territory filtering
- Interactive visual filtering

Product hierarchy:

**Product → Product Subcategory → Product Category**

---

## 🌍 Territory Dashboard

![Territory Dashboard](Screenshots/Territory%20Page.png)

The Territory page focuses on geographic, sales, status, and time-based analysis.

It includes:

- Total Subtotal by Territory
- No. of Orders by SalesQuota and Territory
- Sum of LineTotal by Product
- No. of Orders by FirstName and LastName
- Total Due and No. of Orders by Territory
- No. of Orders by StatusName
- Sum of LineTotal by ProductSubcategory
- Sum of TotalDue by Year / Month
- Territory filtering
- Geographic Map visualization
- Chart / Map switching
- Interactive navigation

---

## 🗂️ Data Model

![Data Model](Screenshots/Data%20Modeling.png)

The project uses a relational Power BI Data Model instead of relying on one flat table.

The model contains:

- **OrderDetail** — central transaction/order-detail data
- **Product** — product and product hierarchy information
- **ShipMethod** — shipping method information
- **Territory** — territory information
- **vSalesPerson** — sales representative information
- **Status** — order status information
- **Dates** — date dimension for time-based analysis
- **Mymeasures** — dedicated table for organizing DAX measures

The relationships between these tables allow filters and calculations to flow through the report.

---

# 🗄️ Data Source

This project is based on the **AdventureWorks 2022** database.

The original data source was provided as a **SQL Server backup (`.bak`)** file.

The database was restored in **Microsoft SQL Server**, then connected to **Microsoft Power BI**, where the required data was imported for analysis.

The imported data was then prepared using **Power Query**, structured through the **Power BI Data Model**, and analyzed using **DAX**.

### 🔄 End-to-End Data Workflow

```text
AdventureWorks 2022 Database
            ↓
      SQL Server Database
            ↓
      Database Restore
            ↓
        Data Import
            ↓
       Power Query
            ↓
Data Transformation & Preparation
            ↓
      Power BI Data Model
            ↓
        Relationships
            ↓
        DAX Measures
            ↓
     Interactive Dashboards
```

### 📥 Original Database

The original **AdventureWorks 2022 SQL Server backup** is available from the official Microsoft SQL Server Samples repository:

[Download AdventureWorks2022.bak](https://github.com/Microsoft/sql-server-samples/releases/download/adventureworks/AdventureWorks2022.bak)

> The database backup is not stored directly in this repository because of its large file size. The original database can be downloaded directly from Microsoft's official GitHub repository.

---

# 📊 Dataset

The AdventureWorks 2022 database provides the business data used to build the report.

The Power BI model includes data related to:

- Orders / Order Details
- Products
- Product Categories
- Product Subcategories
- Sales Representatives
- Sales Quota
- Territories
- Shipping Methods
- Order Status
- Dates
- Freight
- Tax
- Subtotal
- Total Due
- Line Total

The data model supports analysis across products, categories, territories, sales representatives, shipping methods, status, and time.

---

# 🔄 Power Query

**Power Query** is used as part of the data preparation and ETL workflow.

The workflow starts with importing data from the SQL Server database into Power BI and preparing the data before it is used in the analytical model.

### Power Query workflow

- Data Extraction
- Data Import
- Data Transformation
- Data Preparation
- Data Type Handling
- Structuring source data
- Preparing tables for the Data Model

Power Query acts as the preparation layer between the source database and the Power BI analytical model.

---

# 🗂️ Data Modeling

The project uses **Power BI Data Modeling** to organize the imported data into related tables.

```text
                          Product
                             │
                             │
ShipMethod ─────────── OrderDetail ─────────── vSalesPerson
                             │
                             │
                         Territory
                             │
                           Status
                             │
                           Dates
```

A dedicated **Mymeasures** table is also used to organize DAX measures.

This relational structure allows the report to use reusable calculations across multiple visuals while responding dynamically to filters and slicers.

---

# 🔗 Relationships

Relationships were created between the tables in the Power BI Data Model to allow filtering and calculations to work across the report.

The model connects the order-detail data with supporting dimensions such as:

- Product
- ShipMethod
- Territory
- vSalesPerson
- Status
- Dates

The Data Modeling screenshot provides a visual representation of the model and its relationships.

---

# 🧮 DAX

The project uses **DAX (Data Analysis Expressions)** to create reusable measures.

A dedicated **Mymeasures** table is included in the model to organize the measures.

Measures visible in the project include:

```text
No. orders
Total Quantity
Total Freight
Total Tax
Total Subtotal
Total Due
```

These measures are used by KPI cards and visualizations and respond dynamically to report filters and slicers.

### DAX is used for:

- KPI calculations
- Order analysis
- Quantity analysis
- Freight analysis
- Tax analysis
- Subtotal analysis
- Total Due analysis
- Time-based analysis
- Territory analysis
- Product analysis
- Sales representative analysis

---

# 📅 Date & Time Analysis

The model includes a dedicated **Dates** table for time-based analysis.

The report uses date fields and date hierarchies for:

- Year
- Quarter
- Month
- Day

Time-based visuals include:

- Orders by Month
- Total Due by Year / Month
- Year filtering
- Monthly trend analysis

---

# 📦 Product Hierarchy

The **Product** table contains product hierarchy information.

```text
Product
   ↓
Product Subcategory
   ↓
Product Category
```

This hierarchy allows analysis at different levels of detail, from individual products to broader product categories.

---

# 👤 Sales Representative Analysis

The **vSalesPerson** table contains sales representative information used throughout the report.

Fields visible in the model include:

- FirstName
- LastName
- SalesQuota
- SalesYTD
- SalesLastYear
- TerritoryName
- TerritoryGroup
- City
- StateProvinceName

The dashboard uses this information for:

- Orders by SalesPersonID
- Orders by FirstName and LastName
- SalesQuota analysis
- Territory comparison
- Sales representative performance analysis

---

# 🚚 Shipping Analysis

The **ShipMethod** table is used for shipping-related analysis.

The Main dashboard includes:

- No. of Orders by Ship Method
- Ship Method distribution
- Interactive filtering

---

# 🌍 Territory Analysis

The **Territory** table is used for geographic and territory-level analysis.

The report includes:

- Orders by Territory
- Total Subtotal by Territory
- SalesQuota by Territory
- Total Due by Territory
- Territory filtering
- Geographic Map visualization
- Territory comparisons

---

# 📌 Order Status Analysis

The **Status** table provides order status information.

The Territory page includes:

- No. of Orders by StatusName

This allows the report to examine the distribution of orders according to their status.

---

# 🎛️ Interactivity & Navigation

The report was designed as an interactive Power BI experience rather than a collection of static charts.

Interactive features include:

- Slicers
- Year filters
- Territory filters
- Visual cross-filtering
- Visual interactions
- Page navigation
- Navigation buttons
- Bookmark-based navigation
- Chart / Map switching
- Interactive dashboard controls

---

# 🗺️ Map Visualization

The Territory page contains a geographic map visualization used to analyze:

- Territory activity
- Total Due
- Number of Orders
- Geographic distribution

The page also includes controls for switching between different analytical views.

---

# 📈 Report Pages

| Page | Main Purpose |
|------|--------------|
| **Main** | Executive overview of order activity, KPIs, shipping, products, months, and salespeople |
| **Product** | Product performance, product hierarchy, sales representatives, sales quota, and territory analysis |
| **Territory** | Geographic, territory, status, salesperson, product, and time-based analysis |
| **Data Modeling** | Visual representation of the Power BI relational data model |

---

# ✨ Dashboard Features

- Multi-page interactive Power BI report
- KPI Cards
- DAX Measures
- Dedicated Measures Table
- Power Query ETL
- SQL Server Database Source
- Relational Data Model
- Table Relationships
- Date Dimension
- Product Hierarchy
- Product Analysis
- Territory Analysis
- Sales Representative Analysis
- Sales Quota Analysis
- Shipping Method Analysis
- Order Status Analysis
- Monthly Analysis
- Yearly Analysis
- Geographic Map
- Slicers
- Visual Cross-filtering
- Page Navigation
- Navigation Buttons
- Bookmarks
- Chart / Map switching
- Interactive visualizations
- Business-focused dashboard design

---

# 💡 Business Questions Addressed

The dashboard was designed to help answer questions such as:

- How many orders were placed?
- What is the total quantity ordered?
- What is the total freight?
- What is the total tax?
- What is the total subtotal?
- What is the total due?
- How are orders distributed by shipping method?
- How does order volume change by month?
- Which products have the highest order activity?
- How do sales quotas compare across territories?
- Which sales representatives have higher order activity?
- How does order activity vary by territory?
- How are orders distributed by status?
- How does Total Due change over time?
- Which product subcategories contribute the most Line Total?
- How do product, salesperson, territory, shipping, and time dimensions interact?

---

# 🛠️ Tools & Technologies

## Microsoft SQL Server

- AdventureWorks 2022 Database
- SQL Server database restoration from `.bak`
- Relational database source
- Database-to-Power-BI connection

## Microsoft Power BI

- Power BI Desktop
- Data Import
- Data Modeling
- Relationships
- DAX
- Measures
- KPI Cards
- Column Charts
- Bar Charts
- Line Charts
- Pie Chart
- Map Visualization
- Slicers
- Buttons
- Bookmarks
- Page Navigation
- Visual Interactions
- Cross-filtering
- Hierarchies
- Interactive Dashboard Design

## Power Query

- Data Extraction
- Data Import
- Data Transformation
- Data Preparation
- Data Type Handling
- ETL Workflow
- Preparing source tables for the Data Model

## DAX

- Measures
- KPI calculations
- Aggregations
- Order analysis
- Quantity analysis
- Freight analysis
- Tax analysis
- Subtotal analysis
- Total Due analysis
- Time-based analysis
- Territory analysis
- Product analysis
- Sales representative analysis

---

# 📁 Repository Structure

```text
Power-BI-AdventureWorks-2022
│
├── Power-BI-Project
│   └── Power BI Adventure Work 2022 project.pbix
│
├── Screenshots
│   ├── Main Page.png
│   ├── Product Page.png
│   ├── Territory Page.png
│   └── Data Modeling.png
│
└── README.md
```

The large SQL Server database backup is intentionally not stored inside the repository.

---

# 💾 Download

## Power BI Project

The complete Power BI project is available in:

```text
Power-BI-Project/Power BI Adventure Work 2022 project.pbix
```

Open it using **Microsoft Power BI Desktop** for the complete interactive report.

## AdventureWorks 2022 Database

[Download AdventureWorks2022.bak](https://github.com/Microsoft/sql-server-samples/releases/download/adventureworks/AdventureWorks2022.bak)

---

# ⚠️ Important Notes

- The `.pbix` file should be opened using **Microsoft Power BI Desktop**.
- The original database backup is not included in the repository because of its large file size.
- The database can be downloaded from the official Microsoft source linked above.
- To reproduce the project from the original source, restore the AdventureWorks 2022 backup in SQL Server and connect/import the required data into Power BI.
- The screenshots are included so the report design and Data Model can be reviewed directly from GitHub without opening the PBIX file.

---

# 🧠 Skills Demonstrated

- SQL Server
- Database Restoration
- Database Connectivity
- Data Import
- ETL
- Power Query
- Data Transformation
- Data Preparation
- Data Modeling
- Relational Data Modeling
- Table Relationships
- DAX
- DAX Measures
- KPI Development
- Date Dimension
- Time-Based Analysis
- Product Hierarchies
- Product Analysis
- Territory Analysis
- Geographic Analysis
- Sales Representative Analysis
- Sales Quota Analysis
- Shipping Analysis
- Order Status Analysis
- Data Visualization
- Interactive Dashboard Design
- Business Intelligence
- Business Analysis
- Power BI Desktop

---

# 👨‍💻 Author

**Ahmed Essam**

📧 **Email:** [v9essam@gmail.com](mailto:v9essam@gmail.com)

💼 **LinkedIn:** [Ahmed Essam](https://www.linkedin.com/in/ahmed-essam-b6b20b28b)

🐙 **GitHub:** [Ahmedessam502](https://github.com/Ahmedessam502)

---

## ⭐ If you found this project useful, consider giving it a Star.
