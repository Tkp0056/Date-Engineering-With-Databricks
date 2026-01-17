# 🚀 End-to-End Data Engineering Project: FMCG Domain (Databricks)

This repository showcases an end-to-end data engineering project focused on consolidating data from two companies within the Fast-Moving Consumer Goods (FMCG) domain. It demonstrates building a robust ETL (Extract, Transform, Load) pipeline using Databricks Free Edition, perfect for both beginners and advanced users.

## 🎯 Project Goal

The primary objective is to integrate disparate data sources from a newly acquired startup (Sports Bar) into an established retail giant's (Atlon) existing data infrastructure. This addresses data inconsistencies and enables unified reporting and analytics across both entities.

## 💡 Problem Statement

Atlon, a leading sports equipment manufacturer, operates on mature ERP-driven systems with structured data. They recently acquired Sports Bar, a fast-growing startup in athletic nutrition, whose data is highly disorganized, spread across various formats (spreadsheets, cloud drives, WhatsApp exports, APIs).

This merger led to significant data chaos:

Data Format Mismatches: Inconsistent data formats.
Reporting Misalignment: Reporting cycles didn't align.
Missing Data: Gaps in historical data.
Bottleneck: Data chaos became a bottleneck for supply chain forecasting and inventory planning.
Inconsistent Metrics: Conflicting sales numbers and metrics.
The data engineering team was tasked with building a reliable data layer to provide streamlined insights for the merged entity until a full system migration can occur.


## ✅ Success Criteria

Aggregated Analytics: Provide unified analytics from both companies in a single, reliable dashboard.
Low Learning Curve: The solution should be easy for new data professionals to learn and adopt.
Scalability: The solution must be long-term and scalable to accommodate future growth and potential delays in full system migration.

## 🏛️ Technical Architecture 

The solution leverages a Lakehouse Architecture on Databricks, utilizing the Medallion Architecture (Bronze, Silver, Gold layers) for data processing and transformation.

Atlon's Existing Infrastructure:
Atlon has an established OLTP (Online Transaction Processing) system feeding into an OLAP (Online Analytical Processing) system powered by Databricks, with existing Bronze, Silver, and Gold layers.

## Sports Bar's New Pipeline:
<img width="1408" height="768" alt="Atlikon_Sportbar_Data_Architecture" src="https://github.com/user-attachments/assets/bd9cf809-daa3-4bbd-9553-545c4c11acf2" />

For Sports Bar, the data engineering team proposed an ETL pipeline:

- **Extract**: OLTP data from Sports Bar is ingested into AWS S3 (Landing Zone).
- **Bronze Layer (Raw Data)**: Loaded into Databricks without transformations.
- **Silver Layer (Cleaned Data)**: Data cleaning, currency conversion, null handling.
- **Gold Layer (BI Ready Data)**: Aggregated and derived datasets.
- **Merge**: Sports Bar Gold merged with Atlon's Gold layer.
- **Reporting**: BI dashboards built on consolidated Gold layer.

## Data Timeline:

Historical Backfill: 5 months of historical data from Sports Bar (July-November) is processed in a batch.
Incremental Update: From November 30th onwards, daily incremental updates are processed.
