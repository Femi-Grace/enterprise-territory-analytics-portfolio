# enterprise-territory-analytics-portfolio
Production data pipelines, geospatial BI architectures and statistical allocation models driving enterprise resource planning and public sector reorganisation.
# Enterprise Territory Realignment, Resource Optimization & Predictive Outreach Analytics
### Production Data Engineering, Analytical Resource Modelling & Geospatial BI Architecture

**Author:** Prasema Femi Grace  
**Core Stack:** `SQL` • `SSIS` • `FME` • `Power BI (DAX / Power Query)` • `Power Automate` • `Excel (VBA / Statistical Modelling)` • `Microsoft Copilot`  
**Domain Focus:** Territory Design, Resource Allocation, Fiscal Year Readiness, White-Space Segmentation & Scenario Modelling

---

## Executive Overview

This repository documents the production data pipelines, analytical allocation models, and automated Power BI ecosystems I designed and delivered in my roles at **Surrey County Council** and **Oakleaf**. 

Across both organisations, I moved leadership away from static historical spreadsheets by building automated ETL pipelines and decision-support tools—applying **supply-to-demand indexing, outlier benchmarking, geospatial white-space segmentation, and what-if scenario modelling** to eliminate resource misallocation, guarantee Day-1 fiscal readiness, and drive measurable operational ROI.

---

## Experience 1: Surrey County Council — Assistant Data Specialist

### Organisation & Role Overview
Surrey County Council (SCC) is one of the UK's largest local authorities, managing public services, education, fire and rescue, and community infrastructure across a workforce of **15,000+ employees** and multi-million-pound public budgets. 

Working within the central **People, Data & Operations Analytics Team** in a complex, matrixed environment, I partnered directly with Finance, HR, Education, Customer Services, and Fire & Rescue leaders. My core responsibility was to bridge raw ERP extraction (`Microsoft Unit4`) with executive decision-making—untangling enterprise datasets and architecting an equitable, data-driven structural split across East and West territories ahead of a major Local Government Reorganisation (LGR).

### 1. The Operational Challenge
During the **Local Government Reorganisation (LGR)**, the council was mandated to split a unified county-wide structure into two distinct regional operating entities (**East and West territories**) ahead of the **April 1, 2027 fiscal year**.

A simple geographical split (dividing headcount and budgets strictly by existing postcode boundaries) risked severe **structural misallocation**:
* **Centralised Overhead Bloat:** Shared corporate functions, specialist fire units, and senior educational advisors were registered at central headquarters in the West, artificially inflating West headcount while hiding the fact that up to 60% of their day-to-day operational work actually served the East.
* **Legacy Schema Corruption:** High-volume HR and financial records inside **Microsoft Unit4** contained unclosed positions, multi-occupancy anomalies, and orphaned cost centres that threatened budget integrity on Day 1.
* **Asymmetric Service Demand:** Population growth, Special Educational Needs (SEN) density, fire incident frequency, and customer service case volumes were unevenly distributed across the county.

### 2. Data Architecture & Automated Validation Pipeline
To establish a single source of truth across departments, I engineered a multi-stage extraction and integrity pipeline:

1. **Automated Ingestion (`SSIS` & `FME`):** Built automated ETL jobs to extract raw position, payroll, school finance, and operational dispatch logs from **Microsoft Unit4** into a structured staging environment.
2. **Programmatic Integrity Auditing (`SQL` & `Excel VBA`):** Authored parameterized SQL validation queries and automated VBA auditing routines to isolate and resolve:
   * **Multi-Occupancy & Ghost Positions:** Flagged `Position_ID` records exceeding `1.0 FTE` allocation or carrying null funding strings.
   * **Cross-Border Service Leakage:** Joined employee base locations against 24-month operational activity logs (school visits, fire station dispatches, customer service ticket origins) to trace where work was actually happening versus where staff were administratively registered.
3. **Dual-Tag Schema Mapping:** Engineered a bridging dimension table (`Legacy_Cost_Centre` -> `New_Entity_Key: East | West`) to preserve historical year-over-year trend reporting across the April 1, 2027 cutover.

### 3. Analytical Methodology & Data Logic
To ensure resources—including **frontline firefighters, customer service agents, school funding pools, and core operational budgets**—were allocated where demand was highest rather than where legacy budgets sat, I applied three core analytical frameworks:

#### A. Supply-to-Demand Ratio Indexing (Utilisation vs. Capacity)
* **The Mindset:** Instead of assuming East and West needed equal budgets, I tied resource allocation directly to real-world operational triggers. For every local ward and postcode sector, I built a composite **Demand Score** combining weighted pupil and SEN headcounts, customer service inbound case volumes per 1,000 residents, and historical emergency fire incident frequency.
* **How It Caught Misallocation:** By comparing current assigned staffing and budget (Supply) against each area's true operational workload (Demand), I ranked every micro-territory by its **Allocation Efficiency**. Areas with high resource supply and low demand immediately stood out as over-resourced legacy pockets, while high-demand zones with thin staffing were flagged for immediate rebalancing.

#### B. Peer-Group Outlier Benchmarking (Variance & Anomaly Detection)
* **The Mindset:** Comparing a small rural primary school or fire station against a large urban hub creates misleading averages. To audit school finance and operational unit variances fairly, I grouped comparable operational units into strict peer cohorts (such as primary schools of similar pupil size, or urban versus rural fire stations) and measured how far each unit deviated from its group median.
* **How It Caught Misallocation:** Using median-based variance benchmarking (which prevents extreme edge cases from skewing the baseline), any cost centre sitting significantly outside its peer group norm was automatically flagged in the audit layer. This allowed finance leads to separate genuine structural need from historical over-funding or coding errors.

#### C. Activity-Based Fractional FTE Weighting
* **The Mindset:** Shared corporate and specialist teams do not stop at a line on a map. Rather than forcing a binary "East or West" label onto staff who support both regions, I treated headcount and budgets as fractional capacity driven by actual service delivery.
* **How It Caught Misallocation:** By measuring the exact proportion of historical tickets, school visits, and dispatches delivered to East versus West postcodes over two years, I assigned proportional FTE split ratios (for example, 40% East / 60% West) to shared roles—ensuring neither new entity was unfairly burdened with central overhead costs.

### 4. "Fast Start" Fiscal Readiness & Executive Visualisation
To prepare leadership ahead of the **April 1, 2027 financial year**, I implemented a **Shadow-Running Reporting Framework** inside **Power BI**:
* **Choropleth Supply-Demand Heatmaps:** Overlaid ward-level efficiency scores against physical asset locations (fire stations, customer hubs, schools), allowing directors to spot spatial imbalances in seconds.
* **Sankey Funding & Headcount Flow Visuals:** Mapped how unified legacy funding pools split into East and West buckets, providing full audit transparency for the People & Change Directorate.
* **Dynamic Boundary & Budget Sliders (DAX What-If Parameters):** Enabled senior directors to test boundary adjustments and shared-service split ratios live during executive planning sessions, immediately recalculating net fiscal impact across both entities.

---

## Experience 2: Oakleaf — Data Engineer

### Organisation & Role Overview
Oakleaf is a leading Surrey-based mental health charity headquartered in Guildford, delivering vocational training, social inclusion programmes, and wellbeing support to vulnerable adults across the region.

Operating as a **Data Engineer** within a lean, fast-paced Digital Transformation & Strategic Operations unit alongside the CEO, Fundraising Lead, and Community Outreach Coordinators, I replaced manual spreadsheet bottlenecks with automated data pipelines and spatial intelligence tools. My core focus was transforming fragmented CRM data into a county-wide outreach and patient acquisition engine while enabling non-technical staff to self-serve insights using Power BI and Microsoft Copilot.

### 1. The Operational Challenge
Leadership faced two primary operational bottlenecks when scaling outreach programmes across Surrey:
* **Siloed Manual Reporting:** Patient referral, demographic, and engagement records sat inside an unintegrated CRM, requiring hours of manual CSV extraction and cleaning before any strategic insight could be generated.
* **Blind-Spot Outreach Allocation:** Without county-wide spatial visibility, outreach programmes and fundraising campaigns relied on historical intuition rather than empirical demand patterns, risking over-saturation in central Guildford while missing high-need populations in outer Surrey boroughs.

### 2. Automated ETL & Governance Architecture
I architected a zero-touch, GDPR-compliant automated data pipeline leveraging the Microsoft Power Platform:
# Oakleaf Data Engineering & Spatial Outreach Architecture
## Detailed Technical Implementation & Analytical Frameworks

#### A. Market Penetration & White-Space Segmentation
- **The Mindset:** Looking only at internal CRM data shows where current patients live, not where unreached people who need support live. To uncover true growth opportunities, I cross-referenced Oakleaf's internal Surrey postcode referral counts against external UK ONS Census demographic indicators and Indices of Multiple Deprivation (IMD).
- **How It Drove Outreach:** By comparing expected community need against actual referral volume across every Surrey district, I isolated High-Priority White-Space Territories—areas showing high socioeconomic and mental health need indicators alongside low current engagement. Leadership used these exact targets to expand outreach into underserved outer boroughs.

#### B. Travel-Friction & Accessibility Modelling (Distance-Decay Analysis)
- **The Mindset:** High drop-off rates in outer Surrey were not due to a lack of need, but physical travel barriers. Using point-to-point geographic distance mapping between patient postcode centroids and Oakleaf's Guildford hub, I analysed how referral and attendance rates changed as travel distance increased.
- **How It Drove Outreach:** The data revealed a sharp drop-off in engagement once residents lived more than 12 miles from the central hub. This gave leadership an evidence-backed business case to launch localized pop-up clinics and digital-first support programmes in distant boroughs rather than expecting all patients to travel to Guildford.

#### C. Outreach Resource & ROI Scenario Modelling
- **The Mindset:** Outreach teams and fundraising budgets are finite, so leadership needed a way to test where every extra hour or pound would generate the highest return before committing resources.
- **How It Drove Outreach:** I built an interactive Scenario Modelling Engine in Excel and Power BI using DAX `WHATIF` parameters. Leadership could adjust field outreach hours deployed per Surrey borough, targeted campaign spend by postcode cluster, and projected funnel conversion rates (`Initial Outreach -> Active Patient -> Long-Term Engagement`). The model dynamically forecasted expected patient growth and fundraising yield per pound spent, shifting resources toward the highest-performing geographic segments.

### 3. AI, Copilot & Self-Service Enablement
To ensure non-technical outreach coordinators and executive directors could consume insights without bottlenecking data engineering capacity:
- **Copilot-Ready Semantic Layer:** Configured explicit synonyms, clean measure descriptions, and hierarchical date/geography drill-downs inside Power BI so staff could use Microsoft Copilot / Q&A to query data in plain English (e.g., *"Show referral growth in East Surrey districts over the last two quarters"*).
- **Accelerated Script & Formula Engineering:** Utilized Microsoft Copilot alongside Power Query (M) and DAX to streamline complex postcode validation logic and time-intelligence calculations (`SAMEPERIODLASTYEAR`, rolling 90-day engagement averages), reducing development turnaround time by over 40%.
