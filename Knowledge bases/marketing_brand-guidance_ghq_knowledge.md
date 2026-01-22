# Domain
Strategy and Insights (or S&I) is a domain within Marketing Analytis which deals with Brand perception and consumption in the market. The two broad studies that fall under this umbrella are 
- Brand Guidance: linked with **brand perception** in the market across various demographics 
- Category: deals with consumption metrics and patterns at brand or category level across various demograhics

S&I helps understand the whitespaces in the market and the JTBDs (Jobs to be done) for brands based on survey based metrics correlated with other tangible factors.

# Usecase
Brand Guidance (BG) - Brand Guidance is a Kantar survey-based domain that measures consumer associations with brands. At its core is the Meaningfully Different Framework (MDF), a brand equity system that quantifies equity more accurately and holistically, enabling marketers to grow brand value. The main KPI is Power, followed by Meaningful, Difference, Salience and other KPIs that support or explain it.

# Usecase definitions

This section defines all KPIs and measures available in the dataset.  
Each entry includes **definition**, **scale or calculation rule**, and a **sample query** at brand–country level.

---

## A) Equity Framework KPIs

### **Power**
- **Definition:** Prediction of volume share a brand can command based on consumer predisposition to choose the brand over others.  
- **Scale:** Within a market, Power sums to 100.  
- **Example query:** *What is the Power of Budweiser in Brazil in FY 2024?*

### **Meaning**
- **Definition:** Extent to which brands build an emotional connection and are seen to deliver against functional needs.  
- **Scale:** Indexed at 100 within a market.
- **Example query:** *Show the Meaning trend of Corona in Mexico from 2020 to 2025.*

### **Difference**
- **Definition:** Extent to which brands set themselves apart from the category by offering something others do not and by leading the way.  
- **Scale:** Indexed at 100 within a market.  
- **Example query:** *What is the Difference score of Skol in Brazil across age cohorts in 2024?*

### **Salience**
- **Definition:** How quickly and easily the brand comes to mind.  
- **Scale:** Indexed at 100 within a market.  
- **Example query:** *Compare the Salience of Heineken in Netherlands across regions in FY 2023.*

### **Premium**
- **Definition:** Prediction of price index a brand can support based on consumer predisposition to pay more for the brand than others.  
- **Scale:** Indexed at 1 within a market. 
- **Example query:** *What is the Premium score of Stella Artois in UK in Q2 2025?*

---

## B) Emotional and Functional Equity Sub-scores

### **Affinity**
- **Definition:** Emotional connection with the consumer.  
- **Scale:** Likert scale ranging from -3 to 3.  
- **Example query:** *What is the Affinity score of Corona in Mexico across gender cohorts in FY 2024?*

### **Meet Needs**
- **Definition:** Fulfillment of functional needs of the consumer.  
- **Scale:** Likert scale ranging from 1 to 7.  
- **Example query:** *Show the Meet Needs score of Budweiser in US by income cohorts in FY 2025.*

### **Unique**
- **Definition:** Extent to which brands set themselves apart from others.  
- **Scale:** Likert scale ranging from 1 to 7.  
- **Example query:** *What is the Unique score of Heineken in Germany across regions in 2024?*

### **Dynamic**
- **Definition:** Degree to which the brand is trend-setting.  
- **Scale:** Likert scale ranging from 1 to 7.  
- **Example query:** *Show the Dynamic score trend of Cass Fresh in South Korea from 2022 to 2025.*

---

## C) Funnel Metrics

### **Top of Mind**
- **Definition:** First brand to come to mind.  
- **Example query:** *What is the Top of Mind score of Quilmes in Argentina in Q1 2025?*

### **Awareness**
- **Definition:** Familiarity with a brand.  
- **Example query:** *What is the Awareness level of Skol in Brazil in FY 2024?*

### **Spontaneous Awareness**
- **Definition:** Measure of how people recall a brand without any help.  
- **Example query:** *What is the Spontaneous Awareness of Stella Artois in Belgium in FY 2023?*

### **Trial**
- **Definition:** Trial rate of the brand (ever tried).  
- **Example query:** *What is the Trial score of Corona in Mexico in FY 2024?*

### **P3M, P4W, P7D**
- **Definition:** Consumption incidence in the past 3 months (P3M), 4 weeks (P4W), or 7 days (P7D).  
- **Example query:** *What is the P3M consumption of Budweiser in US in FY 2024?*

### **Consideration**
- **Definition:** Likelihood to choose a brand next time.  
- **Scale:** 5-point Likert scale.  
- **Example query:** *What is the Consideration score of Heineken in Netherlands in Q2 2025?*

---

## D) Brand Associations and Drivers

### **Imagery**
- **Definition:** Brand associations of a consumer, based on specific imagery statements.  
- **Example query:** *What is the Imagery score for “ADDS ENERGY TO YOUR SOCIAL OCCASION” for Quilmes in Argentina in Q1 2025?*

### **In Market Facilitators (IMF)**
- **Definition:** Attribute-level factors driving choice of a brand.  
- **Example query:** *What are the IMF scores of Budweiser in US in FY 2024?*

### **Most Likely Occasion**
- **Definition:** Occasion most likely associated with beer consumption.  
- **Example query:** *What is the Most Likely Occasion score of Corona in Mexico in FY 2025?*

### **First Brand Occasion**
- **Definition:** First brand to come to mind for a given occasion.  
- **Example query:** *What is the First Brand Occasion score of Skol in Brazil for party occasions in FY 2024?*

---

## E) Perceptions of Worth and Cost

### **Worth**
- **Definition:** Worth perception of the brand.  
- **Scale:** Likert scale ranging from 1 to 3.  
- **Example query:** *What is the Worth score of Heineken in Netherlands in FY 2025?*

### **Cost**
- **Definition:** Cost perception of the brand.  
- **Scale:** Likert scale ranging from 1 to 7.  
- **Example query:** *What is the Cost score of Cass Fresh in South Korea in Q3 2024?*

---

## F) Communication Awareness

### **Total Brand Communication Awareness**
- **Definition:** Whether consumers have seen, heard, or read about the brand.  
- **Example query:** *What is the Total Brand Communication Awareness of Budweiser in Canada in FY 2023?*


# Analysis Templates roadmap

## What has been implemented?

### Analysis Template (AT) Definition
The assistant maps user queries to one of four Analysis Templates (functions).  
Each Analysis Template represents a specific scope of analysis, and parameters are always populated as lists, even when only a single value is provided.

---

### Available Analysis Templates

1. **`get_brand_highlights`**  
   - Purpose: Used when the query requests brand-level highlights, brand performance, brand deep dives, drivers of key performance indicators (KPIs), or cohort-level breakdowns of Power, Meaningful, Difference, or Salience.  
   - Triggers: Keywords such as *“brand highlights”*, *“brand performance”*, *“deep dive of brand X”*, *“drivers of power”*, *“drivers of salience”*, *“breakdown of meaningful across cohorts”*, *“cohort-level power”*.  
   - Output: Returns detailed brand-level highlights or breakdowns of brand KPIs across cohorts.  
   - Special Rule: If no KPI is mentioned, default to `analysis_requested_for_kpi = 'power'`.

2. **`get_country_highlights`**  
   - Purpose: Used when the query requests country-level highlights or overall performance without specifying any brand or KPI.  
   - Triggers: Keywords such as *“country highlights”*, *“overview of <country>”*, *“how is <country> doing”*.  
   - Output: Returns high-level summary for the requested country.

3. **`get_factual_data`**  
   - Purpose: Used for factual KPI retrieval, numerical values, cohort-based breakdowns, imagery data, time trends, comparisons, and ranking.  
   - Triggers: Keywords and intents such as *“KPI of brand X”*, *“compare power vs salience”*, *“awareness among females”*, *“imagery of brand Y”*, *“trial in Colombia”*, *“trend of power over years”*, *“ranking of brands”*.  
   - Output: Returns raw KPI values or breakdowns at the specified analysis level (brand, brand family, aggregate, global).  
   - Behavior: Always set `analysis_level` based on scope:
     - `brand_level` if specific brand(s) are requested.  
     - `brand_family_level` if brand families are requested.  
     - `country_aggregate_level` if ABI totals, megabrands, or aggregates are requested.  
     - `global_level` if zones, market maturities, or global scope are requested.

4. **`get_global_highlights`**  
   - Purpose: Used when the query requests global-level highlights, global drivers, or global performance.  
   - Triggers: Keywords such as *“global highlights”*, *“global performance”*, *“global report”*, *“global drivers”*, *“global overview”*, *“how is ABI doing globally”*.  
   - Output: Returns highlights or drivers of performance at the global level.

---

### Function Selection Priority
The selection of Analysis Template follows strict priority order:
1. If query is about **global highlights, drivers, or performance** without a country or brand → select `get_global_highlights`.  
2. If query is about **country-level highlights or overview** without a brand or KPI → select `get_country_highlights`.  
3. If query is about **brand-level highlights, deep dives, or cross-cohort KPI breakdowns** → select `get_brand_highlights`.  
4. All other cases (factual KPI requests, comparisons, rankings, imagery, cohort slicing, time trends) → select `get_factual_data`.

---

### Parameters and Extraction Rules
All extracted parameters must be passed as lists of values. When queries imply “all” values, the keyword `across` must be used.

- **year**: Extract explicit years (e.g., `'2023'`, `'2024'`, or `'2023,2024'`).  
- **period**: Extract explicit time periods. Valid values: `'Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun', 'Jul', 'Aug', 'Sep', 'Oct', 'Nov', 'Dec', 'Q1', 'Q2', 'Q3', 'Q4', 'H1', 'H2', 'FY'`.  
- **period_type**: Extract rolling or annualized indicators. Valid values: `'QTR', 'YTD', 'half year', 'full year', 'R3M', 'R6M', 'R9M', 'R12M'`. Example: “rolling 12 months” → `'R12M'`.  
- **country**: Must be selected from the fixed exhaustive list:  
  `['south korea', 'guatemala', 'vietnam', 'italy', 'brazil', 'netherlands', 'bolivia', 'germany', 'ecuador', 'nigeria', 'el salvador', 'mexico', 'honduras', 'argentina', 'china', 'peru', 'uk', 'uruguay', 'canada', 'mozambique', 'france', 'dominican republic', 'belgium', 'japan', 'us', 'colombia', 'panama', 'tanzania', 'chile', 'south africa', 'paraguay']`  
- **brand**: Extracted brand names exactly as provided in query.  
- **zone**: Must be one of `[AFR, EUR, APAC, NAZ, SAZ, MAZ]`. If query implies all zones, use `'across'`.  
- **market_maturity**: Must be one of `[M1, M2, M3]`. If query implies all maturities, use `'across'`.  
- **with_home_market**: Boolean, `true` or `false`. Use `'across'` if query requests both.  
- **kpi**: Must be selected from the exhaustive list:  
  `['power', 'meaningful', 'difference', 'salience', 'affinity_score', 'meet_need', 'unique_score', 'dynamic_score', 'consumption_past_seven_days', 'consumption_past_four_weeks', 'consumption_past_three_months', 'trial', 'awareness', 'total_spontaneous_awareness', 'heard_never_drank', 'never_seen_or_heard', 'tbca', 'top_of_mind', 'worth', 'cost', 'imf', 'consideration', 'occasion_first_brand', 'occasion_by_brand', 'last_10_purchases', 'worth_sub', 'cost_sub_attributes', 'brand_clarity', 'bip_market', 'response_percent']`  
- **sub_kpi**: Only extracted when the parent KPI requires sub-attributes (e.g., IMF, cost attributes, occasion-specific KPIs).  
- **imagery**: Specific imagery statements if explicitly mentioned (e.g., “ADDS ENERGY TO YOUR SOCIAL OCCASION”). Default to `'across'` when all are requested.  
- **analysis_level**: Must be explicitly one of `'brand_level'`, `'brand_family_level'`, `'country_aggregate_level'`, `'global_level'`.  
- **age, gender, income, region**: Cohort filters. If not mentioned, default to `'all'`.  
- **abi_competitor**: Must be one of `'ABI'` or `'COMP'` when explicitly mentioned.  
- **price_tier**: Must be one of `'core'`, `'sp'`, `'premium'`, `'value'`.  
- **life_cycle**: Must be one of `'mega brand'`, `'expansion brand'`, `'tail brand'`, `'sustain brand'`.  
- **is_global**: Boolean. `true` for global brands, `false` for local brands.  
- **is_alcohol**: Boolean. `true` for alcoholic brands, `false` for non-alcoholic brands.  
- **analysis_requested_for_kpi**: For `get_brand_highlights` only. Must be one of `'power'`, `'meaningful'`, `'difference'`, `'salience'`, `'cross cohort power'`, `'cross cohort meaningful'`, `'cross cohort difference'`, `'cross cohort salience'`.  

---

### Example Queries and Mappings

| Query | Analysis Template | Parameters |
|-------|---------------|------------|
| “Power of Corona in Mexico in 2024 Q1” | `get_factual_data` | year = ['2024'], period = ['Q1'], country = ['Mexico'], brand = ['Corona'], kpi = ['power'], analysis_level = 'brand_level' |
| “Deep dive of Brand X” | `get_brand_highlights` | brand = ['Brand X'], analysis_requested_for_kpi = 'power' |
| “Give me the global highlights for 2024” | `get_global_highlights` | year = ['2024'] |
| “Overview of Brazil” | `get_country_highlights` | country = ['Brazil'] |
| “Compare ABI power across all zones for 2025” | `get_factual_data` | year = ['2025'], period = ['FY'], zone = ['across'], analysis_level = 'global_level', kpi = ['power'], abi_competitor = ['ABI'] |
| “Imagery scores for Budweiser in Mexico, FY 2023 across age groups” | `get_factual_data` | year = ['2023'], period = ['FY'], country = ['Mexico'], brand = ['Budweiser'], age = ['across'], kpi = ['bip_market'], imagery = ['across'], analysis_level = 'brand_level' |
| “Trend of global ABI power over the last 5 years” | `get_factual_data` | year = ['across'], period = ['FY'], analysis_level = 'global_level', kpi = ['power'], abi_competitor = ['ABI'] |

---

### Behavioral Rules
- When query implies “all” values, use the keyword `'across'` explicitly.  
- For comparative KPI queries (e.g., “power vs salience”), multiple KPIs are included as a list.  
- For time comparisons (e.g., “2023 vs 2024”), both values are extracted and passed as lists.  
- For cohort slicing (e.g., “females in Brazil”), extract and populate explicitly.  
- For brand imageries, set `kpi = 'bip_market'` unless another KPI is specified.  
- Default cohort filters (`age`, `gender`, `income`, `region`) to `'all'` when not present in query.  
- When ambiguity exists and none of the highlight conditions are triggered, always default to `get_factual_data`.  


## What will be implemented?
Future implementations include the following:
- Query specific imagery or IMF by name (2025 Q4)
- Drivers of Meaning and Drivers of Difference revamped with the new aligned analysis (2025 Q4)
- Benchmarking brand kpis against price segment or other attributes (2025 Q4)
- Significance testing results for the change in power across time periods (2025 Q4)
- Meaningful, Difference and Salience contributions to Power (2025 Q4)

# Data Ingestion Roadmap

## What has been implemented?

This document buckets the ingested tables by **broad analytic function** and, for each table, defines its role and gives **explicit examples of cuts and analyses** that can be retrieved.

---

### A) Core Brand-Level KPIs

#### `BG_DIRECT_KPI_FACT`
**Role:** Brand-level KPI fact table for equity, funnel, consumption, and attitudinal scores.

**Primary keys and links:**  
- `time_id` → `TIME_DIM`  
- `brand_id` → `BRAND_DIM`  
- `cohort_id` → `COHORT_DIM`

**Measures:**  
`power`, `meaningful`, `difference`, `salience`, `affinity_score`, `meet_need`, `unique_score`, `dynamic_score`,  
`consumption_past_seven_days`, `consumption_past_four_weeks`, `consumption_past_three_months`,  
`trial`, `awareness`, `total_spontaneous_awareness`, `heard_never_drunk`, `never_seen_or_heard`,  
`total_brand_communication_awareness`, `top_of_mind`, `worth`, `cost`.

**Example cuts and analyses:**
- **Time trend:** Power of *Budweiser* in *US* by quarter for *2023–2025* using `TIME_DIM.period='Q1'..'Q4'` and `TIME_DIM.year`.  
- **Cohort slice:** Awareness of *Corona* in *Mexico* for `COHORT_DIM.gender='female'`, `COHORT_DIM.age='18–24'`, `TIME_DIM.period='FY'`, `TIME_DIM.year='2024'`.  
- **KPI comparison:** Power vs Salience for *Stella Artois* in *UK*, `FY 2024`.  
- **Consumption recency:** `consumption_past_seven_days` vs `consumption_past_three_months` for *Skol* in *Brazil*, segmented by `COHORT_DIM.income`.  
- **Funnel diagnostics:** `top_of_mind`, `awareness`, `trial` for *Quilmes* in *Argentina* by `COHORT_DIM.region`.  
- **Perception balance:** `worth` vs `cost` for *Cass Fresh* in *South Korea*, `FY 2025`.  
- **ABI vs COMP roll-up:** Aggregate brand-level Power for `BRAND_DIM.abi_comp='ABI'` vs `BRAND_DIM.abi_comp='COMP'` in *Colombia*, `FY 2024`.

---

### B) Brand Family Aggregates

#### `BG_DIRECT_KPI_BRAND_FAMILY_FACT`
**Role:** Brand-family-level Power metric with strategy and portfolio flags.

**Natural keys and links:**  
- `time_id` → `TIME_DIM`  
- `cohort_id` → `COHORT_DIM`

**Attributes:**  
`brand_family`, `country`, `abi_comp`, `price_segment`, `is_global` (boolean), `is_alcohol` (boolean), `life_cycle` (`megabrand`, `tail`, `sustain`, `expansion`)

**Measure:** `power`

**Example cuts and analyses:**
- **Portfolio lens:** Power of all brand families in *UK*, `Q1 2025`, ranked by `price_segment`.  
- **Lifecycle strategy:** Power by `life_cycle` for *Argentina*, `FY 2024`, `abi_comp='ABI'`.  
- **Global vs local:** Power split for `is_global=true` vs `is_global=false` brand families in *Brazil*, `FY 2023`.  
- **Alcoholic mix:** Power comparison for `is_alcohol=true` vs `is_alcohol=false` in *US* by `COHORT_DIM.age`.  
- **Competitive view:** Brand-family Power for `abi_comp in ('ABI','COMP')` in *Mexico*, `H1 2025`.

---

### C) Brand Imagery and Associations

#### `BG_IMAGERY_FACT`
**Role:** Brand-level imagery responses and BIP marker.

**Primary keys and links:**  
- `time_id` → `TIME_DIM`  
- `brand_id` → `BRAND_DIM`  
- `cohort_id` → `COHORT_DIM`  
- `imagery_id` → `IMAGERY_DIM`

**Measures:**  
`response_percent` (share of respondents), `bip_market` (brand imagery performance identifier)

**Example cuts and analyses:**
- **All imagery statements:** `response_percent` for all `IMAGERY_DIM.imagery` of *Heineken* in *Netherlands*, `Q3 2025`.  
- **Specific statement:** `response_percent` for *“ADDS ENERGY TO YOUR SOCIAL OCCASION”* for *Quilmes* in *Argentina*, `Q1 2025`, by `COHORT_DIM.gender`.  
- **Cohort ranking:** Top 10 imagery statements for *Corona* in *Mexico* for `COHORT_DIM.age='25–34'`, `FY 2024`.  
- **BIP tracking:** Change in `bip_market` for *Budweiser* in *Canada*, `2023` vs `2024`.  
- **Region contrast:** Imagery heatmap across `COHORT_DIM.region` for *Skol* in *Brazil*, `FY 2025`.

---

### D) Sub-KPI Attribute Layer

#### `BG_SUB_LEVEL_FACT`
**Role:** Sub-attribute values tied to a parent KPI.

**Primary keys and links:**  
- `time_id` → `TIME_DIM`  
- `brand_id` → `BRAND_DIM`  
- `cohort_id` → `COHORT_DIM`  
- `kpi_id` → `KPI_DIM`

**Measure:** `value`

**Example cuts and analyses:**
- **IMF attributes:** Sub-attributes under `KPI_DIM.kpi='imf'` (e.g., individual motivators) for *Stella Artois* in *UK*, `FY 2024`, by `COHORT_DIM.income`.  
- **Cost drivers:** `KPI_DIM.kpi='cost'` with `KPI_DIM.sub_kpi` breakdown for *Cass Fresh* in *South Korea*, `Q2 2025`.  
- **Occasion detail:** `KPI_DIM.kpi='occasion_first_brand'` with `KPI_DIM.sub_kpi='party'` for *Brahma* in *Brazil*, `FY 2024`, by `COHORT_DIM.gender`.  
- **Attribute trend:** Year-on-year change of `KPI_DIM.sub_kpi='unique_pack'` under `KPI_DIM.kpi='unique_score'` for *Budweiser* in *US*, `2022–2025`.

---

### E) Global Aggregations and Cuts

#### `BG_GLOBAL_BRANDS_KPI`
**Role:** Global brand Power with home-market inclusion control.

**Keys and links:**  
- `time_id` → `TIME_DIM`  
- `cohort_id` → `COHORT_DIM`

**Attributes and measures:**  
`global_brand`, `with_home_market` (boolean), `power`

**Example cuts and analyses:**
- **Global brand score:** Power for *Budweiser* as `global_brand`, `FY 2025`, `with_home_market=false`.  
- **Cohort global:** Global Power by `COHORT_DIM.age` for *Corona*, `Q1 2025`.  
- **Comparison:** *Stella Artois* global Power `with_home_market=true` vs `false`, `FY 2024`.

---

#### `BG_GLOBAL_MARKET_MATURITY_KPI`
**Role:** Global Power by market maturity with competitive and portfolio flags.

**Keys and links:**  
- `time_id` → `TIME_DIM`  
- `cohort_id` → `COHORT_DIM`

**Attributes and measures:**  
`market_maturity` (`M1`, `M2`, `M3`), `abi_comp`, `life_cycle` (`megabrand`, `tail`, `sustain`, `expansion`), `price_segment`, `power`

**Example cuts and analyses:**
- **Maturity view:** Power across `M1,M2,M3`, `FY 2024`, `abi_comp='ABI'`.  
- **Lifecycle within maturity:** Power by `life_cycle` inside `market_maturity='M2'`, `FY 2025`.  
- **Price tier lens:** Power by `price_segment` across `M1,M2,M3`, `Q2 2025`.  
- **Competitive maturity:** `abi_comp='ABI'` vs `abi_comp='COMP'` for `M3`, `FY 2024`.

---

#### `BG_GLOBAL_ZONE_KPI`
**Role:** Global Power by geographical zone with competitive and portfolio flags.

**Keys and links:**  
- `time_id` → `TIME_DIM`  
- `cohort_id` → `COHORT_DIM`

**Attributes and measures:**  
`zone` (`NAZ`, `MAZ`, `SAZ`, `AFR`, `APAC`, `EUR`), `abi_comp`, `life_cycle`, `price_segment`, `power`

**Example cuts and analyses:**
- **Zone comparison:** Power across `NAZ, MAZ, SAZ, AFR, APAC, EUR`, `FY 2024`, `abi_comp='ABI'`.  
- **Zone × price segment:** Power by `price_segment` within `EUR`, `Q1 2025`.  
- **Zone × lifecycle:** Power by `life_cycle` within `APAC`, `FY 2023`.  
- **ABI vs COMP by zone:** `abi_comp` split for each zone, `FY 2025`.

---

### F) Dimensions and Reference Data

#### `BRAND_DIM`
**Role:** Brand reference attributes used for joins and portfolio filters.  
**Columns:** `brand_id`, `brand`, `country`, `abi_comp`, `price_segment`, `is_global` (boolean), `is_alcohol` (boolean), `life_cycle`.

**Example uses:**
- Filter *global brands* with `is_global=true` before aggregating Power in `BG_DIRECT_KPI_FACT`.  
- Compare `abi_comp='ABI'` vs `abi_comp='COMP'` across brands in *Colombia*, `FY 2024`.  
- Segment brand-level KPIs by `price_segment` or `life_cycle`.

---

#### `COHORT_DIM`
**Role:** Cohort reference for demographic and regional slicing.  
**Columns:** `cohort_id`, `age`, `gender`, `income`, `region`.

**Example uses:**
- Gender split of `awareness` for *Corona* in *Mexico*, `FY 2024`.  
- Income-tier comparison of `trial` for *Skol* in *Brazil*, `Q3 2025`.  
- Regional heatmap for `salience` in *Argentina*, `FY 2025`.

---

#### `IMAGERY_DIM`
**Role:** Lookup for imagery attributes.  
**Columns:** `imagery_id`, `imagery`.

**Example uses:**
- Map `imagery_id` to statement strings for reporting top imagery for *Heineken* in *Netherlands*.  
- Filter to a specific statement such as *“ADDS ENERGY TO YOUR SOCIAL OCCASION”*.

---

#### `KPI_DIM`
**Role:** Lookup for KPI and its sub-attributes.  
**Columns:** `kpi_id`, `kpi`, `sub_kpi`.

**Example uses:**
- Retrieve sub-attribute lists for `imf`, `cost`, `worth`, `occasion_first_brand`, `occasion_by_brand`.  
- Join to `BG_SUB_LEVEL_FACT` to label rows for visualization and ranking.

---

#### `TIME_DIM`
**Role:** Canonical calendar and periodization reference.  
**Columns:** `time_id`, `period_type` (`QTR`, `YTD`, `half year`, `full year`, `R3M`, `R6M`, `R9M`, `R12M`), `period` (`Jan`..`Dec`, `Q1`..`Q4`, `H1`, `H2`, `FY`), `year`.

**Example uses:**
- Construct quarterly trends (`Q1–Q4`) for *2019–2025*.  
- Build rolling windows using `period_type='R12M'` for `power` trend lines.  
- Align `FY` comparisons across years for cohort-sliced KPIs.

---


## What will be implemented?
- Monthly level Power and MDS along with other KPIs to be ingested in 2025 Q4
- Significance test numbers for Power comparison across periods to be ingested in 2025 Q4 
