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

## Key Findings

### Q1. Overall Delivery Performance

Delivery performance across the 7,030 shipment-level records was predominantly positive:

- **63.29%** of shipments were delivered **On Time**.
- **25.28%** were delivered **Early**.
- **11.44%** were delivered **Late**.

Although the majority of shipments met or beat their scheduled delivery dates, **804 shipments were late**, indicating a meaningful level of delivery risk that warrants further investigation across countries, shipment modes, vendors, and product categories.

### Q2. Country Delivery Risk

Delivery risk varied considerably across countries, with several countries showing substantially higher late-delivery rates than the overall dataset.

Among countries with at least 20 shipments:

- **Burundi** recorded the highest late-delivery rate at **29.5%** (18 late shipments out of 61).
- **Congo, DRC** followed at **21.2%** (24 late shipments out of 113).
- **South Africa** recorded a **19.1%** late-delivery rate, representing **111 late shipments** across 581 shipments.
- **Mozambique** recorded a **17.8%** late-delivery rate, with **72 late shipments** across 404 shipments.
- **Nigeria**, despite having a lower late-delivery rate of **12.1%**, recorded **112 late shipments**, the highest late-shipment count among the countries shown.

The results show that country-level delivery risk should be evaluated using both **late-delivery rate and shipment volume**. Smaller countries can have high late-delivery rates, while higher-volume countries can contribute a larger number of late shipments despite having lower rates.

### Q3. Shipment Mode Performance

Delivery performance differed substantially across shipment modes:

- **Truck** had the highest late-delivery rate at **20.7%**.
- **Ocean** followed at **19.3%**.
- **Air Charter** recorded a **10.5%** late-delivery rate.
- **Air** recorded a lower late-delivery rate of **8.5%**.
- Shipments with **N/A** as the recorded mode had a **1.3%** late-delivery rate.

The results indicate that **Truck and Ocean shipments experienced the highest observed late-delivery rates**, while Air shipments showed considerably lower delay rates. These differences highlight shipment mode as an important area for further operational investigation.

### Q4. Shipment Size and Freight-Cost Efficiency

Freight-cost efficiency improved substantially as shipment size increased among shipments with resolved freight costs:

- The **smallest shipment quartile** had an average freight cost per unit of **$67.53**.
- This decreased to **$2.23** in Q2 and **$1.31** in Q3.
- The **largest shipment quartile** had the lowest average freight cost per unit at just **$0.31**.

Average total freight cost increased with shipment size, from **$2,640** for the smallest quartile to **$18,211** for the largest. However, the much larger shipment quantities resulted in substantially lower freight cost per unit.

Late-delivery rates remained relatively low across all four quartiles, ranging from **1.2% to 2.9%**, suggesting that the improvement in freight-cost efficiency with larger shipments was not accompanied by a major increase in late deliveries within this analysis scope.

Cost comparisons were limited to shipments with **available freight-cost data**, as missing freight values were not treated as zero.

### Q5. Vendor and Shipment Mode Interaction

Among the highest-volume vendors, delivery performance varied across shipment modes:

- **SCMS from RDC** operated across multiple shipment modes, with late-delivery rates ranging from **0.9% for N/A shipments** to **23.6% for Truck shipments**. Its Air and Air Charter shipments recorded rates of **14.0%** and **10.9%**, respectively.
- **Aurobindo Pharma Limited** also used multiple modes, with a **12.0%** late-delivery rate for Air shipments compared with **29.2%** for Ocean shipments.
- Several vendors operated predominantly through a single shipment mode, including **Orgenics (Air: 13.7%)**, **S. BUYS (Truck: 5.6%)**, and **CIPLA (Air: 9.7%)**.
- Other high-volume vendors recorded comparatively low late-delivery rates, including **Trinity Biotech (0.4%)**, **MYLAN (0.9%)**, **Hetero (1.2%)**, **ABBVIE (1.2%)**, and **Chembio Diagnostics (0.9%)**.

The analysis indicates that vendor delivery performance should be considered alongside **shipment mode**, rather than evaluating vendors independently of the transportation method they use.
