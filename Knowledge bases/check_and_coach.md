# Domain
What is Management Syatem?
Management System is a structured framework that provides the fundamentals for sustaining and improving organizational results. It includes training in various methodologies such as SDCA (Standardize-Do-Check-Act), PDCA (Plan-Do-Check-Act), and encompasses all Management Systems like VPO, SMS, DPO, LCP, and ProMS. The system is designed to be applicable at all levels of the organization and involves regular training, both for new hires and as annual refreshers, to close execution gaps or introduce new concepts and processes. The Management System connects strategic plans to shopfloor execution through a cascading process involving business descriptions, process maps, SWOT analysis, KPI dashboards, routine and performance review processes, and a suite of management tools. It ensures alignment, standardization, and continuous improvement across the organization, integrating leadership, method, and knowledge to optimize efficiency and achieve strategic goals


# Usecase
What is LCP?
LCP is one of the management system which provides a unified framework to drive efficiency, sustainability, and innovation across global operations. They standardize processes, clarify roles, and integrate digital tools to optimize costs, cash flow, planning, logistics, people, safety, and sustainability. Collectively, these guides ensure cross-functional alignment with strategic goals, fostering operational excellence and long-term value creation. Through LCP Coaching Assistant we are enabling the faster and efficient resolution which in turn leads to operational improvement.

# Usecase definitions

- What does YTD mean?
    YTD: Year To Date - Structured data has data available at the YTD level along with MTD where YTD represents the value till the Date/Month mentioned for the year.
- What does MTD mean?
    MTD: Month To Date - Structured data has data available at the MTD level along with YTD where MTD represents the value of the Specific Month mentioned for the year.
- What does AC mean?
    AC - Actual values
- What does BU mean?
    BU - Budgeted values
- What does LY mean?
    LY - Last Year values for/at the same month last year.

# Analysis Templates roadmap
## What has been implemented?

### Analysis Template (AT) Definition
The assistant tries to map user queries to the Analysis Template (function) defined.  
Analysis Template considers the parameters from the questions and runs the analysis to provide a reproducable result.

### Available Analysis Templates

1. **`call_get_kpi_report`**  
   - Purpose: Used when the query requests values, comparisions, or trends of key performance indicators (KPIs)
   - Triggers: Keywords such as *Value of KPI X”*, *“trend of KPI X”*, *“Compare KPI X for /location_type/”*.  
   - Output: Returns KPI Value or Trend or Comarision across location types / Attribute Types.  
   - Special Rule: 
            - If no Year is mentioned, default to `year = Current Year`
            - If no Atrriute Type is mentioned, default to `attribute = 'AC'`.

### Function Selection Priority
The selection of Analysis Template follows strict priority order:
1. If query is about **values, comparisions, or trends of key performance indicators (KPIs)** → select `call_get_kpi_report`.  

### Parameters and Extraction Rules
All extracted parameters must be passed as lists of values. When queries imply “all” values, the keyword `across` must be used.

- **query_type**: Must be one of `'kpi_compare'`, `'kpi_snapshot'`.  

- **kpi_code**: Must be one of  
  `'VLC'`, `'MT1'`, `'MT2'`, `'DIO Gap'`, `'MT4'`, `'MT7'`,  
  `'SL-K0033'`, `'LV-K0170'`, `'LT-K0060'`, `'LS-K8250'`,  
  `'LP-K2200'`, `'LP-K1600'`, `'LC-K7934'`, `'LB-K2200'`, `'LB-K1300'`.  

- **kpi_name**: Must be one of  
  `'VLC (P+P)'`, `'NPS'`, `'DIO (days)'`, `'DIO Gap'`, `'TRI'`, `'SCOH / VIC'`,  
  `'Total In Full %'`, `'Transportation CO2/HL Sold'`,  
  `'Weight per Shipment vs Max Weight Allowed'`,  
  `'% FG HL Out of Range Total'`, `'Production Plan Attainment Total'`,  
  `'Monthly Forecast Accuracy (M+1)'`, `'% Materials Out of Range Total'`,  
  `'Weekly Forecast Accuracy (W+2)'`, `'Allocation Efficiency'`.  

- **year**: String. Example: `'2025'`.  

- **month**: Integer from `1` to `12`.  

- **location_type**: Must be one of `'COUNTRY'`, `'ZONE'`, `'COUNTRY_GROUP'`, `'GLOBAL'`.  

- **country**: Must be one of  
  `'Luxembourg'`, `'South Africa'`, `'India'`, `'France'`, `'Paraguay'`, `'Sweden'`, `'Denmark'`, `'Uruguay'`, `'Ghana'`, `'Ecuador'`,  
  `'Austria'`, `'Italy'`, `'Peru'`, `'Netherlands'`, `'Barbados'`, `'Panama'`, `'Korea'`, `'Norway'`, `'Chile'`, `'China'`,  
  `'Canary Islands'`, `'Mozambique'`, `'Tanzania'`, `'VIM'`, `'El Salvador'`, `'Finland'`, `'United States'`, `'Portugal'`, `'Switzerland'`, `'Dominican Republic'`,  
  `'RU1'`, `'Spain'`, `'United Kingdom'`, `'Namibia'`, `'Belgium'`, `'Bolivia'`, `'Ukraine'`, `'Russia'`, `'Botswana'`, `'Nigeria'`,  
  `'Guatemala'`, `'Germany'`, `'Honduras'`, `'Canada'`, `'Vietnam'`, `'Eswatini Country'`, `'Uganda'`, `'UKR'`, `'Mexico'`, `'Colombia'`,  
  `'Licence'`, `'Poland'`, `'Greece'`, `'Brazil'`, `'Lesotho'`, `'Zambia'`, `'Argentina'`, `'Ireland'`.  

- **zone**: Must be one of `'EUR'`, `'AFR'`, `'APAC'`, `'MAZ'`, `'SAZ'`, `'NAZ'`.  

- **country_group**: Must be one of  
  `'BNFL'`, `'AFR - BU South'`, `'BU India'`, `'BU Andina'`, `'EUR - BU CENTRAL'`, `'BU Rio de la Plata'`,  
  `'AFR - BU South East'`, `'BU Canada'`, `'BU Peru & Ecuador'`, `'BU Colombia'`, `'BU CAC'`, `'BU East Asia'`,  
  `'BU Brazil'`, `'AFR - BU Nigeria'`, `'EUR - BU West Europe'`, `'BU China'`, `'BU United States'`,  
  `'EUR - BU East Europe'`, `'BU SEA'`, `'BU Mexico'`.  

- **attribute**: Must be one of `'AC'`, `'AC,LY'`, `'AC,BU'`, `'AC,LY,BU'`.  

- **aggregation_period**: Must be `'MTD'`.  

- **compare_metric**: Must be one of  
  `'across_zones'`, `'across_countrygroup'`, `'across_countrygroup_in_a_zone'`, `'across_countries_in_a_country_group'`.  

---

### Behavioral Rules
- Default, set `aggregation_period = 'YTD'` unless MTD is specified.  
- Default, set `location_type = 'GLOBAL'` unless any location is specified.
- Default, set `year = Current Year` unless any Year is specified.
- Default, set `attribute = 'AC'` unless any other attribute like Budgeted or Last year is specified.

## What will be implemented?
Future implementations include the following:
- Create a templete for the self assessment data once onboarded.
- Summary views which would have number of analysis together based on the role specific requirements.
- As we get more details on the kind of questions being used, we will continue to update the templete

# Data ingestion roadmap 

## What has been implemented?

#### Structured
- Anaplan KPIs and Manual KPIs

#### Unstructured
-  2025 supply network planning Lcp handbook V1.
-  2025 transport execution Lcp handbook V1.
-  2025 demand planning Lcp handbook V1.
-  2025 inventory deployment Lcp handbook V1.
-  2025 core Lcp handbook V1.
-  2025 circular packaging Lcp handbook V1.
-  2025 delivery management Lcp handbook V1.
-  2025 e2e cash & cost pillar v1.1.
-  2025 global supply chain people pillar handbook.
-  2025 green logistics Lcp handbook V1.
-  2025 inventory policy Lcp handbook V1.
-  2025 lcp handbook materials planning V2.
-  2025 lcp handbook rules V01 (final).
-  2025 logep handbook V2.
-  2025 order management Lcp handbook V1.
-  2025 portfolio management Lcp handbook V1.
-  2025 s&op Lcp handbook V1.
-  2025 safety Lcp handbook V1.
-  2025 supply chain design Lcp handbook V8.
-  2025 supply chain management pillar handbook.
-  2025 transport management Lcp handbook V1.
-  2025 transport scheduling Lcp handbook V1.
-  2025 warehouse management Lcp handbook V1.
-  2025 E2e innovation pillar handbook.
-  Bu head ranking 2025 Rules 1.
-  Lcp 2025 - kpis book (final).
-  Lcp global owners 2025.
-  Supply chain E2e planning handbook V01.
-  Handbook Documentation handbook 2023 Lcp.
-  Handbook Handbook cust. centricity .
-  Handbook Lcp Handbook Int trade payment.


## What will be implemented?

#### Structured
- Self-assessment scores data
- Onboard more KPIs
