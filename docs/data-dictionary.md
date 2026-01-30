# Data Dictionary

## Overview
This document provides detailed information about the chocolate shipments dataset used in the Power BI dashboard.

## Dataset Summary
- **Total Records**: 25,076 shipments
- **Date Range**: January 1, 2023 - February 20, 2025
- **File Format**: Excel (.xlsx)
- **File Size**: ~1.3 MB

## Table Structure

### Main Dataset: Chocolate Shipments

| Column Name | Data Type | Format | Nullable | Description | Example Values |
|-------------|-----------|--------|----------|-------------|----------------|
| **ShipmentID** | Text | S00000XXX | No | Unique identifier for each shipment | S00000004, S00000009 |
| **SPID** | Text | SPXX | No | Sales Person ID - Links to sales representative | SP01, SP02, SP03 |
| **PID** | Text | PXX | No | Product ID - Links to product catalog | P14, P15, P16 |
| **GID** | Text | GX | No | Geography ID - Links to country/region | G1, G2, G3 |
| **Shipdate** | Date | YYYY-MM-DD | No | Date when shipment was dispatched | 2023-05-05, 2024-12-03 |
| **Amount** | Number | Decimal(2) | No | Revenue amount in USD | 7107.75, 8664.75 |
| **Boxes** | Integer | Whole Number | No | Number of boxes in the shipment | 285, 377, 421 |
| **Order_Status** | Text | String | No | Current status of the order | Delivered, Cancelled |

## Dimension Tables (Inferred)

### Sales Persons (SPID Reference)
Based on dashboard analysis:
- SP01: Ponnan
- SP02: Suman
- SP03: Duran
- SP04: John
- SP05: Subbarao
- SP06: Dinanath

### Geography (GID Reference)
- G1: India
- G2: USA
- G3: Australia
- G4: UK
- G5: New Zealand
- G6: Canada
- (Exact mapping may vary)

### Products (PID Reference)
Sample products identified:
- Organic Choco Syrup
- Caramel Stuffed
- Smooth Silky Salty
- 99% Dark
- Almond Choco
- 70% Dark Bites
- Peanut Butter Cubes
- Raspberry Choco
- Choco Coated Almonds
- Fruit & Nut Bars
- Orange Choco
- Milk Bars
- Mint Chip Choco
- White Choc
- Manuka Honey Choco

## Calculated Fields (DAX Measures)

### Revenue Metrics
- **Total Amount**: `SUM(Shipments[Amount])`
- **Total Boxes**: `SUM(Shipments[Boxes])`
- **Average Amount**: `AVERAGE(Shipments[Amount])`
- **Average Boxes per Shipment**: `AVERAGE(Shipments[Boxes])`

### Profit Calculations
- **Total Profit**: Calculated based on cost structure (not in raw data)
- **Profit Percentage**: `(Total Profit / Total Amount) * 100`
- Varies by product: 56.5% to 90.2%

### Time Intelligence
- **Current Year (CY)**: Shipments from current period
- **Previous Year (PY)**: Shipments from same period last year
- **YoY Growth**: `(CY - PY) / PY * 100`

### Count Metrics
- **Shipments Count**: `COUNTROWS(Shipments)`
- **Unique Products**: `DISTINCTCOUNT(Shipments[PID])`
- **Active Sales Persons**: `DISTINCTCOUNT(Shipments[SPID])`

## Data Quality Notes

### Completeness
- All fields are populated with no null values
- Date range is continuous with no gaps

### Data Validation
- ShipmentID follows consistent format (S00000XXX)
- All amounts are positive values
- Boxes are whole numbers (integers)
- Order_Status has only two values: "Delivered" or "Cancelled"

### Data Relationships
The data model uses star schema with:
- **Fact Table**: Shipments (main dataset)
- **Dimension Tables**: Sales Persons, Products, Geography, Calendar (Date)

## Business Rules

### Amount Calculation
- Amount = Unit Price × Boxes
- Includes any applicable discounts or promotions

### Profit Calculation
- Profit = Amount - Cost
- Profit Percentage varies by product type and geography

### Order Status
- **Delivered**: Successfully completed shipment
- **Cancelled**: Order cancelled before or after shipment

### Geographic Distribution
- Revenue distribution is weighted towards India (28.57%)
- Multiple currencies converted to USD for reporting

## Data Refresh Schedule
- **Frequency**: As per business requirements (recommend monthly)
- **Source**: Excel file in data folder
- **Process**: Manual refresh in Power BI Desktop or automated via Power BI Service

## Change Log

| Date | Version | Changes |
|------|---------|---------|
| 2025-02-20 | 1.0 | Initial data dictionary created |
| | | Dataset covers Jan 2023 - Feb 2025 |

