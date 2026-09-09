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

## Tools & Methodology

### Tools

- **Microsoft Excel** — used for data preparation, restructuring, calculated fields, data validation, and creation of the project-specific shipment-level dataset.
- **Tableau** — used for exploratory analysis, calculated fields, visualisation, dashboard development, and final presentation of the findings.

### Methodology

The project followed a structured data-preparation and analysis workflow:

1. **Data Preparation**  
   The original SCMS shipment data was reviewed and refined in Excel. Additional calculated fields were created to support delivery-performance, shipment-size, freight-cost, vendor, and product-level analysis.

2. **Shipment-Level Transformation**  
   The data was consolidated to a shipment-level dataset so that measures such as delivery performance and freight cost could be analysed consistently at the appropriate shipment level.

3. **Data Validation**  
   Key calculations and assumptions were reviewed during the analysis. Particular attention was given to freight-cost availability, shipment-level freight resolution, shipment-size effects, and product/brand classification.

4. **Exploratory Analysis**  
   The refined dataset was analysed across delivery status, country, shipment mode, shipment size, vendor, time period, and ARV brand.

5. **Visualisation & Dashboard Development**  
   The validated findings were developed into three Tableau dashboards:
   - **Supply Chain Overview**
   - **Mode & Cost Analysis**
   - **Vendor & Product Analysis**

6. **Validation & Refinement**  
   Where initial analytical approaches produced misleading or incomplete comparisons, they were reviewed and refined before the final findings and dashboards were produced.

## Project Dataset

The original shipment-level data was refined and prepared in Excel to create the project-specific **Shipment Level** dataset used for the Tableau analysis.

The cleaned project dataset is included in this repository:

`excel/shipment level.xlsx`

For dataset details, preparation methodology, sources, citation, and data-usage information, see [`DATASET.md`](DATASET.md).
