# 🍫 Chocolate Shipments Analytics Dashboard

A comprehensive Power BI dashboard analyzing chocolate shipments data across multiple geographies, products, and sales personnel from January 2023 to February 2025.

![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![Excel](https://img.shields.io/badge/Excel-217346?style=for-the-badge&logo=microsoft-excel&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-blue.svg?style=for-the-badge)

## 📊 Dashboard Overview

This Power BI dashboard provides deep insights into chocolate shipment operations, tracking over **24,000 shipments** across **7 countries** with a total revenue of **$137M** and **9M boxes** shipped.

### Key Metrics Tracked
- **Total Revenue**: $137M
- **Total Boxes Shipped**: 9M
- **Total Shipments**: 24K
- **Total Profit**: $79M
- **Profit Margin**: 57.4%

## 🎯 Features

### 1. **Year-over-Year Comparison**
- Current Year (CY) vs Previous Year (PY) analysis
- Monthly trend visualization for amount and boxes
- Period: April 2024 to January 2025

### 2. **Geographic Distribution**
- **India**: $39M (28.57%)
- **USA**: $29M (21.23%)
- **Australia**: $29M (21.06%)
- **UK**: $20M (14.82%)
- **New Zealand**: $10M (7.25%)
- **Canada**: $10M (7.07%)

### 3. **Top Performers**
#### Top 6 Sales Persons:
1. **Ponnan** - $11.3M | 697.5K boxes | 58.8% profit
2. **Suman** - $10.2M | 636.0K boxes | 57.8% profit
3. **Duran** - $8.9M | 543.3K boxes | 57.9% profit
4. **John** - $8.1M | 509.2K boxes | 57.0% profit
5. **Subbarao** - $7.9M | 497.5K boxes | 56.5% profit
6. **Dinanath** - $7.8M | 482.7K boxes | 57.2% profit

#### Top 6 Products by Revenue:
1. Organic Choco Syrup - $12M
2. Caramel Stuffed - $10M
3. Smooth Silky Salty - $8M
4. 99% Dark - $8M
5. Almond Choco - $7M
6. 70% Dark - $7M

### 4. **Product Performance**
All products analyzed with profit percentage metrics:
- **Best Profit Margin**: Peanut Butter Cubes (90.2%)
- **Strong Performers**: Raspberry Choco (84.7%), Choco Coated Almonds (82.6%)

### 5. **Shipment Distribution Analysis**
- Distribution visualization by boxes count
- Identifies shipment patterns and frequency

## 📁 Project Structure

```
chocolate-shipments-dashboard/
│
├── README.md
├── LICENSE
├── .gitignore
│
├── data/
│   └── sample-chocolate-shipments-data-all-Apr-2025.xlsx
│
├── reports/
│   └── Final_powerbiProj.pdf
│
├── dashboard/
│   └── chocolate_shipments.pbix
│
└── docs/
    ├── data-dictionary.md
    └── setup-guide.md
```

## 🚀 Getting Started

### Prerequisites
- **Power BI Desktop** (Latest version recommended)
- **Microsoft Excel** (for data source)
- **Windows 10 or later** (for Power BI Desktop)

### Installation Steps

1. **Clone the repository**
   ```bash
   git clone https://github.com/Sanjaymo/Chocolate-Shipments-Analytics-Dashboard.git
   cd Chocolate-Shipments-Analytics-Dashboard
   ```

2. **Open the Power BI file**
   - Navigate to the `dashboard` folder
   - Open `chocolate_shipments.pbix` with Power BI Desktop

3. **Update Data Source** (if needed)
   - Go to `Transform Data` > `Data Source Settings`
   - Update the path to point to your local `data` folder

4. **Refresh the data**
   - Click `Refresh` in the Home ribbon to update all visuals

## 📊 Data Schema

The dataset contains **25,076 records** with the following structure:

| Column Name | Data Type | Description |
|-------------|-----------|-------------|
| ShipmentID | Text | Unique shipment identifier |
| SPID | Text | Sales Person ID |
| PID | Text | Product ID |
| GID | Text | Geography ID |
| Shipdate | Date | Date of shipment |
| Amount | Number | Revenue amount in USD |
| Boxes | Number | Number of boxes shipped |
| Order_Status | Text | Status (Delivered/Cancelled) |

**Date Range**: January 1, 2023 to February 20, 2025

## 🔍 Key Insights

1. **Geographic Performance**: India leads with 28.57% of total revenue, followed by USA and Australia
2. **Sales Excellence**: Top 6 sales persons contribute significantly with profit margins above 56%
3. **Product Mix**: Premium products (Peanut Butter Cubes) show highest profit margins at 90.2%
4. **Consistent Growth**: Year-over-year analysis shows steady growth trajectory
5. **Operational Efficiency**: Overall profit margin of 57.4% indicates strong operational health

## 🛠️ Technologies Used

- **Power BI Desktop**: Dashboard creation and visualization
- **Power Query**: Data transformation and cleaning
- **DAX (Data Analysis Expressions)**: Custom calculations and measures
- **Excel**: Data source management

## 📈 Dashboard Pages

1. **Overview Dashboard**: Main landing page with key metrics
2. **Sales Performance**: Detailed sales person analysis
3. **Product Analytics**: Product-wise performance breakdown
4. **Geographic Analysis**: Region-wise revenue distribution
5. **Trend Analysis**: Time-series analysis CY vs PY

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request. For major changes, please open an issue first to discuss what you would like to change.

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👤 Author

**Your Name**
- GitHub: [Sanjaymo](https://github.com/Sanjaymo)
- LinkedIn: [Sanjay Choudhari](https://www.linkedin.com/in/sanjaychoudhari09)

## 🙏 Acknowledgments

- Data source: Sample chocolate shipments dataset
- Inspiration: Business intelligence best practices
- Power BI community for visualization ideas

## 📞 Contact

For any questions or feedback, please reach out via:
- Email: sanjaychoudhari288@gmail.com
- Issues: [GitHub Issues](https://github.com/Sanjaymo/chocolate-shipments-dashboard/issues)

---

⭐️ If you found this project helpful, please consider giving it a star!

