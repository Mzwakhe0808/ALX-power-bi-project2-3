## Data Extraction & Transformation (ETL)
Data was imported from Md_water_services_data.csv into Power BI. The following Power Query steps were executed to ensure a clean dataset:
•	Removing Duplicates – Identified and removed repeated records.
•	Handling Missing Values – Addressed null and incomplete entries using appropriate imputation and reference lookups.
•	Standardizing Formats – Unified data formats to ensure consistency across the dataset.

Data Modeling (Star Schema)
The model utilizes a Multi-Star Schema to ensure high performance and DAX accuracy.
Data model: Organized into 2 Fact Tables (visits & water_source) and 6 Dimension Tables.
Relationship Logic:
•	Cardinality: Enforced 1-to-many relationships; many-to-many relationships were strictly avoided.
•	Bridge Tables: Utilized location_id as a unique key to maintain referential integrity.
•	Filter Flow: Set to Single Direction by default. Bi-directional filtering was only applied where functionally necessary to prevent ambiguous paths.
👉 Aim for Star Schema
 
Figure 2: Multi-star schema model.
 
DAX Transformations (Business Logic Layer)
To translate raw operational data into strategic insights, business rules were embedded directly into, the semantic model using DAX. These transformations ensured financial projections and service impact metrics were both accurate and decision focused.
•	Aggregated Improvements – Standardized reporting by consolidating multiple “Install tap” categories into a unified group (*Install public tap(s)) to reduce categorical noise and improve readability.
•	Rural Cost Adjustment – Incorporated contextual cost modeling by introducing a Rural_adjusted_cost column, increasing infrastructure costs by 50% for rural sources to reflect logistical and operational complexity.
•	Queue Time Aggregation – Calculated Average_queue_time per source using controlled aggregation logic, enabling a good performance evaluation of shared water sources across multiple visits.
•	Water Access – Classification aligned with UN service-level definitions to determine whether each source qualifies as “Basic Access” or “Below Basic Access.” This created a measurable benchmark for project success.
•	Impact & Financial KPI Measures – Developed measures to quantify both cost and societal impact:
o	Basic Access %
o	No Basic Access %
o	Total Budget
o	Provincial Budget % Allocation
Collectively, these transformations elevate the model from descriptive reporting to decision    support analytics, directly linking infrastructure investment to measurable improvements in public water access.
 
