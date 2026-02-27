## 💧 Water Services Infrastructure Analytics Dashboard
## 📌 Project Summary

This project analyzes water service infrastructure data to assess public water access, operational performance, and infrastructure investment impact.

Using Power BI, the solution transforms raw survey data into a structured semantic model that supports financial planning and service-level decision-making.

## 🎯 Objectives

Evaluate current water access levels across regions

Measure infrastructure investment impact

Identify service gaps (Basic vs Below Basic Access)

Support data-driven rural infrastructure planning

Provide financial allocation insights at provincial level

## 📂 Dataset

Source File:
Md_water_services_data.csv

The dataset includes:

Water source information

Visit records

Improvement types

Cost data

Geographic classifications (location, province, rural/urban)

## 🔄 ETL Process (Power Query)

Data was extracted and transformed using Power Query in Power BI.

## Data Preparation Steps

✔ Removed duplicate records

✔ Handled missing/null values using structured lookups

✔ Standardized data formats (dates, text, numeric fields)

✔ Ensured consistent categorical naming

These steps ensured high data quality prior to modeling.

## 🏗 Data Model Architecture

The model follows a Multi-Star Schema design to optimize performance and DAX reliability.

Model Structure

Fact Tables

visits

water_source

Dimension Tables

Location

Province

Service Classification

Improvement Types

Supporting lookup tables

Relationship Configuration

Cardinality: One-to-many (1:*) relationships enforced

Bridge Key: location_id maintains referential integrity

Filter Direction: Single direction (default)

Many-to-Many: Strictly avoided

## 👉 Design Principle: Maintain a clean Star Schema to prevent ambiguity and improve calculation accuracy.

##📊 DAX Transformations

Business rules were embedded directly into the semantic model using DAX.

Implemented Logic

Improvement Aggregation
Standardized multiple “Install tap” variations into:
Install public tap(s)

Rural Cost Adjustment
Created Rural_adjusted_cost column increasing infrastructure costs by 50% for rural areas to reflect operational complexity.

Queue Time Aggregation
Calculated Average_queue_time per water source across multiple visits.

Water Access Classification
Categorized sources as:

Basic Access

Below Basic Access
Based on UN service-level definitions.

## 📈 Key Performance Indicators (KPIs)

Basic Access %

No Basic Access %

Total Budget

Provincial Budget % Allocation

These KPIs link infrastructure spending directly to measurable public service outcomes.




