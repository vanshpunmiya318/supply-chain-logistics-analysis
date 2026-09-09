# Supply Chain & Logistics Performance Analysis

Supply chain and logistics performance analysis using Excel and Tableau, focused on delivery performance, shipment modes, freight costs, vendors, countries, shipment size, and product-level risk.

## Business Problem

Supply chain operations require a balance between delivery reliability, transportation cost, shipment size, vendor performance, and product availability.

This project analyses historical shipment data to identify where delivery delays occur and how operational factors such as shipment mode, country, shipment size, vendor, and product characteristics relate to delivery performance and freight costs.

The analysis is designed to answer eight key business questions:

- How is overall delivery performance distributed?
- Which countries show higher delivery risk?
- How do shipment modes differ in delivery performance?
- How does shipment size affect freight-cost efficiency?
- How do vendors and shipment modes interact?
- How has delivery performance changed over time?
- Which ARV brands show higher or lower delivery risk?
- Which vendors show stronger or weaker operational performance?

## Objectives

The project aims to:

- Measure overall delivery performance and identify the extent and severity of late shipments.
- Identify countries and shipment modes associated with higher delivery risk.
- Evaluate how shipment size affects freight-cost efficiency.
- Examine vendor performance and the relationship between vendors and shipment modes.
- Analyse changes in delivery performance over time.
- Identify product-level differences in delivery risk across ARV brands.
- Compare vendors across shipment volume, delivery performance, and freight-cost efficiency.
- Present the findings through interactive Tableau dashboards to support operational decision-making.

## Dataset & Source

This project uses the **Supply Chain Shipment Pricing Data** dataset, containing historical shipment-level information from the **USAID Supply Chain Management System (SCMS)**.

The dataset includes information relating to shipment dates, delivery performance, shipment mode, vendor, country, shipment size, freight cost, and product characteristics.

### Sources

**Kaggle dataset used for this project:**  
[Supply Chain Shipment Pricing Data](https://www.kaggle.com/datasets/sawandikirby/supply-chain-shipment-pricing-data)

**Original USAID dataset:**  
[USAID Supply Chain Shipment Pricing Data](https://data.usaid.gov/d/a3rc-nmf6)

The Kaggle version was used as the accessible dataset for this project, while the USAID source is provided for original-source attribution.

> **Data usage note:** The Kaggle re-upload states that the original source dataset did not include an explicit license and that the re-upload is intended for educational, non-commercial, and analytical demonstration purposes. The original data rights remain with the original data owners. :contentReference[oaicite:2]{index=2}

### Project Dataset

The original shipment-level data was refined and prepared in Excel to create the project-specific **Shipment Level** dataset used for the Tableau analysis.

The cleaned project dataset is included in this repository:

`excel/shipment level.xlsx`
