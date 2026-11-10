# Issue #19 — Global sources for the World map's metrics

**Issue:** https://github.com/Visualize-Policy/research-writing-admin/issues/19

Pick the exact data series (and years) for each World-map metric, compare OECD against WHO/World
Bank figures for a handful of countries, hand-collect coverage % and elective wait times into
`writing/019-world-data/hand_collected.csv`, and write plain-language descriptions of every metric.
Programming counterpart: wtdickens/health-dashboard#62.

---

| Metric | Source | Series Code | Years Available | Recommended Year | Countries Covered | Justification for Recommended Year | Definition |
|---|---|---|---|---|---|---|---|
| Life expectancy at birth | World Bank WDI | `SP.DYN.LE00.IN` | 1960–2024 | 2024 | 217 countries | Most recent data with widest range of countries | The average number of years a newborn is expected to live if mortality patterns at the time of its birth remain constant in the future. |
| Health spending per capita | World Bank WDI / WHO GHED | `SH.XPD.CHEX.PP.CD` | 2000–2024 | 2024 | 192 countries | Most recent data with widest range of countries | Current expenditures on health per capita expressed in international dollars at purchasing power parity. |
| Health spending % GDP | World Bank WDI / WHO GHED | `SH.XPD.CHEX.GD.ZS` | 2000–2024 | 2023 | 192 countries | Most recent data with widest range of countries | Current health expenditure as a percentage of GDP. |
| OOP spending % health spending | World Bank WDI / WHO GHED | `SH.XPD.OOPC.CH.ZS` | 2000–2024 | 2023 | 192 countries | Most recent data with widest range of countries | Household out-of-pocket payments as a percentage of current health expenditure. |
| UHC Service Coverage Index | World Bank WDI | `SH_UHC_SCI` | 2000–2023 | 2023 | 193 countries | Most recent data with widest range of countries | The UHC Service Coverage Index combines 14 tracer indicators of service coverage into a single summary measure for SDG Indicator 3.8.1. |

| Country | Year | OECD: Spending/person (USD PPP) | WDI/WHO: Spending/person (USD PPP) | Difference ($) | OECD: Spending/GDP (%) | WDI/WHO: Spending/GDP (%) | Difference (percentage points) | Notes |
|---|---:|---:|---:|---:|---:|---:|---:|---|
| United States | 2024 | $14,885.00 | $13,473.00 | $1,412.00 | 17.6 | 17 | 0.6 | |
| Canada | 2024 | $7,301.00 | $7,646.00 | -$345.00 | 11.5 | 11 | 0.5 | |
| United Kingdom | 2024 | $6,747.00 | $6,606.00 | $141.00 | 11.4 | 11 | 0.4 | |
| Japan | 2024 | $5,790.00 | $5,365.00 | $425.00 | 10.1 | 11 | -0.9 | |
| Switzerland | 2024 | $9,963.00 | $10,602.00 | -$639.00 | 11.6 | 12 | -0.4 | |
| Germany | 2024 | $9,365.00 | $8,826.00 | $539.00 | 12.7 | 12 | 0.7 | |
| France | 2024 | $7,367.00 | $6,868.00 | $499.00 | 11.4 | 12 | -0.6 | |
| Australia | 2024 | $7,469.00 | $7,691.00 | -$222.00 | 11.1 | 10 | 1.1 | |
| Netherlands | 2024 | $8,436.00 | $8,195.00 | $241.00 | 10.2 | 10 | 0.2 | |
| Sweden | 2024 | $7,871.00 | $7,770.00 | $101.00 | 10.9 | 11 | -0.1 | |

| Metric | Explainer |
|---|---|
| Life expectancy at birth | It is an estimate for a baby born today if current death rates stayed the same. It is not how long today's older adults will live, and it says nothing about quality of life. |
| Health spending per person (PPP dollars) | It is the amount spent on health care for each person in a country in a year, including both government and private spending. The amounts are adjusted for differences in prices between countries (Purchasing Power Parity adjustment), so that a dollar buys about the same amount of goods and services everywhere. It does not show how good the care is or how healthy people are, and a higher number does not mean better care. |
| Health spending as % of GDP | It is the percentage of the economy that is spent on healthcare. Developed and developing countries can share the same percentage, but the actual amount spent can still vary. |
| Out-of-pocket spending (% of health spending) | It is the share of a country's total health spending that is paid directly from households rather than from government budgets, private health insurance, or external aid. It does not show how much care people skip because they cannot afford it. |
| UHC service coverage index | It is a score from 0 to 100 that measures how well a country provides essential health services to its people. It is not the share of people who are insured. It is built from 14 indicators. |
| Population with health coverage (%) | It is the share of a given population that has public or private health insurance, or is eligible for essential healthcare services at any point within a specific time period. Health coverage refers to government/compulsory coverage data only. |
| Median wait for elective care (days) | It is the number of calendar days it takes for the middle patient (50th percentile) on an elective treatment waiting list to receive the scheduled care after assessment. |
| Purchasing Power Parity (USD) | It is an economic metric that measures the amount of foreign currency needed to purchase the same basket of goods and services that $1 USD would buy in the United States. |
| Gross Domestic Product | The total market value of all final goods and services produced within a country's borders during a specific period of time. |
