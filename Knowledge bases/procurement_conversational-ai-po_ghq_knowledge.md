# Domain : Procurement
In AB InBev, procurement refers to the global function responsible for sourcing and managing all the goods and services the company needs to run its business—from raw materials for brewing beer to marketing, logistics, IT, and professional services. It is the strategic function that ensures the company buys the right goods and services at the right cost, quality, and sustainability standards to support brewing, operations, and growth worldwide.

# UseCase : procurement_conversational-ai-po_ghq
**BrewGPT PO** is a conversational AI solution designed to provide one-click answers to procurement-related queries. It enables users to quickly access information on purchases, goods received, invoice details, material spend, quantities and pricing, vendor performance, and payment terms. The system also delivers insights into financial spend by GL accounts, vendor delivery performance, missing or partial goods receipts, and spend analytics at category or country level across regions.

# Usecase definitions

-- Purchase Order (PO) : A formal request issued to a vendor to supply goods or services, specifying material, quantity, price, and delivery terms.

-- Goods Receipt (GR) : A confirmation that ordered goods have been received in the system, either fully or partially, against a PO.

-- Invoice : A vendor’s request for payment, submitted after goods or services have been delivered.

-- Spend : The total financial outflow related to procurement, measured across categories, vendors, regions, or GL accounts.

-- Material Pricing : The agreed cost of raw materials or services, often negotiated through contracts or purchase agreements.

-- Vendor : A supplier providing goods or services to AB InBev, with attributes like payment terms, performance, and compliance tracked.

-- Payment Terms : The agreed-upon conditions that define when and how a vendor is paid (e.g., Net 30, Net 60).

-- GL (General Ledger) Spend : Financial expenditures recorded under specific GL accounts for tracking and reporting purposes.

-- Delivery Performance : A vendor’s reliability in fulfilling orders on time, in full, and at the required quality.

-- Missing/Partial GR : A situation where the goods receipt has not been recorded (missing) or only part of the ordered quantity has been received (partial).

-- Category Spend : Procurement spend segmented by product or service categories (e.g., packaging, logistics, marketing).

-- Country/Regional Spend : Procurement spend segmented geographically, helping analyze supplier dependency or cost structures by region.

# Analysis Templates roadmap
## What has been implemented?

- There are a total of 6 ATs or functions currently implemented for BrewGPT Procurement. Below are the list and its definition

1. **category_country_spend_summary**
*Definition* : Provides the details of the category or country level spend, total quantity of purchase , count of PO and Invoices available and count of suppliers for the requested category or country. 

*Inputs to provide* : Users to provide atleast one of the below details along with the time period (Country or category)  

*Outputs to expect* : Shows the Category or country level spend and quantity details along with count of Invoices and POs , countries and suppliers for the requested timeframe. 

*Sample Queries* : 
-- Provide the spend for Technology Category in Belgium for Q2 2025.  
-- Show the increase in spend for packaging category in 2025 compared to 2024 in UK  
-- can you breakdown the spend at country level for FY24 ?  
-- What is the 2024 spend for CAPEX in Europe.

2. **material_spend_summary**
*Definition*: Provides summary at material level spend details and quantity including the unit, count of suppliers providing the material, Invoice count, the minimum, maximum and average unit price of the material.

*Inputs to provide* : Users to provide atleast one of the below details along with the time period (Material , Vendor, Country, category)  

*Outputs to expect* : Shows the Material wise spend and quantity details along with the Unit Price, Unit of measurement, Average Unit Price , count of Invoices and POs for the requested timeframe. 

*Sample Queries*:
-- Provide the material spend details for packaging category in Belgium.  
-- Provide the spend for material 51366905 in 2024  
-- What are the top 5 materials by quantity in Germany in 2023?  
-- Can you provide the material spend details for MALT in 2025.

3. **vendor_spend_summary**
*Definition*: This function is used to understand the Spend at Vendor level. It provides details of the vendor details, its spend and total quantity ordered for the timeframe and its PO and Invoice count and average Payment Term.

*Inputs to provide* : Users to provide atleast one of the below details along with the time period (Vendor, Country, category)  

*Outputs to expect* : Shows the Vendor wise spend and quantity details along with the count of Invoices and POs for the requested timeframe. 

	*Sample Queries*:
-- Provide the vendor spend in Netherlands for 2024.  
-- Provide the spend for vendor 300533 in 2025.  
-- Provide list of vendors that supply glasssheets  
-- Provide the spend for vendor SOFTSERV - PARENT VENDOR NAME in Belgium in year 2025

4. **po_level_spend_summary**
*Definition*: This is a function that provided the line-item level details of the Purchase order, Invoice or the Goods Received depending on the question asked. This function is triggered when user wants to understand the details in PO or get the GR or Invoice details for the PO or the Purchase details for the requested Invoice or GR Number.

*Inputs to provide* : User can get the complete details of the GR,Invoice or the PO by providing the exact PO Number, Invoice Number or the GR number for which information is required. Alternatevily, users can provide the vendor or category in the question for which the above details are required.  

*Outputs to expect* : Line item level details or the selected source ( GR, PO or Invoice) for the selected timeframe. 

	*Sample Queries*:
-- Provide the PO details for Vendor  
-- Can you provide the PO details for category technology in march 2025  
-- Provide the GR Details for purchase Order 4508557224  
-- Provide the invoices raised for Purchase Order 4507920582 in 2024

5. **po_gr_ir_summary**
*Definition*: This function focusses primarily on understanding the delivery performance of the vendors and understanding the missing or partial goods received for the category or PO in question.

*Inputs to provide* : User can query the delvery performance or the Partial GR details across vendors by providing atleast one of the below details along with the time period (Vendor, Material, Country, category or PO number)  

*Outputs to expect* : Shows the Vendor wise delivery performance and details of missing or partial GR for the requested timeframe. 

	*Sample Queries*:
 -- Provide the delivery performance in bottles category in march 2025 per vendor for belgium  
-- show me delivery perofmrance for po number 2000020417 in 2023  
-- What is the average delivery delay in 2023 for Vendor SMURFIT KAPPA WSM  
-- How many Tech POs are having partial GR posting in 2024?

6. **GL_spend_summary**
*Definition*: This feature allows users to query the General Ledger spend summary for various categories or vendors or the PO numbers for requested timeframe.

*Inputs to provide* : User can query the GL spend summary by providing atleast one of the below information along with the time period (Vendor, GL Account , Cost center, category or PO number)  

*Outputs to expect* : Shows the financial accounting / General Ledger spend, quantity summary across the GL Account with additional information on cost centers, Supplier count, country count for the requested Year. 

	*Sample Queries*:
-- What is the GL spend for Malt GPO Category in Belgium, Netherlands and UK?  
-- Provide the GL Details at cost center "M125B411" for 2025  
-- Give me the material spend details for Belgium in 2025 for packaging category.  
-- can you provide GL Details for pos 4508557226,4508575017,4508571305,4508587005
 

## What will be implemented?
- ProMS Handbook : Provides the details of the procurement managenent system like sourcing and negotiation in ABI with vendors, Supplier relationship management , contract management and operations and category strategy. BrewGPT will use the provided documents for ProMS and helps answer the details in these handbooks. 

-- *Sample Queries* : WIP
  
- The below functions that are currently available for Europe will be implemented for other Zones like NAZ,MAZ,SAZ  
-- GL_spend_summary
-- category_country_spend_summary, 
-- po_gr_ir_summary, 
-- po_level_spend_summary, 
-- vendor_spend_summary, 
-- material_spend_summary

# Data ingestion roadmap 

## What has been implemented?
-- BrewGPT is enabled with below table information.

-   Table Name : PURCHASE_ORDER 
  This table provides line-item level purchase order (PO) data, including vendor and material details, along with categorization information, such as material VBS and vendor VBS categories. It contains various fields that support financial analysis, such as PO spend, PO quantity, and other PO-related metrics. Additionally, it includes details on outline agreements, contracted POs, PO automation, purchasing groups, and other procurement attributes, making it useful for tracking and analyzing purchase order commitments.

- Table Name : INVOICE
This table provides invoice data at the invoice ID level, detailing vendor and material information, as well as categorization information such as material VBS and vendor VBS categories. It is primarily used for financial analysis, including metrics such as invoice spend, invoice quantity, and other invoice-related insights. This table is the default source for queries related to financial spend, price, quantity etc. unless another specific table is specified.

- Table Name : GOODS_RECEIVED
This table provides comprehensive Goods Receipt (GR) data at the GR ID level, including vendor and material details, along with categorization information such as material VBS and vendor VBS categories. Each row in this table represents a GR transaction based on the received material or service. It is useful for tracking GR spend, GR quantity, and other GR-related metrics. This table is essential for analyzing delivery performance, material goods receipt trends.

- Table Name : GL_ACCOUNT
This table contains General Ledger (GL) financial data related to procurement transactions, including invoice postings linked to purchase orders (POs). It provides details at the document line-item level, capturing financial and accounting attributes such as GL account numbers, cost centers, company codes, PO numbers, and GL posting amounts. This table is essential for spend analysis, and cost tracking with respect to GL accounts enabling insights into accounting entries related to procurement activities.

- Table Name : MATERIAL_VBS_MASTER
This table provides a six-level hierarchical categorization (L1 to L6) for each material or good purchased, with each level offering increasingly granular classification. Each material_vbs_code is associated with categories from L1 (broadest) to L6 (most granular), where each level is a child of the one above it (e.g., L1 is the parent of L2, L2 is the parent of L3, and so on). This hierarchical structure enables detailed analysis of material spend by category. 

- Table Name : PLANT_MASTER
This is a dimension table which contains zone_id, plant_id, company_code, purchase_organization, purchase_group, plant_name data.

- Table Name : VENDOR_MASTER
This is a dimesion table which contains vendor_code, country, vendor_name, parent_vendor_name, vendor_vbs_code, payment_terms 

- Table Name : MATERIAL_MASTER
This is a dimension table which contains material_id, material_description, material_vbs_code, material_vbs_category.

- Table Name : VENDOR_VBS_MASTER
This is a dimenstion table which contains vendor_vbs_code, main_category, sub_category, gpo_category, vendor_vbs_category.

## What will be implemented?
- WAPT - Basic Details and Opportunities for WAPT : Basic details for WAPT and the Unrestricted opportunity for Suppliers will be available in system by September 2025.
- ProMS Unstructured Data : The procurement management system data will be available in system in Q4 2025. 
- Purchase Order  ,Goods Received and Invoice Details for NAZ, SAZ, MAZ, APAC & AFR(SA) will be available by October 2025.
