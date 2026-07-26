# 🌍 Environmental Sustainability Metrics Dashboard

**A global analysis of land, emissions, energy, water, and biodiversity trends built with Power BI and the World Bank's World Development Indicators (WDI).**

Data Analytics Capstone Project | AnalystLab Africa — Batch B Internship
👤 Prepared by: **Nwafor Chinaza**


---

## Project Overview

Environmental sustainability is one of the most pressing global challenges of the current decade  spanning deforestation, greenhouse gas emissions, the transition to renewable energy, freshwater scarcity, and biodiversity protection. This project applies a complete data analytics workflow — **Ask, Prepare, Process, Analyze, Share, Act**  to World Bank environmental data covering **217 countries**, **23 indicators**, and **over 60 years of observations**, resulting in a two-page interactive Power BI dashboard that tells an honest story: **The Challenge** (global decline) and **Bright Spots** (measurable progress).

---

## Objective

This analysis set out to answer three core questions:

1. Which countries and regions are furthest along in environmental decline, and what does that decline look like across land, emissions, and water metrics?
2. Which countries are demonstrating measurable environmental progress, and what distinguishes them from those still declining?
3. What actionable recommendations can be drawn from these patterns for policymakers, investors, and development organizations such as AnalystLab Africa's partner network?

---

## Dataset

**Source:** [World Bank — World Development Indicators (WDI)](https://datatopics.worldbank.org/world-development-indicators/)

The WDI bulk download contains six files. Each was reviewed in Excel to understand its structure before deciding what was relevant to this analysis:

| File | Used? | Purpose |
|---|---|---|
| `WDICSV.csv` | ✅ Primary dataset | Indicator values by country, indicator, and year (1960–2025) |
| `WDICountry.csv` | ✅ Enrichment | Region and Income Group classification per country |
| `WDISeries.csv` | Reference only | Indicator metadata and definitions |
| `WDIfootnote.csv` | Not used | Country-specific data caveats |
| `WDIcountry-series.csv` | Not used | Indicator-coverage map per country |
| `WDIseries-time.csv` | Not used | Notes on indicator definition changes over time |

**23 environmental indicators** were selected across five analytical pillars: **Land, Emissions, Energy, Water, and Biodiversity.**

---

## Tools Used

- **Excel** — initial review of raw source files
- **Power Query (Power BI)** — data cleaning and transformation
- **Power BI Desktop** — data modeling (DAX), dashboard design, interactivity
- **PowerPoint / Word** — documentation and reporting

---

## Repository Structure

```
├── README.md
├── Environmental_Sustainability_Metrics.pbix        # Power BI dashboard file
├── Environmental_Sustainability_Report_Nwafor_Chinaza.pdf   # Final written report
├── Environmental_Sustainability_Report_Nwafor_Chinaza.docx  # Editable version
├── screenshots/
│   ├── Enviromental_Sustainable_Metrics_dashboard_1.png     # "The Challenge" page
│   └── Enviromental_Sustainable_Metrics_dashboard_2.png     # "Bright Spots" page
└── demo_video_link.md                                # Link to recorded walkthrough
```

 **Note:** The full raw dataset is not included in this repository due to file size constraints, per project guidelines. It can be downloaded directly from the [World Bank WDI portal](https://datatopics.worldbank.org/world-development-indicators/) (WDI_CSV.zip, under Bulk Downloads).

---

## Data Cleaning Process

All cleaning was performed in Power Query and is fully documented in the final report (Section 3). Summary:

| Stage | Row Count | Action Applied |
|---|---|---|
| Raw rows (23 indicators, wide format) | 6,095 | Filtered to selected indicators |
| After unpivot (long format) | 402,270 | Converted wide → long format |
| After removing blank values | 189,016 | Removed rows with no recorded value |
| **After removing non-country aggregates (final)** | **153,589** | Joined with `WDICountry.csv` (Inner Join) |

Key steps included: promoting headers, filtering to 23 indicators, unpivoting 66 year-columns into a single Year/Value pair, removing rows with no recorded data (rather than fabricating zeros), and merging with country metadata to exclude World Bank regional aggregates (e.g., "Sub-Saharan Africa," "World") from country-level analysis.

---

## Dashboard Preview

### Page 1 — The Challenge
*Global snapshot of environmental decline: five KPI cards, forest area decline, CO2 emissions increase, and the 15 most water-stressed countries.*

![The Challenge Dashboard](https://github.com/Lorietta25/AnalystLab-Week-8-Internship_Capstone_Project/blob/main/Environmental%20Sustainable%20Metrics%20dashboard%201.png?raw=true)

### Page 2 — Bright Spots
*Countries demonstrating measurable positive change: renewable energy growth, forest area gain, and leading protected-area coverage.*

![Bright Spots Dashboard](https://github.com/Lorietta25/AnalystLab-Week-8-Internship_Capstone_Project/blob/main/Environmental%20Sustainable%20Metrics%20dashboard%202.png?raw=true)

**Fully interactive:** synchronized **Year**, **Region**, and **Income Group** slicers filter both pages simultaneously. Download the `.pbix` file above to explore live.

---

## Key Findings

**Global Snapshot (The Challenge):**

| Indicator | Value |
|---|---|
| Avg. Forest Area | 32.61% of land area |
| Avg. CO2 Emissions per Capita | 5.04 t CO2e |
| Avg. Renewable Energy Share | 30.73% |
| Median Water Stress Level | 12.09% |
| Avg. Protected Areas | 13.07% of territory |

**Change Over Time (Bright Spots):**

| Indicator | Value |
|---|---|
| Avg. Renewable Energy Change | -3.79% |
| Avg. Forest Area Change | -1.34% |
| Avg. Protected Area Growth | +5.47% |

---

## Insights

1. **The Wealth–Emissions Paradox** — High-income countries emit 26x more CO2 per capita than low-income countries, yet are the group successfully growing renewable energy share — while low-income countries, despite a far higher current renewable share, are losing ground fastest as they industrialize.
2. **Sub-Saharan Africa's Disproportionate Vulnerability** — The region shows the steepest renewable energy and forest area decline of any group tested, despite contributing the least to global emissions.
3. **Recent-Decade Stabilization** — Restricting the analysis to 2010–2023 shows a markedly smaller rate of decline than the full 1990–2025 window, suggesting recent policy interventions may be having a stabilizing effect.
4. **The Desalination–Emissions Link** — Gulf states topping the water-stress rankings are frequently the same nations topping the CO2-increase rankings, linked by energy-intensive desalination.
5. **Governance as a Predictor of Forest Outcomes** — Countries with centralized conservation policy (Bhutan, Vietnam) show forest gains, while countries facing decentralized agricultural pressure show the steepest losses — suggesting policy design, not just income, shapes outcomes.

*(Full WHAT → WHY → WHY → SO WHAT breakdown for each insight is available in the final report, Section 6.)*

---

## Recommendations

1. Target renewable energy investment toward low-income countries, not just high emitters.
2. Prioritize Sub-Saharan Africa for targeted environmental support.
3. Study and replicate centralized reforestation policy models (e.g., Bhutan, Vietnam).
4. Decouple water security from emissions via renewable-powered desalination in high-stress regions.
5. Continue monitoring recent trends rather than assuming stabilization is permanent.

---

##  How to Use This Repository

1. Download `Environmental Sustainability Metrics.pbix`.
2. Open in **Power BI Desktop** (free download from Microsoft).
3. Use the **Year**, **Region**, and **Income Group** slicers on either page to explore the data interactively.
4. Refer to the full Docx report for methodology, cleaning steps, and detailed insights.


---

## Acknowledgments

This project was completed as part of the **AnalystLab Africa** Data Analytics Internship (Batch B, 1st June – 1st August). Thank you to the AnalystLab Africa team for the mentorship and structure throughout this internship.

**#AnalystLabAfrica**

---

 **Connect with me:** [Add your LinkedIn profile link here]
