# pizza-sales-medallion-architecture

Pizza Sales Lakehouse — Medallion Architecture, SCD2 & SCD3

This project demonstrates a complete data engineering pipeline for pizza sales built using the principles of Medallion Architecture (Bronze -> Silver -> Gold) along with implementations of Slowly Changing Dimensions (SCD2 and SCD3).
The goal is to deliver a modern Lakehouse-style analytics platform that supports clean data processing, historical versioning, and business-ready analytical tables.

Medallion Architecture
Bronze Layer — Raw Data

Raw data is ingested directly from source files CSV with minimal preprocessing.

The structure reflects the original input without business transformations.

Metadata such as ingestion timestamps may be added.

This layer serves as the single source of truth for downstream transformations.

Silver Layer — Clean & Enriched Data

Data is cleaned, standardized, deduplicated, and enriched with additional attributes.

Relationships between tables are established, and schemas are harmonized.

SCD2 and SCD3 logic is applied in this layer to maintain historical and partially historical dimensions.

Silver tables act as a structured analytical model ready for business logic.

Gold Layer — Business-Ready Data

The final layer exposes fully curated datasets optimized for analytics and reporting.

Aggregations, KPIs, and business metrics are computed.

Gold tables are refined for high-performance consumption in BI tools (Power BI, Tableau, Looker).

Slowly Changing Dimensions
SCD2 — Full Historical Versioning

This project uses the SCD2 pattern to:

preserve the full history of dimensional attribute changes,

create new rows for every change while closing old versions,

track validity periods with valid_from, valid_to, and is_current flags.

This ensures complete historical traceability and point-in-time accuracy.

SCD3 — Partial Historical Tracking

Selected Silver and Gold tables implement SCD3 to:

store both the current and previous value of selected attributes,

enable quick “old” comparisons,

Project Objectives

Build a fully functional end-to-end data pipeline aligned with modern Lakehouse practices.



Demonstrate raw → refined → business data flows using the Medallion Architecture.

Implement robust historical tracking via SCD2 and SCD3.

Deliver business-ready datasets suitable for reporting, dashboards, and advanced analytics.
<img width="1193" height="612" alt="job_graph" src="https://github.com/user-attachments/assets/4a647215-3845-467f-9a5c-61ea8c55cf81" />
<img width="573" height="452" alt="scd2" src="https://github.com/user-attachments/assets/e8fadb18-d7db-4459-9cfd-a8e6db1bb7e1" />
<img width="1096" height="510" alt="scd3" src="https://github.com/user-attachments/assets/b7fc1539-b0a0-4e7a-b370-53a7ef8127a3" />
