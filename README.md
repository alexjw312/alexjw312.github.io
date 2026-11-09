# Jinwook (Alex) Jung · Portfolio

Source for my portfolio site: https://alexjw312.github.io

A single HTML file. Charts on the case-study pages use synthetic data. This repository contains no company code or data.

---

## 1. Obigo (Seoul)
**Automated Reporting with a Bounded LLM Layer**
*Data & AI Intern · June – August 2026*

### Context
- An at-home car-maintenance service from Obigo's group launched inside a major Korean insurer's app in May 2026
- The insurer received a weekly operations report covering traffic, reservations, and issues

### Problem
- One person collected the data by hand, pasted it into PowerPoint, and emailed the report every week
- Problems only surfaced in the next week's report
- Each new partner would have added the same manual work again

### My Contribution
- Designed and built a five-step pipeline: collect → compute → write → check → deliver
- Pulled GA4 event exports and service data from BigQuery, keeping raw pulls as NDJSON so metrics can be recomputed without re-querying
- Computed every KPI, funnel rate, interval, and chart value in Python (pandas, NumPy) before any LLM call
- Used the Claude API only to write short text in fixed slots (title, status, evidence, priority) from the finished metrics
- Checked generated text against banned-phrase rules; an API failure or rule violation falls back to template sentences built from the same metrics
- Rendered a 4-page weekly PDF from HTML templates, with pre-send checks on page count, missing glyphs, chart values, and section order
- Delivered daily reports to Telegram and ObigoChat and weekly reports by email, logging every send
- Built a restart-safe scheduler (APScheduler) that tries 8 times a day, saves pending dates, and alerts when 2 or more days fall behind
- Built the report formats, delivery tests, and fallback paths on dummy data while data access was delayed

### Analysis in the Report
- A 7-step reservation funnel to find where users drop off
- Week-over-week change split into traffic and conversion effects
- Wilson intervals to withhold conclusions on small samples (e.g., 0 of 6 users → 0–39%)
- Next-week outlook shown as an 80% prediction interval
- License-plate to vehicle-model mapping success tracked as a data quality KPI

### Output
- 16/16 daily and 2/2 weekly reports delivered in the first 16 days of unattended operation (from July 21, 2026)
- 1 late-data day recovered automatically by retry
- Reporting moved from weekly and manual to daily and automatic; adding a delivery channel became a configuration change

### Also at Obigo
- Audited AI-generated tags on Pickle, Obigo's in-car podcast platform: analyzed tag frequency and distribution across 5 categories to find over-used, rarely used, and skewed tags, and delivered the findings as an HTML report built in R

### Skills Used
- Python (pandas, NumPy), BigQuery SQL, GA4
- Claude API, output validation, fallback design
- APScheduler, HTML-to-PDF rendering, SMTP and messaging APIs

### Why It Matters
- Code owns the numbers and the LLM owns the wording, so the report stays correct and on time even when the model or the data fails
- Next step: automatically check that every number in generated text matches the computed metrics

---

## 2. AI-Omics Lab (Purdue University)
**Scientific Data Engineering & Backend Validation**
*Project Team Member · September 2025 – April 2026*

### Context
- AI-Omics research team (Advisor: Dr. W. Andy Tao)
- Disease biomarker ML research using high-resolution mass spectrometry data

### Problem
- Large-scale scientific data with different structures by experiment
- ML model training is not possible without validated data
- Reproducibility is a core constraint in research

### My Contribution (Core Work)
- Backend data pipeline (Python): file I/O, modular code design, exception handling
- Automated experimental data verification using rule-based validation logic
- Standardized data structures prior to ML training through scientific data processing
- Collaboration: understanding a Django-based backend structure
- Collaboration using Git/GitHub (feature branching, rebase)

### Output
- Designed and implemented backend validation logic to ensure the integrity of mass spectrometry data
- Enabled a stable preprocessing pipeline and improved reproducibility of AI-based omics research

### Skills Used
- Python (Core, backend logic)
- Django, data validation
- Git/GitHub, collaborative development

### Why It Matters
- Learned that ensuring data reliability before modeling is one of the most important data science competencies in real-world research environments

---

## 3. University Hospital Limerick (Ireland)
**Healthcare & Epidemiological Data Analytics**
*Research Intern · May – July 2025*

### Context
- Analysis of over 15 years of healthcare data
- Comparative analysis across 33 EU countries

### Problem
- Heterogeneous healthcare data structures across countries and regions
- Required interpretation from a public health perspective rather than simple statistics

### My Contribution
- Data wrangling and integration using tidyverse (dplyr, tidyr, forcats)
- Epidemiological analysis using age standardization and age-standardized death rates (ASDR)
- Disease classification based on ICD-10 codes
- Geospatial and interactive analytics using sf, leaflet, and giscoR
- Dashboard development using Plotly and Crosstalk

### Reproducible Research
- Quarto-based analytical reports

### Output
- Time-series and map visualizations of hospitalization and mortality rates for selected EU countries
- Supported researchers’ data accessibility and decision-making

### Skills Used
- R, tidyverse
- Epidemiology
- GIS
- Dashboarding

### Why It Matters
- Converted complex healthcare data into accessible formats
- Enabled cross-country comparisons of healthcare indicators using a consistent standard
- Provided dashboards that directly support research and decision-making

---

## 4. Other Data Operations Experience

### Applied Data & Operational Experience
**ACT Foundation (Seoul)**
*Intern · June – August 2024*

- Managed an asset database with over 1,000 records
- Improved data accessibility and operational efficiency
- Gained hands-on experience in data operations within a nonprofit organization

### Operational Data in the Military
**Republic of Korea Air Force**
*Mandatory military service · July 2021 – April 2023*

- Managed detailed operational data on fighter-jet flights and missions
- Coordinated with 30+ team members to complete missions under time pressure

### Key Takeaways
- Developed an understanding of practical, real-world data management and operations
