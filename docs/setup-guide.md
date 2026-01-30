# Setup Guide

## Table of Contents
1. [System Requirements](#system-requirements)
2. [Installation](#installation)
3. [Data Source Setup](#data-source-setup)
4. [Dashboard Configuration](#dashboard-configuration)
5. [Publishing to Power BI Service](#publishing-to-power-bi-service)
6. [Troubleshooting](#troubleshooting)

---

## System Requirements

### Minimum Requirements
- **Operating System**: Windows 10 (64-bit) or later
- **RAM**: 4 GB minimum (8 GB recommended)
- **Disk Space**: 500 MB free space
- **Display**: 1440 x 900 resolution minimum

### Software Requirements
- **Power BI Desktop**: Version 2.120 or later (Download from [Microsoft Store](https://aka.ms/pbidesktop))
- **Microsoft Excel**: 2016 or later (for data source)
- **.NET Framework**: 4.7.2 or later

---

## Installation

### Step 1: Install Power BI Desktop

1. Download Power BI Desktop from one of these sources:
   - Microsoft Store (Recommended)
   - [Direct Download](https://aka.ms/pbidesktop)
   
2. Run the installer and follow the on-screen instructions

3. Launch Power BI Desktop and sign in with your Microsoft account

### Step 2: Clone or Download the Repository

**Option A: Using Git**
```bash
git clone https://github.com/yourusername/chocolate-shipments-dashboard.git
cd chocolate-shipments-dashboard
```

**Option B: Direct Download**
1. Go to the GitHub repository
2. Click the green "Code" button
3. Select "Download ZIP"
4. Extract the ZIP file to your desired location

---

## Data Source Setup

### Step 1: Locate the Data Files

Ensure the following files are in the `data` folder:
```
data/
└── sample-chocolate-shipments-data-all-Apr-2025.xlsx
```

### Step 2: Open the Power BI File

1. Navigate to the `dashboard` folder
2. Double-click `chocolate_shipments.pbix`
3. Power BI Desktop will open the file

### Step 3: Update Data Source Connection

If you moved the files to a different location:

1. In Power BI Desktop, click **Transform Data** > **Data source settings**
2. Select the Excel data source
3. Click **Change Source...**
4. Browse to the new location of your Excel file
5. Click **OK**

### Step 4: Refresh the Data

1. Click the **Refresh** button in the Home ribbon
2. Wait for the data to load (should take 10-30 seconds)
3. Verify all visuals are displaying correctly

---

## Dashboard Configuration

### Understanding the Dashboard Structure

The dashboard contains multiple pages:

1. **Main Overview**: Key metrics and KPIs
2. **Sales Analysis**: Sales person performance
3. **Product Performance**: Product-wise breakdown
4. **Geographic Analysis**: Regional distribution
5. **Trend Analysis**: Time-series comparisons

### Customizing the Dashboard

#### Changing Date Filters

1. Select the date slicer on the main page
2. Adjust the date range as needed
3. All visuals will update automatically

#### Modifying Color Themes

1. Go to **View** > **Themes**
2. Select a pre-built theme or create custom
3. Colors will apply across all pages

#### Adding New Visuals

1. Click **Home** > **Get Data** for additional sources
2. Drag fields to the canvas to create new visuals
3. Use **Format** pane to customize appearance

---

## Publishing to Power BI Service

### Prerequisites
- Power BI Pro or Premium license
- Access to a Power BI workspace

### Publishing Steps

1. **Save Your Work**
   - Click **File** > **Save**

2. **Publish to Service**
   - Click **Home** > **Publish**
   - Select your workspace
   - Click **Select**

3. **Configure Data Refresh** (Optional)
   - Open the dataset in Power BI Service
   - Go to **Settings** > **Scheduled refresh**
   - Configure refresh schedule and credentials

4. **Share the Dashboard**
   - Open the published report
   - Click **Share** button
   - Enter email addresses of recipients
   - Set appropriate permissions

---

## Troubleshooting

### Common Issues and Solutions

#### Issue 1: "Cannot connect to data source"

**Solution:**
- Verify the Excel file path is correct
- Check that the file is not open in Excel
- Ensure you have read permissions for the file
- Update the data source path in Power BI

#### Issue 2: "Visuals not displaying data"

**Solution:**
- Click Refresh to reload data
- Check filters aren't excluding all data
- Verify relationships in Model view
- Clear cache: File > Options > Data Load > Clear Cache

#### Issue 3: "Slow performance"

**Solution:**
- Close other applications
- Reduce visual complexity
- Optimize DAX measures
- Consider aggregating large datasets
- Upgrade to DirectQuery if using Import mode

#### Issue 4: "Publishing fails"

**Solution:**
- Check your internet connection
- Verify you have a Power BI Pro license
- Ensure you have publish permissions to the workspace
- File size should be under 1 GB for free accounts

#### Issue 5: "Date filters not working"

**Solution:**
- Verify the date column is marked as Date type
- Check the relationship with Date table
- Ensure date format is consistent (YYYY-MM-DD)

### Data Validation Checklist

Before publishing, verify:
- [ ] All data sources connect successfully
- [ ] All visuals display expected data
- [ ] Filters work correctly across pages
- [ ] Drill-through functionality works
- [ ] Tooltips display relevant information
- [ ] Export to Excel/PDF functions properly
- [ ] Mobile layout is configured (if needed)

---

## Advanced Configuration

### Setting Up Row-Level Security (RLS)

If you need to restrict data access:

1. Go to **Modeling** tab
2. Click **Manage Roles**
3. Create new role (e.g., "Sales Person")
4. Add DAX filter: `[SPID] = USERNAME()`
5. Test using **View as Role**

### Creating Custom Measures

Example: Average Profit Margin
```DAX
Avg Profit Margin = 
AVERAGEX(
    VALUES(Shipments[PID]),
    [Total Profit] / [Total Amount]
)
```

### Optimizing Performance

1. **Use Query Folding**
   - Check in Power Query Editor
   - View Native Query when possible

2. **Reduce Visual Count**
   - Limit to 30-40 visuals per page

3. **Optimize DAX**
   - Use CALCULATE instead of FILTER where possible
   - Avoid complex calculated columns

4. **Enable Incremental Refresh**
   - For large datasets (>1M rows)
   - Configure in dataset settings

---

## Additional Resources

### Power BI Documentation
- [Power BI Desktop Documentation](https://docs.microsoft.com/power-bi/)
- [DAX Function Reference](https://dax.guide/)
- [Power BI Community](https://community.powerbi.com/)

### Video Tutorials
- [Power BI YouTube Channel](https://youtube.com/powerbi)
- [Guy in a Cube](https://guyinacube.com/)

### Best Practices
- [Power BI Guidance](https://docs.microsoft.com/power-bi/guidance/)
- [Dashboard Design Tips](https://docs.microsoft.com/power-bi/create-reports/service-dashboards-design-tips)

---

## Getting Help

If you encounter issues not covered in this guide:

1. **Check GitHub Issues**: [Project Issues Page](https://github.com/sanjaymo/Chocolate-Shipments-Analytics-Dashboard/issues)
2. **Create New Issue**: Include error messages and screenshots
3. **Contact Maintainer**: Email your.email@example.com

---

## Version History

| Version | Date | Changes |
|---------|------|---------|
| 1.0.0 | 2025-02 | Initial setup guide created |

---

