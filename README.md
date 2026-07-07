Power BI + Excel analysis of workforce attrition and AI exposure risk
# HR Attrition & AI Exposure Risk Analytics

Which roles are losing employees to attrition AND exposed to AI-driven disruption at the same time?

Most attrition dashboards stop at "who's leaving." This project goes a step further — cross-referencing attrition data with AI exposure scores by job role to flag where a company faces *compounded* workforce risk: high turnover in roles that are also the most likely to be automated.

![Risk Matrix Dashboard]<img width="1170" height="666" alt="image" src="https://github.com/user-attachments/assets/49d54f51-ff21-46d5-a048-c7238783863b" />



## The Business Question

HR teams typically treat attrition and AI/automation risk as separate problems — one owned by retention teams, the other by workforce planning. This project combines both into a single view, so a leadership team can ask: *"Where are we bleeding people from roles we're about to need fewer of anyway — and where are we bleeding people from roles we can't afford to lose to automation?"*



## What's Inside

Power BI Dashboard (3 pages)
- Executive Overview — KPI summary, attrition-rate-vs-target gauge, AI risk category breakdown, department-level attrition
- Attrition Deep-Dive — tenure, overtime, job satisfaction, and income drivers of attrition, plus a Key Influencers visual to surface what actually predicts attrition
- Workforce Risk Matrix — a quadrant scatter plotting AI Exposure Score against Attrition Rate by job role, sized by headcount, with benchmark lines splitting roles into risk zones

## Excel Workforce Strategy Model
- 15,000-row dataset (`tbl_AI_Jobs`) analyzed with dynamic array formulas (`SLOPE` + `FILTER`)
- A live Excel Data Table for what-if salary-impact modeling under different AI exposure scenarios
- A weighted Decision Matrix (min-max normalized, rank-scored) prioritizing industries for reskilling investment
- A built-in data-quality profile sheet — row counts, missing-value checks, unique-value validation

---

## Data Model
HR_Data (1,470 employees) 
├── joined on JobRole
AI_Exposure_Lookup (9 roles)


Two tables, one relationship — kept deliberately simple so the model stays interpretable, with the analytical depth coming from DAX measures rather than schema complexity.

---

## Key Insights

1. **Sales Representative and Sales Executive roles carry the highest combined risk** — both sit in the top-right quadrant of the Risk Matrix, meaning above-average attrition *and* above-average AI exposure. This is exactly the blind spot a standard attrition-only dashboard would miss.
2. **Overtime is the strongest single driver of attrition** in this dataset — employees working overtime show a markedly higher attrition rate than those who don't, based on the Key Influencers analysis.
3. **Retail shows the highest reskilling urgency** in the Excel workforce model, driven by a combination of high AI exposure score and low current investment in projected salary protection.

---

## Tech Used
- Power BI: DAX (weighted risk indexing, rank-based measures, dynamic reference-line benchmarking), synced slicers, bookmarks, Key Influencers AI visual
- Excel: dynamic arrays, Data Tables (what-if analysis), weighted decision matrices, conditional formatting, native Slicers, data-quality validation

---

## Files
- [`HR_Attrition_and_AI_Exposure_Analytics.pbix`](HR_Attrition_and_AI_Exposure_Analytics.pbix) — Power BI dashboard
- [`FutureOfWorkInTheAgeOfAI.xlsx`](FutureOfWorkInTheAgeOfAI.xlsx) — Excel workforce strategy model

*Note: some Excel formulas use Microsoft 365 dynamic array functions and require Excel 2021+ or Microsoft 365 to calculate correctly.*
