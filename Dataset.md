# Dataset

## Supply Chain Shipment Pricing Data

This project uses the **Supply Chain Shipment Pricing Data** dataset, containing historical shipment-level information from the **USAID Supply Chain Management System (SCMS)**.

The dataset covers pharmaceutical and health-commodity shipments and includes information relating to delivery dates, shipment modes, vendors, countries, freight costs, shipment quantities and values, product groups, and brands.

## Dataset Details

The original workbook used during the project contains:

- **Original shipment-history rows:** 10,324
- **Original variables:** 41
- **Project shipment-level records:** 7,030
- **Project variables:** 14
- **Unique shipment identifier:** ASN/DN
- **Countries:** 43
- **Vendors:** 73
- **Shipment modes:** Air, Truck, Air Charter, Ocean, and N/A
- **Product groups:** 5
- **Brands:** 47

The project-specific **Shipment level** dataset consolidates the underlying shipment-history records to one record per ASN/DN and contains:

- ASN/DN
- Country
- Vendor
- Shipment mode
- Scheduled delivery date
- Delivered to client date
- Delivery variance
- Delivery status
- Freight cost
- Total shipment quantity
- Total shipment value
- Product group
- Brand
- Brand consistency

## Data Preparation

The original shipment-history data was refined in **Microsoft Excel** before being analysed in Tableau.

The preparation process included:

- Reviewing the original shipment-history structure and identifying the fields required for the analysis.
- Creating cleaned numeric fields for weight and freight cost where the source contained numeric values alongside text-based freight or weight descriptions.
- Creating shipment-mode and delivery-performance fields for consistent analysis.
- Calculating delivery variance from scheduled and delivered-to-client dates.
- Classifying shipments as **Early, On Time, or Late** based on delivery variance.
- Resolving shipment-level freight cost using the underlying line-item records so that freight cost could be analysed at the shipment level.
- Consolidating shipment quantity and shipment value to the shipment level.
- Using lookup logic to bring product-group and brand information into the shipment-level dataset.
- Classifying shipments as **Single** or **Mixed** brand based on the brands associated with each ASN/DN.

The resulting **Shipment level** worksheet contains one record per ASN/DN and was used as the primary dataset for the Tableau analysis.

### Validation and Refinement

The analysis was iteratively reviewed during preparation to identify cases where incomplete freight information, shipment composition, or aggregation choices could distort comparisons.

Where necessary, calculations and comparison groups were refined before the final Tableau dashboards were produced. In particular, freight-cost comparisons were restricted to shipments with resolved freight costs where appropriate, rather than treating missing freight values as zero.

The analysis is descriptive and observational. The findings identify patterns and differences within the shipment data but do not establish causal relationships.

## Source

### Kaggle

The accessible copy used for this project was obtained from Kaggle:

**Supply Chain Shipment Pricing Data**

[Supply Chain Shipment Pricing Data - Kaggle](https://www.kaggle.com/datasets/sawandikirby/supply-chain-shipment-pricing-data)

### Original Source

The underlying dataset is associated with the **United States Agency for International Development (USAID)** and its Development Data Library.

**USAID - Supply Chain Shipment Pricing Data**

[USAID Development Data Library - Supply Chain Shipment Pricing Data](https://data.usaid.gov/d/a3rc-nmf6)

The Kaggle copy was used as the accessible dataset for the project, while the USAID source is provided for original-source attribution.

### Data Usage Note

The Kaggle re-upload used for this analysis states that the original dataset carried no explicit license and was re-uploaded for educational, non-commercial, and analytical demonstration purposes.

Separately, the original USAID publication identifies a **CC-BY** licensing arrangement under which the data is posted by USAID with attribution to the partner organisation that collected it.

This project uses the dataset for **non-commercial, educational analysis** and provides both sources for transparency and attribution.

## Citation

**Supply Chain Shipment Pricing Data.** USAID Supply Chain Management System (SCMS). Dataset accessed through Kaggle and the USAID Development Data Library.

The accessible Kaggle copy used in this project is:

**Supply Chain Shipment Pricing Data**, Kaggle.

The original source is:

**USAID Development Data Library - Supply Chain Shipment Pricing Data.**
