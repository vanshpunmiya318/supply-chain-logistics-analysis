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
- Shipments with **N/A** as the recorded mode had a **1.3%** late-delivery rate, but this category was treated as a **data-quality flag rather than a meaningful shipment mode**.

The results indicate that **Truck and Ocean shipments experienced the highest observed late-delivery rates**, while Air shipments showed considerably lower delay rates. The N/A category was excluded from meaningful mode-performance interpretation because it represents missing or unspecified shipment-mode information.

### Q4. Shipment Size and Freight-Cost Efficiency

Freight-cost efficiency improved substantially as shipment size increased, among shipments with resolved freight costs (n = 6,198):

* The **smallest shipment quartile** had an average freight cost per unit of **$83.81**.
* This fell to **$3.01** in Q2 and **$1.00** in Q3.
* The **largest shipment quartile** had the lowest average freight cost per unit at **$0.28**.

Average total freight cost increased with shipment size, from **$2,758** for the smallest quartile to **$20,658** for the largest. However, the much larger shipment quantities more than offset the increase in total freight cost, resulting in substantially lower freight cost per unit for larger shipments.

Late-delivery rates also increased with shipment size, from **5.1%** in the smallest quartile to **17.9%** in the largest. This indicates a trade-off within this analysis: larger shipments were substantially more freight-efficient per unit but had higher observed late-delivery rates.

Cost comparisons were limited to shipments with **available freight-cost data**, consistent with the approach used in Q3. Missing freight values were not treated as zero.

**Validation note:** The shipment-size analysis was independently checked after an initial result produced an incorrect shipment population. The issue was traced to broken freight-cost references in the underlying Excel workbook, which caused some records to be excluded from the freight-resolved analysis. The source formulas were restored, the Tableau data source was reconnected, and the final results were re-verified using the corrected population of **6,198 freight-resolved shipments**.

### Q5. Vendor and Shipment Mode Interaction

Among the highest-volume vendors, delivery performance varied across shipment modes:

- **SCMS from RDC** operated across multiple shipment modes, with late-delivery rates ranging from **0.9% for N/A shipments** to **23.6% for Truck shipments**. Its Air and Air Charter shipments recorded rates of **14.0%** and **10.9%**, respectively.
- **Aurobindo Pharma Limited** also used multiple modes, with a **12.0%** late-delivery rate for Air shipments compared with **29.2%** for Ocean shipments.
- Several vendors operated predominantly through a single shipment mode, including **Orgenics (Air: 13.7%)**, **S. BUYS (Truck: 5.6%)**, and **CIPLA (Air: 9.7%)**.
- Other high-volume vendors recorded comparatively low late-delivery rates, including **Trinity Biotech (0.4%)**, **MYLAN (0.9%)**, **Hetero (1.2%)**, **ABBVIE (1.2%)**, and **Chembio Diagnostics (0.9%)**.

The analysis indicates that vendor delivery performance should be considered alongside **shipment mode**, rather than evaluating vendors independently of the transportation method they use.

### Q6. Delivery Performance Over Time

Delivery performance varied considerably across the 2006–2015 period, with a sharp increase in late-delivery rates from 2010 onwards:

- The late-delivery rate increased from **3.4% in 2009** to **13.5% in 2010**.
- **2011 recorded the highest late-delivery rate at 22.0%**, making it the main anomaly in the period.
- The rate then fell to **6.9% in 2012**, before remaining elevated at **17.1% in 2013** and **17.6% in 2014**.
- Investigation of the 2011 peak found that **SCMS from RDC accounted for 123 of the 181 late shipments**, representing **68% of all late shipments that year**. Across its 328 shipments in 2011, the vendor recorded a **37.5% late-delivery rate**.
- SCMS from RDC's elevated late-delivery rate was observed across the main shipment modes it used: **Air (34.9%)**, **Air Charter (37.5%)**, and **Truck (39.9%)**, indicating that the 2011 issue was not isolated to a single transportation mode.
- The vendor's 2011 late shipments were also spread across multiple countries, including **Nigeria, Zambia, Uganda, Zimbabwe, and Côte d'Ivoire**.
- A further country-level investigation found that **Uganda recorded 16 late shipments out of 41 in 2011 (39.0%)**, with all 16 of those late shipments associated with SCMS from RDC.

The analysis therefore identified **2011 as the peak period of delivery disruption**, with SCMS from RDC representing the largest identified contributor to the year's late shipments. South Africa also recorded an elevated 2011 late-delivery rate of **26.3% (50 of 190 shipments)**, representing a separate contributor not explained by SCMS from RDC.

**Note:** The 2006 rate of 0.0% was based on only **52 shipments** and should be interpreted cautiously.

### Q7. Within-ARV Brand Segmentation

Among ARV shipments with a single recorded brand, delivery performance varied across brands, although the majority of shipments were concentrated in the Generic category:

- The analysis identified **5,472 ARV shipments** in total.
- **197 shipments (3.6%)** contained multiple brand values and were excluded from the brand-level comparison, leaving **5,275 single-brand shipments**.
- Applying a minimum reporting threshold of **20 shipments per brand** resulted in **12 brands** being included in the comparison.
- **Generic** accounted for **4,480 shipments** and had a late-delivery rate of **14.7%**, making it by far the largest ARV brand category.
- Other qualifying brands included **Aluvia (177 shipments, 9.0% late)**, **Kaletra (142, 2.8%)**, **Norvir (109, 0.0%)**, **Videx (56, 1.7%)**, **Truvada (54, 0.0%)**, **Stocrin/Sustiva (31, 0.0%)**, **Viread (26, 3.0%)**, **Prezista (24, 0.0%)**, **Invirase (21, 0.0%)**, **Isentress (21, 0.0%)**, and **Ziagen (20, 4.3%)**.
- Several brands recorded a **0.0% late-delivery rate**, meaning that no late shipments were observed for those brands in the analysed dataset. These results should not be interpreted as evidence of perfect or consistently superior reliability, particularly for brands represented by relatively small shipment volumes.

The analysis used **Brand** as the segmentation field after testing several alternatives. Molecule/Test Type, Manufacturing Site, and Dosage Form were rejected because they contained substantially more mixed-value shipments, while Brand had the lowest proportion of mixed records at **3.6%**.

The results provide a more detailed view of delivery performance within the ARV product group while applying a minimum shipment threshold to avoid comparisons based on very small shipment volumes.

### Q8. Vendor Operational Comparison

The final vendor comparison combines shipment volume, late-delivery rate, and weighted freight cost per unit to provide a broader view of operational performance across the 10 vendors with at least 100 shipments:

- **SCMS from RDC** handled the highest shipment volume with **3,440 shipments**, recording a **16.2% late-delivery rate** and a weighted freight cost per unit of **$0.259**.
- **Aurobindo Pharma Limited** handled **541 shipments**, with a **17.0% late-delivery rate** and a weighted freight cost per unit of **$0.291**.
- **Orgenics, Ltd** recorded **667 shipments** and a **13.6% late-delivery rate**, but its weighted freight cost per unit was substantially higher at **$5.157**.
- **Trinity Biotech, Plc** recorded a **0.4% late-delivery rate** across **285 shipments**, with a weighted freight cost per unit of **$3.643**.
- **S. Buys Wholesaler** recorded **194 shipments**, a **4.6% late-delivery rate**, and the lowest weighted freight cost per unit in the comparison at **$0.011**.
- The remaining vendors showed different combinations of delivery reliability and freight cost, demonstrating that vendor performance cannot be described using a single operational measure.

The comparison uses a **minimum reporting threshold of 100 shipments per vendor** to focus on vendors with a meaningful level of shipment activity. This threshold is a reporting criterion rather than a measure of statistical significance. Freight cost per unit was calculated using a **volume-weighted approach**, based on total freight cost divided by total shipment quantity, rather than averaging individual shipment-level cost-per-unit values. Freight-cost metrics were calculated using shipments with **resolved freight-cost data**; missing freight values were not treated as zero.

The results highlight the importance of considering **shipment volume, delivery reliability, and freight efficiency together** when assessing vendor operations. A vendor with a lower freight cost per unit may still have a higher late-delivery rate, while a vendor with a lower late-delivery rate may operate at a substantially higher freight cost per unit.

## Business Recommendations

Based on the findings across the eight analyses, the following operational actions could be considered:

1. **Review high-risk shipment modes**  
   Truck and Ocean shipments recorded the highest observed late-delivery rates. These modes should be reviewed further to identify operational bottlenecks, route-level issues, or other factors contributing to delays.

2. **Prioritise high-volume countries with significant late-shipment counts**  
   Country-level risk should be assessed using both late-delivery rates and shipment volumes. High-volume countries such as Nigeria can generate a substantial number of late shipments even when their percentage rate is lower than that of smaller countries.

3. **Investigate recurring vendor and country disruption patterns**  
   The 2011 analysis identified SCMS from RDC as the largest identified contributor to late shipments that year, while South Africa represented a separate contributor. Similar vendor- and country-level patterns should be monitored when investigating future increases in delivery delays.

4. **Consider shipment consolidation where operationally feasible**  
   The shipment-size analysis across the full dataset showed substantially lower freight cost per unit for larger shipments, while larger shipments also had higher observed late-delivery rates. Shipment consolidation could therefore be considered where practical, but alongside appropriate delivery-risk controls rather than as an unconditional cost-saving measure.

5. **Evaluate vendors using multiple operational measures**  
   Vendor performance should be assessed using shipment volume, late-delivery rate, and freight-cost efficiency together. The analysis shows that a lower freight cost per unit does not necessarily correspond to a lower late-delivery rate, making single-metric vendor evaluation potentially misleading.

6. **Assess vendor concentration and shipment-mode redundancy**  
   The analysis identified substantial concentration of shipment activity among a small number of vendors, while most of the highest-volume vendors operated through a single shipment mode. This suggests that vendor concentration and limited mode redundancy should be considered when assessing operational resilience and potential disruption exposure.

## Dashboards

The analysis was presented through three interactive Tableau dashboards, each focused on a different operational perspective.

### 1. Supply Chain Overview

Provides an overall view of delivery performance, including delivery-status distribution, delivery variance, late-shipment severity, country-level risk, and delivery trends over time.

### 2. Mode & Cost Analysis

Examines delivery performance across shipment modes and the relationship between shipment size and freight-cost efficiency. Freight-cost comparisons are based on shipments with resolved freight-cost data.

### 3. Vendor & Product Analysis

Combines vendor-level operational comparison, vendor-by-shipment-mode performance, and ARV brand-level delivery risk to provide a more detailed view of vendor and product performance.

The dashboards were developed in Tableau using the validated shipment-level dataset prepared in Excel.

## Limitations

The analysis has several limitations that should be considered when interpreting the results:

- **Freight-cost availability:** Freight-cost analysis was limited to the **6,198 of 7,030 shipments (88.2%)** with resolved freight-cost data. The remaining 832 shipments were excluded from freight-cost calculations because their freight costs were either bundled into commodity costs or invoiced separately. Missing freight values were not treated as zero.

- **Freight-cost derivation:** For shipments where multiple line items shared a single recorded freight charge, freight cost was resolved once at the shipment (ASN) level rather than duplicated across line items. The underlying references were validated to ensure that cross-referenced freight values resolved to the correct shipment. As a result, some freight-cost figures represent a shipment-level reconstruction rather than a directly itemized cost recorded independently for each line item.

- **Shipment-level analysis:** The analysis uses the shipment/ASN level as the primary unit of analysis. Results therefore describe shipment-level operational patterns and should not be interpreted as independent observations of individual products, orders, or delivery routes.

- **Reporting thresholds:** Minimum shipment thresholds were applied in several analyses to reduce the influence of very small groups. These thresholds are **reporting criteria rather than measures of statistical significance** and do not eliminate sampling or representativeness limitations.

- **Small groups:** Some countries, vendors, brands, years, and shipment modes have relatively small shipment volumes. For example, the 2006 late-delivery rate was based on only **52 shipments**, while several ARV brands had fewer than 30 qualifying shipments. These results should therefore be interpreted cautiously.

- **ARV brand segmentation:** The brand-level ARV analysis excluded **197 mixed-brand shipments**, leaving **5,275 single-brand shipments** for comparison. Brand was selected because it had the lowest proportion of mixed-value records among the segmentation fields tested, but this still means the analysis does not represent every ARV shipment.

- **Shipment mode data quality:** The **N/A shipment mode** category was retained as a data-quality flag rather than interpreted as a genuine transportation mode. Its low observed late-delivery rate should therefore not be treated as evidence of superior performance.

- **Association rather than causation:** The 2011 investigation identified **SCMS from RDC as the largest identified contributor to late shipments in that year**, but the analysis does not establish that the vendor caused the wider increase in late deliveries. Other factors, including the separate contribution observed in South Africa, were also present.

- **Historical dataset:** The dataset covers shipments from **2006 to 2015**. The findings therefore describe historical supply-chain patterns within this dataset and may not directly represent current logistics conditions, costs, vendors, or delivery performance.

- **Scope of analysis:** The project focuses on descriptive operational analysis using the available shipment, delivery, vendor, product, mode, and freight-cost fields. Factors not captured in the dataset, such as specific routes, customs events, weather, infrastructure conditions, or individual carrier performance, were not independently analysed.
