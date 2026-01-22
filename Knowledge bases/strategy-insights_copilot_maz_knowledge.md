# Domain
The MAZ Domain supports S&I (Strategy & Insights) by enabling cross-functional reporting and analysis on multiple datasets. Currently, coverage is available for Colombia and Mexico, with planned expansion to additional markets in the future.
This domain brings together diverse datasets and structured analysis to provide consistent, actionable insights for business decision-making. It is designed to generate cross-functional reports and analysis across areas such as:
Brand Guidance
Sales and Market Performance (Sell-In, Sell-Out, Nielsen, POS)
Macroeconomic Indicators (country- and region-level context)
By integrating these datasets within a unified domain, MAZ enables a single source of truth for S&I teams, supporting both strategic planning and tactical execution.

# Usecase
1. Brand Guidance
Focuses on the study of brand power.
Based on survey-driven metrics, capturing consumer perceptions of brand strength and positioning.
Helps track brand health, equity, and long-term sustainability.

2. Category Insights
Focuses on the study of participation.
Based on survey-driven metrics around consumer occasions, participation, and category consumption patterns.
Provides understanding of category dynamics and drivers of growth.

3. Point of Sales Data (Nielsen)
Provides a market-level view of performance through retail sales data.
Covers sales volume, value, market share, distribution, and pricing.
Enables competitive benchmarking and channel performance tracking.

4. FP&A (ABI Revenue)
Represents internal revenue and sales metrics from ABI systems.
Provides a view of actual commercial performance, aligned with financial reporting.
Supports forecasting, budget alignment, and performance evaluation.

5. Macroeconomics
Integrates external economic indicators at country and regional levels.
Includes GDP, inflation, income levels, and other key macroeconomic drivers.
Provides context to interpret brand, category, and commercial performance.

# Usecase definitions
1. COL_MARKET_SHARE
brand – Name of ABI or competitor brand.
brand_numerical_distribution – % of markets stocking the brand.
container_type – Packaging type (e.g., bottle, can, draft).
country – Country of sales.
is_alcoholic – Identifies if the product contains alcohol.
manufacturer – Producer of the product.
market_name – Market or region (e.g., Andes, Norte).
market_share – Share of category sales held by the brand.
market_tag – Code identifying the market.
pack_size – Size of a sales pack.
pack_type – Category of packaging (e.g., entry, frequency).
pack_unit – Unit size of the pack (e.g., 1 pack, 6 pack).
pack_volume – Volume of liquid in the SKU.
presentation_type – Whether returnable or non-returnable.
size_type – Serving size (single serve vs sharing).
product_numerical_distribution – % of stores carrying the SKU.
revenue_cop – Net sales revenue in Colombian pesos.
sales_volume_hl – Sales volume in hectolitres.
sku_name – Name of the specific SKU.
sku_tag – Unique SKU identifier.
sub_brand – Sub-brand under the main brand.
time_period – Period of reporting (month/quarter).
year – Year of reporting.

2. CO_INVOICE
country – Country where invoice is issued.
date – Billing date of the invoice.
product_short_code – Internal product code.
region – Region of the invoice.
revenue_cop – Revenue after discounts/taxes.
sales_volume_hl – Sales volume in hectolitres.

3. CO_PRODUCT
is_alcoholic – Identifies if the product contains alcohol.
pack_type – Classification of pack (e.g., entry, frequency).
brand_origin_type – Whether the brand is local or imported.
container_type – Packaging container type.
beer_type – Style/type of beer.
brand – Main brand name.
pack_size – Size of a pack.
pack_volume – Volume per SKU.
presentation_type – Returnable or non-returnable format.
price_segment_name – Price tier (e.g., core, premium).
product_short_code – Internal product identifier.
product_volume – HL per physical case.
size_type – Serving size (single vs sharing).
sku_name – Detailed SKU description.
sub_brand – Sub-brand of the product.

4. FACT_CONSUMER_KPIS_BRAND_ATLANTIA
brand – Brand being measured.
country – Country of survey data.
year – Survey year.
brand_p4w_participation – % of consumers consuming in last 4 weeks.
cohort – Cohort value (e.g., age group).
cohort_name – Type of cohort (age, gender, region, SEL).
manufacturer – Company producing the brand.
price_tier – Price classification of brand.
source – Source of the survey data.
sub_brand – Sub-brand measured.
time_period – Reporting period for survey.

5. FACT_CONSUMER_KPIS_BRAND_KANTAR
brand – Brand name.
difference – How distinctive the brand is.
meaningful – Emotional and functional relevance to consumers.
power – Predictive demand potential score.
salience – Mental availability of the brand.
cohort – Cohort segment value.
cohort_name – Cohort type (age, gender, etc.).
country – Country of survey.
manufacturer – Company producing the brand.
price_tier – Price classification.
source – Source of data (Kantar/Atlantia).
sub_brand – Sub-brand name.
year – Survey year.
time_period – Period of reporting.affinity_score – Consumer love for the brand.
meet_need – Ability to meet functional/emotional needs.
unique_score – Perceived uniqueness of the brand.
dynamic_score – Brand’s trend-setting ability.
consumption_p7d – % consumed in past 7 days.
consumption_p4w – % consumed in past 4 weeks.
consumption_p3m – % consumed in past 3 months.
trial – % of people who tried the brand.
aware_of_brand – % aware of the brand.
total_spontaneous_awareness – % recalling brand unprompted.
top_of_mind – % who mention brand first.

6. FACT_CONSUMER_KPIS_GLOBAL_CATEGORY
servings_volume – Total volume of consumption.
source – Source of data.
year – Year of survey.
country – Country of survey.
p4w_participation – % of consumers participating in last 4 weeks.
beverage_type – Type of beverage (beer, wine, etc.).
cohort – Cohort group value.
cohort_name – Type of cohort (age, gender, etc.).
occasions – Average occasions of consumption.
time_period – Reporting period.

7. STR_INSIGHTS_MACROECONOMICS
country – Country name.
date – Date of metric (start of month).
kpi_name – Name of macroeconomic indicator.
region – Regional breakdown.
time_period – Reporting timeframe.
value – Measured value of the KPI.
year – Year of reporting.

8. Kantar
A) Equity Framework KPIs
Power
Definition: Prediction of volume share a brand can command based on consumer predisposition to choose the brand over others.
Scale: Within a market, Power sums to 100.
Example query: What is the Power of Budweiser in Brazil in FY 2024?
Meaning
Definition: Extent to which brands build an emotional connection and are seen to deliver against functional needs.
Scale: Indexed at 100 within a market.
Example query: Show the Meaning trend of Corona in Mexico from 2020 to 2025.
Difference
Definition: Extent to which brands set themselves apart from the category by offering something others do not and by leading the way.
Scale: Indexed at 100 within a market.
Example query: What is the Difference score of Skol in Brazil across age cohorts in 2024?
Salience
Definition: How quickly and easily the brand comes to mind.
Scale: Indexed at 100 within a market.
Example query: Compare the Salience of Heineken in Netherlands across regions in FY 2023.
Premium
Definition: Prediction of price index a brand can support based on consumer predisposition to pay more for the brand than others.
Scale: Indexed at 1 within a market.
Example query: What is the Premium score of Stella Artois in UK in Q2 2025?
B) Emotional and Functional Equity Sub-scores
Affinity
Definition: Emotional connection with the consumer.
Scale: Likert scale ranging from -3 to 3.
Example query: What is the Affinity score of Corona in Mexico across gender cohorts in FY 2024?
Meet Needs
Definition: Fulfillment of functional needs of the consumer.
Scale: Likert scale ranging from 1 to 7.
Example query: Show the Meet Needs score of Budweiser in US by income cohorts in FY 2025.
Unique
Definition: Extent to which brands set themselves apart from others.
Scale: Likert scale ranging from 1 to 7.
Example query: What is the Unique score of Heineken in Germany across regions in 2024?
Dynamic
Definition: Degree to which the brand is trend-setting.
Scale: Likert scale ranging from 1 to 7.
Example query: Show the Dynamic score trend of Cass Fresh in South Korea from 2022 to 2025.
C) Funnel Metrics
Top of Mind
Definition: First brand to come to mind.
Example query: What is the Top of Mind score of Quilmes in Argentina in Q1 2025?
Awareness
Definition: Familiarity with a brand.
Example query: What is the Awareness level of Skol in Brazil in FY 2024?
Spontaneous Awareness
Definition: Measure of how people recall a brand without any help.
Example query: What is the Spontaneous Awareness of Stella Artois in Belgium in FY 2023?
Trial
Definition: Trial rate of the brand (ever tried).
Example query: What is the Trial score of Corona in Mexico in FY 2024?
P3M, P4W, P7D
Definition: Consumption incidence in the past 3 months (P3M), 4 weeks (P4W), or 7 days (P7D).
Example query: What is the P3M consumption of Budweiser in US in FY 2024?
Consideration
Definition: Likelihood to choose a brand next time.
Scale: 5-point Likert scale.
Example query: What is the Consideration score of Heineken in Netherlands in Q2 2025?
D) Brand Associations and Drivers
Imagery
Definition: Brand associations of a consumer, based on specific imagery statements.
Example query: What is the Imagery score for “ADDS ENERGY TO YOUR SOCIAL OCCASION” for Quilmes in Argentina in Q1 2025?
In Market Facilitators (IMF)
Definition: Attribute-level factors driving choice of a brand.
Example query: What are the IMF scores of Budweiser in US in FY 2024?
Most Likely Occasion
Definition: Occasion most likely associated with beer consumption.
Example query: What is the Most Likely Occasion score of Corona in Mexico in FY 2025?
First Brand Occasion
Definition: First brand to come to mind for a given occasion.
Example query: What is the First Brand Occasion score of Skol in Brazil for party occasions in FY 2024?
E) Perceptions of Worth and Cost
Worth
Definition: Worth perception of the brand.
Scale: Likert scale ranging from 1 to 3.
Example query: What is the Worth score of Heineken in Netherlands in FY 2025?
Cost
Definition: Cost perception of the brand.
Scale: Likert scale ranging from 1 to 7.
Example query: What is the Cost score of Cass Fresh in South Korea in Q3 2024?
F) Communication Awareness
Total Brand Communication Awareness
Definition: Whether consumers have seen, heard, or read about the brand.
Example query: What is the Total Brand Communication Awareness of Budweiser in Canada in FY 2023?

# Analysis Templates Roadmap
What is Analysis Templates?

Analysis Templates (AT) are pre-defined functions within Insights Copilot designed to consistently answer specific types of business questions with a structured workflow. They ensure reproducibility, accuracy, and alignment with business use cases by standardizing how queries are interpreted and executed.


## What has been implemented?
**get_brand_highlights**
Purpose: Used when the query requests brand-level highlights, brand performance, brand deep dives, drivers of key performance indicators (KPIs), or cohort-level breakdowns of Power, Meaningful, Difference, or Salience.
Triggers: Keywords such as “brand highlights”, “brand performance”, “deep dive of brand X”, “drivers of power”, “drivers of salience”, “breakdown of meaningful across cohorts”, “cohort-level power”.
Output: Returns detailed brand-level highlights or breakdowns of brand KPIs across cohorts.
Special Rule: If no KPI is mentioned, default to analysis_requested_for_kpi = 'power'.

**get_country_highlights**
Purpose: Used when the query requests country-level highlights or overall performance without specifying any brand or KPI.
Triggers: Keywords such as “country highlights”, “overview of <country>”, “how is <country> doing”.
Output: Returns high-level summary for the requested country.

**get_factual_data**
Purpose: Used for factual KPI retrieval, numerical values, cohort-based breakdowns, imagery data, time trends, comparisons, and ranking.
Triggers: Keywords and intents such as “KPI of brand X”, “compare power vs salience”, “awareness among females”, “imagery of brand Y”, “trial in Colombia”, “trend of power over years”, “ranking of brands”.
Output: Returns raw KPI values or breakdowns at the specified analysis level (brand, brand family, aggregate, global).
Behavior: Always set analysis_level based on scope:
brand_level if specific brand(s) are requested.
brand_family_level if brand families are requested.
country_aggregate_level if ABI totals, megabrands, or aggregates are requested.
global_level if zones, market maturities, or global scope are requested.

**get_global_highlights**
Purpose: Used when the query requests global-level highlights, global drivers, or global performance.
Triggers: Keywords such as “global highlights”, “global performance”, “global report”, “global drivers”, “global overview”, “how is ABI doing globally”.
Output: Returns highlights or drivers of performance at the global level.

**call_get_atlantia_brand_participation**

Definition:
This Analysis Template is designed to answer questions related to brand participation according to Atlantia. It is particularly useful for understanding participation metrics over time, by brand, tier, price tier, or cohort.
Example: “What is the participation of Aguila Light in 2024 according to Atlantia?”
Outputs Expected:
Participation metric (brand_p4w_participation) as per Atlantia.
Results segmented by the specified inputs (brand, tier, cohort, etc.).
Summarized and structured response integrated seamlessly into the chat.
Example Queries:
“What is the participation of Aguila Light in 2024 according to Atlantia?”
“Show me participation for Megabrands in Q2 2023 for Colombia.”
“What is the participation of Core brands across Mexico in FY 2024 by gender?”

**call_get_beverage_type_participation**

Definition:
This Analysis Template is designed to answer questions related to beverage participation and performance according to Atlantia. It covers metrics such as participation, occasions, servings, share of occasions (SOO), and share of throat (SOT) for beverages.
Example: “What is the POS of beverages in 2024 according to Atlantia?”
Outputs Expected:
Participation and performance metrics for beverages, aligned to the chosen KPI(s).
Results segmented by beverage type, cohorts, and other specified dimensions.
Summarized output presented in structured sections within chat.
Example Queries:
“What is the POS of wine in 2024 according to Atlantia?”
“Show me occasions and servings for  beverages in Q1 2025 for Colombia.”
“What is the participation of Top 5 beverages in Mexico for H2 2024 by gender?”

**call_get_nielsen_market_share**

Definition:
This Analysis Template is designed to answer questions related to nielsen kpi and brand performance according to Nielsen. It is particularly useful for tracking KPIs of ABI and non-ABI (competitor) brands across markets, time periods, and packaging formats.
Example: “What is the market share of Poker CTE in 2024 in Nielsen?”
Outputs Expected:
Nielsen performance metrics based on the selected KPI(s).
Results segmented by brand, tier, market, pack details, or other specified inputs.
Structured response with numerical accuracy and business-ready presentation.
Example Queries:
“What is the market share of Poker CTE in 2024 in Nielsen?”
“Show me sales volume for Core+ brands in Q3 2023 in Mexico by pack type in nielsen.”
“What is the weighted distribution of Top 5 brands across Colombia in FY 2024 by container type?”

**call_get_abi_sell_in_sales_volume_revenue**

Definition:
This function retrieves brand performance metrics based on sell-in sales volume or numerical distribution according to sell-in.
Expected Output:
Aggregated sell-in KPI values (volume, distribution)
Structured by brand / tier / time period / geography as per inputs
Summarized text + optional tabular breakdown
Example Queries:
“What is the sales volume of Stella Artois in 2024 according to sell-in in Colombia?”
“Show me numerical distribution of Core brands in Mexico Q1 2025 in sellin.”
“Give me the top 5 brands by sales volume in Colombia FY 2023 in sellin.”

**call_get_macroeconomic_kpis**

Definition:
This function provides macroeconomic indicators such as GDP, CPI, unemployment rate, and exchange rates.
Expected Output:
Specific macroeconomic indicator values
Summarized narrative for trend interpretation
Structured time-series table if multiple periods selected
Example Queries:
“What was the unemployment rate in Colombia in 2024?”
“Show me GDP per capita for Mexico from 2020 to 2024.”
“What is the inflation (CPI) trend for Peru Q1 2023?”

**call_get_product_attribute_mix**

Definition:
This function provides sales distribution across product attributes such as container type, presentation type, price segment, beer type, etc.
Expected Output:
Distribution percentages across selected attribute categories
Summarized insights on product mix changes
Tabular representation (attribute vs. share %)
Example Queries:
“What is the container type in Colombia in 2024?”
“Give me the pack type mix for Mexico Q2 2025.”
“Show size type  in Colombia FY 2023.”

### What will be implemented?
**Kantar**
Pending enhancements to Analysis Templates include:
Price Segment Views – Deeper insights by price segment.
Benchmarking – Comparisons vs. segment or competitor performance.
Imagery & Occasion Queries – Ability to answer specific imagery- or occasion-based questions by name.

**Atlantia**
Cross-Cohorts – Deeper analysis combining multiple cohort dimensions

**Nielsen**
City Granularity – Finer breakdown of Nielsen data at the city level for more localized performance insights.

**sellin**
City Granularity – Finer breakdown of Nielsen data at the city level for more localized performance insights.

**macroeconomics**
Weather Data – Integration of climate and weather indicators to enrich economic and consumption context.

**Other**
Direct-to-Consumer (D2C) and FP&A by October 7th

# Data ingestion roadmap
## What has been implemented?
Source: **Brand Guidance**
The Brand Guidance dataset has been implemented to measure consumer perceptions, brand health, and equity tracking across multiple markets. It provides survey-based insights that connect brand performance to consumer attitudes and behaviors.
1. Views Enabled
Business users can explore the Brand Guidance dataset across multiple perspectives:
Brand Tier – Brand performance by tier classification.
Price Tier – Brand positioning by price segment (note: avoid inquiries referencing “Core” and “Core+” directly).
Portfolio Classification – Includes Mega Brand view.
Global Brand Classification – ABI vs Competitor tagging.
Cross-Cohorts – Analysis by:
Age
Gender
Region
Income

2. Timeframes Available
Brand Guidance enables trend tracking across both short- and long-term horizons:
Quarterly
Year-to-Date (YTD)
Half-Yearly
Full Year
Rolling Windows – R3M, R6M, R9M, R12M
Data Availability: From Q1 2020 to Q2 2025

3. Metrics Enabled
The dataset enables deep measurement of brand strength across the following dimensions:
MDS – Power, Meaningful, Different, Salience.
AMUD – Affinity, Meet Needs, Uniqueness, Dynamic.
Awareness Funnel – Levels of consumer awareness.
Consumption Funnel – Trial, past 3 months (P3M), past 4 weeks (P4W), past 7 days (P7D).
Imagery (BIPS) – Brand imagery perception scores.

Source: **Atlantia**

The Atlantia dataset provides survey-based insights into consumer participation and category dynamics. It allows users to explore brand, category, and consumer performance across multiple cohorts, with flexible timeframes and metrics such as participation, occasions, servings, and share dynamics.
1. Views Enabled
Users can analyze data across different perspectives:
Price Tier – View performance by price segment.
Brand Tier – Assess brand performance by tier classification.
Beverage Type – Coverage includes:
Beer
Wine
Spirits
Carbonated Soft Drinks (CSDs)
Bottled Water
Energy Drinks
Global Brand Classification – Available for Colombia only.
Cohorts – Consumer segmentation based on:
Age
Gender
Region
Socio-Economic Level (SEL)
2. Timeframes Available
Business users can explore trends and performance over:
3-Month Rolling (Default)
Quarterly
Half-Yearly
Full Year
Data Availability: From January 2022 to June 2025
3. Metrics Enabled
The following key business metrics are already available:
Participation – Share of consumers engaging with a brand or beverage type.
Occasions – The number of consumption occasions.
Servings – Total servings consumed.
Servings LBE – Liters of Beer Equivalent servings.
Servings Volume – Volume of servings in standard units.
Share of Occasion (SOO) – Share of occasions captured by a brand or beverage type.
Share of Throat (SOT) – Volume share captured by a brand or beverage type.
Example dataset and its definition eg. what data is covered with samples

Source: **Nielsen**

The Nielsen dataset provides market-level insights into brand and competitor performance. It offers rich pack-level granularity, regional breakdowns, and a wide range of metrics such as sales volume, value, market share, and distribution, enabling competitive benchmarking and channel performance tracking.
1. Views Enabled
Users can analyze data across the following perspectives:
Price Tier – View performance by price segment.
Brand Tier – Assess brand performance by tier classification.
Global Brand Classification – Available for Colombia only.
Market / Region – Regional performance breakdown:
Andes
Centro
Norte
Sur
Packs – Granular pack-level analysis across:
Pack Volume
Pack Type
Pack Unit
Size Type
Container Type
Presentation Type
2. Timeframes Available
Business users can track performance across different time horizons:
Monthly
Quarterly
Half-Yearly
Full Year
Data Availability: From January 2022 to June 2025
3. Metrics Enabled
The following Nielsen metrics are now available for analysis:
Sales Volume – Total sales in hectoliters.
Market Share – Share of category captured by a brand.
Sales in Value – Sales expressed in monetary terms.
Brand Numerical Distribution – % of outlets carrying the brand.
Brand Weighted Distribution – Distribution weighted by sales volume.
Numerical Distribution – % of outlets carrying the category.
Weighted Distribution – Category distribution weighted by sales.
Rate of Sale – Sales velocity per outlet.
WAMP (SKU) – Weighted Average Market Price at SKU level.
Volume per Unit – Average pack volume sold.
Price per Liter (SKU) – Price realization per liter at SKU level.

Source: **Sell-In**

The Sell-In dataset provides internal sales performance insights across brands, packs, and regions. It enables analysis of both daily sales execution and aggregated trends, helping users evaluate distribution reach, pack dynamics, and commercial performance over time.
1. Views Enabled
Users can analyze Sell-In data through multiple perspectives:
Price Tier – Performance by price segment.
Brand Tier – Brand performance by tier classification.
Regions – Regional breakdown for Colombia:
Andes
Centro
Norte
Sur
Packs – Detailed pack-level analysis across:
Pack Volume
Pack Type
Size Type
Container Type
Mix Analysis – Product mix analysis across:
Presentation Type
Beer Type
Is Alcoholic / Non-Alcoholic
Price Segment
2. Timeframes Available
Sell-In provides flexible timeframes for analysis, enabling both short-term and long-term tracking:
Daily
Monthly
Quarterly
Half-Yearly
Full Year
Data Availability: From January 2021 to 20 August 2025
3. Metrics Enabled
The following Sell-In metrics are available for business analysis:
Sales Volume – Internal sales volume reported.
Numerical Distribution – Outlet-level coverage of Sell-In distribution.

Source: **Macroeconomic Data**

The Macroeconomic dataset provides country- and regional-level economic indicators that support performance benchmarking and contextual analysis. It includes metrics such as GDP, inflation, employment, and consumer price indices, offering essential context for interpreting brand, category, and commercial performance.
1. Views Enabled
Macroeconomic data can be explored across:
Global Brand Classification – Countries available:
Colombia
Ecuador
El Salvador
Guatemala
Honduras
Mexico
Panama
Peru
República Dominicana
Market / Region View – Regional grouping:
Andes
Centro
Norte
Sur
2. Timeframes Available
Users can analyze macroeconomic indicators over both short- and long-term horizons:
Monthly
Quarterly
Half-Yearly
Full Year
Data Availability: From 2005 to 2025
(Note: Some periods are missing in the source, requiring adjustments and data finesse.)
3. Metrics Enabled
All Macroeconomic Metrics – Includes GDP, inflation, employment indicators, consumer price indices, and other key economic measures available in the dataset.

## What will be implemented?
**Kantar** - Monthly level Power and MDS along with other KPIs to be ingested in 2025 Q4,
Significance test numbers for Power comparison across periods to be ingested in 2025 Q4
**Nielsen** – Addition of City-Level Data to provide more localized market performance insights.
**Sell-In** – Expansion to include City-Level Data for deeper internal sales visibility.
**Macroeconomics** – Integration of Weather Data to enrich external context and consumption analysis.
**other** - Direct-to-Consumer (D2C) and FP&A Dataset by October 7th