# E-Commerce Sales Performance Dashboard

## Executive overview
<img width="1151" height="646" alt="لقطة شاشة 2025-11-01 150707" src="https://github.com/user-attachments/assets/199e478b-73e7-4337-b032-601e66062779" />
## Product performance
<img width="1150" height="643" alt="لقطة شاشة 2025-11-01 150722" src="https://github.com/user-attachments/assets/ba57b23d-301d-4e90-b423-8a876d808d6d" />
## Time Trends
<img width="1156" height="645" alt="لقطة شاشة 2025-11-01 150735" src="https://github.com/user-attachments/assets/e2f541bb-8565-4e9e-a1af-5b828766e6af" />

A comprehensive Power BI analytics solution for tracking and analyzing e-commerce sales performance across multiple dimensions including products, customers, geographic regions, and time periods.

---

## 📋 Table of Contents

- [Overview](#-overview)
- [Key Features](#-key-features)
- [Dashboard Preview](#-dashboard-preview)
- [Data Model](#-data-model)
- [Metrics & KPIs](#-metrics--kpis)
- [Visualizations](#-visualizations)
- [Installation](#-installation)
- [Usage](#-usage)
- [Technical Stack](#-technical-stack)
- [Contributing](#-contributing)
- [License](#-license)

---

## 🎯 Overview

This interactive dashboard provides real-time insights into e-commerce operations, enabling data-driven decision-making through visual analytics and key performance indicators (KPIs). The solution is built on a robust star schema data model and offers multi-dimensional analysis capabilities.

### Business Impact
- **Revenue Tracking**: Monitor $105.40M in total sales
- **Customer Insights**: Analyze 9,191 distinct customers
- **Product Analytics**: Track 264 distinct items
- **Volume Analysis**: Measure 6M units sold

---

## ✨ Key Features

### 📊 Multi-Dimensional Analysis
- **Temporal Analysis**: Monthly, quarterly, and yearly trends (2014-2021)
- **Product Performance**: Top products, category breakdown, profitability
- **Customer Segmentation**: Sales by customer type and purchase patterns
- **Geographic Intelligence**: Interactive map with district-level sales
- **Supplier Analytics**: Multi-supplier comparison and performance tracking

### 🎛️ Interactive Controls
- Dynamic month and year filters
- Supplier selection slicers
- Cross-filtering across all visualizations
- Drill-down capabilities from year to day level

### 📈 Real-Time Insights
- Live KPI monitoring
- Trend identification
- Performance benchmarking
- Anomaly detection

---

## 🖼️ Dashboard Preview

### Main Dashboard
- KPI summary cards with total sales, quantity, and customer metrics
- Monthly revenue trend line chart
- Customer and unit type stacked bar chart
- Geographic heat map with district-level sales clustering

### Product Analysis View
- Top 10 products by revenue (horizontal bar chart)
- Supplier performance matrix
- Item-level sales breakdown

### Quarterly Trends View
- Area chart showing quarterly sales progression
- Quantity-based performance metrics
- Time-series comparison tools

---

## 🗄️ Data Model

### Star Schema Architecture

```
fact_table (Center)
    ├── customer_key → customer_dim
    ├── item_key → item_dim
    ├── store_key → store_dim
    ├── time_key → time_dim
    └── payment_key → Trans_dim
```

### Dimension Tables

#### `item_dim`
- item_key (PK)
- item_name
- unit
- unit_price
- supplier
- man_country

#### `customer_dim`
- customer_key (PK)
- contactUte
- name
- nid

#### `store_dim`
- store_key (PK)
- district
- division
- upazila

#### `time_dim`
- time_key (PK)
- date
- day
- month
- quarter
- week
- year

#### `Trans_dim`
- payment_key (PK)
- bank_name
- trans_type

#### `fact_table`
- customer_key (FK)
- item_key (FK)
- payment_key (FK)
- store_key (FK)
- time_key (FK)
- quantity
- total_price
- unit
- unit_price

---

## 📊 Metrics & KPIs

### Primary KPIs
| Metric | Value | Description |
|--------|-------|-------------|
| Total Sales | $105.40M | Sum of all transaction values |
| Total Quantity | 6M | Total units sold |
| Average Unit Price | $17.56 | Mean price per unit |
| Distinct Items | 264 | Unique products in catalog |
| Distinct Customers | 9,191 | Unique customer count |

### Secondary Metrics
- Sales by product category (bags, bars, bottles, cans)
- Revenue by supplier
- Geographic distribution by district
- Quarterly growth rates
- Customer lifetime value

---

## 📈 Visualizations

### Chart Types Used

1. **Line Chart**: Monthly sales trends with volatility analysis
2. **Stacked Bar Chart**: 100% composition by customer and unit type
3. **Horizontal Bar Chart**: Product rankings by total sales
4. **Area Chart**: Quarterly sales progression
5. **Map Visualization**: Geographic clustering using Azure Maps
6. **Matrix Table**: Supplier performance comparison
7. **KPI Cards**: Key metrics with visual indicators

### Color Scheme
- Navy blue for primary data series
- Multi-color palette for categorical breakdowns (bags, bars, bottles, cans)
- Red gradient for geographic heat maps
- Professional dark theme for overall interface

---

## 🚀 Installation

### Prerequisites
- Microsoft Power BI Desktop (latest version)
- Windows 10/11 or compatible OS
- Minimum 4GB RAM (8GB recommended)

### Setup Steps



2. **Open Power BI File**
   - Launch Power BI Desktop
   - Open `E-Commerce_Dashboard.pbix`

3. **Configure Data Source**
   - Navigate to Home → Transform Data
   - Update data source connections
   - Apply credentials if required

4. **Refresh Data**
   - Click Home → Refresh
   - Wait for data load completion

---

## 💡 Usage

### Getting Started

1. **Select Time Period**
   - Use Month name and Year name slicers on the right panel
   - Choose single or multiple periods for comparison

2. **Filter by Supplier**
   - Check/uncheck suppliers in the Supplier name filter
   - View filtered results across all visuals

3. **Explore Geographic Data**
   - Hover over map bubbles for district details
   - Click to drill into specific regions

4. **Analyze Products**
   - Navigate to product view (Image 2)
   - Review top performers and supplier metrics

5. **Track Trends**
   - Use quarterly view (Image 3) for time-series analysis
   - Identify seasonal patterns and growth opportunities

### Best Practices

- **Regular Refresh**: Schedule automatic data refresh for up-to-date insights
- **Bookmark Views**: Save custom filter combinations for quick access
- **Export Data**: Use "Export data" feature for detailed offline analysis
- **Mobile Layout**: Configure mobile view for on-the-go access

---

## 🛠️ Technical Stack

| Component | Technology |
|-----------|-----------|
| BI Platform | Microsoft Power BI Desktop |
| Data Modeling | Star Schema |
| Visualization | Power BI Visuals |
| Mapping Service | Microsoft Azure Maps |
| Data Processing | Power Query (M Language) |
| Calculations | DAX (Data Analysis Expressions) |

### Key DAX Measures

```dax
Total Sales = SUM(fact_table[total_price])
Total Quantity = SUM(fact_table[quantity])
Average Unit Price = AVERAGE(fact_table[unit_price])
Distinct Customers = DISTINCTCOUNT(fact_table[customer_key])
```

---

## 🔧 Customization

### Adding New Measures
1. Open Power BI Desktop
2. Navigate to Modeling → New Measure
3. Write DAX formula
4. Add to appropriate visual

### Modifying Visuals
1. Select visual on canvas
2. Adjust properties in Visualizations pane
3. Customize colors, labels, and formatting

### Extending Data Model
1. Go to Model view
2. Add new tables via Power Query
3. Create relationships with fact table
4. Update visuals to include new dimensions

---

## 📁 Project Structure

```
ecommerce-dashboard/
│
├── E-Commerce_Dashboard.pbix      # Main Power BI file
├── data/
│   ├── fact_table.csv              # Sales transactions
│   ├── item_dim.csv                # Product master
│   ├── customer_dim.csv            # Customer master
│   ├── store_dim.csv               # Store locations
│   ├── time_dim.csv                # Date dimension
│   └── Trans_dim.csv               # Transaction types
│
├── images/
│   ├── dashboard_main.png
│   ├── product_analysis.png
│   └── data_model.png
│
│
└── README.md                       # This file
```

---

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

### Contribution Guidelines
- Follow existing code style and naming conventions
- Document all new measures and calculations
- Test thoroughly before submitting PR
- Update README if adding new features

---

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 👥 Authors

marwan eslam ouda





## 🗺️ Roadmap

- [ ] Add predictive analytics for sales forecasting
- [ ] Implement customer lifetime value analysis
- [ ] Create mobile-optimized version
- [ ] Add real-time data streaming
- [ ] Integrate with external APIs
- [ ] Develop automated alerting system

---

## 📚 Additional Resources

- [Power BI Documentation](https://docs.microsoft.com/en-us/power-bi/)
- [DAX Reference](https://dax.guide/)
- [Power Query M Reference](https://docs.microsoft.com/en-us/powerquery-m/)


</div>
