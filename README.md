# U.S. 1992 Presidential Elections — Power BI Dashboard

Interactive Power BI dashboard analyzing the 1992 U.S. presidential election at the county level, crossing electoral results with socioeconomic indicators. Final project of the Data Analytics course at Coderhouse.

## Overview

The dashboard explores the 1992 U.S. presidential election — Bill Clinton vs. George H. W. Bush — through the lens of the 2,413 counties for which socioeconomic data were available. The goal is not only to visualize who won where, but to examine how income, poverty, population density, veteran share, and other social variables correlate with the electoral outcome at the county level.

The workbook uses a **star-schema data model** with dimension tables (`ID_Estado`, `ID_Condado`, `ID_Ganador`) and a central fact table, allowing filters and slicers to propagate cleanly across all pages. Column names, categorical values, and regional groupings were cleaned and translated in **Power Query** before loading.

## Data

- **Observations:** 2,413 U.S. counties across 43 states
- **Election:** 1992 U.S. presidential election (Clinton vs. Bush; Perot's vote share is included in the data but he did not win any county)
- **Socioeconomic variables:** median age, mean savings, per capita income, poverty rate, veteran share, female share, population density, share of population in nursing homes, crime index per capita
- **Electoral variables:** winner by county, "Clinton win" boolean

## Dashboard Structure

The report has **four pages** connected by a navigation menu on the cover.

### 1. Cover (`Portada`)
Landing page with buttons that navigate to the three analytical pages.

![Cover page](docs/screenshots/01-portada.png)

### 2. Presidential Elections (`Elecciones presidenciales`)
Overview of electoral results:
- KPI cards for states analyzed (43), states won by Bush (14) and states won by Clinton (29)
- Choropleth map of the U.S. colored by state winner
- State-level breakdown table showing, for each state, counties analyzed, counties won by Bush, and counties won by Clinton
- Region and State slicers with cross-filtering

Aggregate result: of 2,413 counties, Bush won 1,220 and Clinton won 1,193 — a much closer race at the county level than the electoral college outcome suggests.

![Presidential Elections page](docs/screenshots/02-elecciones-presidenciales.png)

### 3. Economic Indicators (`Indicadores Económicos`)
Cross-analysis of electoral outcome and economic variables:
- KPI cards for regions analyzed, average poverty rate (16.04%), and average household income (~USD 16.4k)
- Area chart of household income by region
- Bar chart of poverty rate by region, with color-coded regional legend
- Detailed state-level table combining region, mean savings, household income, and winner

![Economic Indicators page](docs/screenshots/03-indicadores-economicos.png)

### 4. Social Indicators (`Indicadores Sociales`)
Cross-analysis of electoral outcome and social variables:
- KPI cards for counties analyzed (2,413), average age (34), and average population density (178.69)
- Line chart showing the effect of population density on voting patterns, separated by winner
- Line chart of the share of population in nursing homes by region
- Pie chart of gender distribution
- Treemap of veteran share by region

![Social Indicators page](docs/screenshots/04-indicadores-sociales.png)

## Techniques

- **Data modeling** — star schema with three dimension tables and one fact table, enabling clean filter propagation
- **Power Query** — column renaming and translation, categorical recoding, regional grouping
- **DAX measures** — KPIs (counts of counties/states won by each candidate, regional averages of socioeconomic variables) used across all pages
- **Cross-page filtering** — Region and State slicers applied consistently for coherent drill-down
- **Multiple visualization types** — choropleth map, bar and line charts, area chart, pie chart, treemap, KPI cards, and detailed tables

## Files

- `Elecciones_EEUU_1992.pbix` — Power BI report file (open with Power BI Desktop)
- `Elecciones_EEUU_1992.xlsx` — Underlying dataset with the fact and dimension tables
- `docs/screenshots/` — Screenshots of the four dashboard pages

## Course

Final project — *Data Analytics*, Coderhouse (June–October 2023). Individual project.

## Data Source

County-level 1992 U.S. presidential election results and socioeconomic indicators. Compiled from publicly available electoral and census sources for coursework purposes.
