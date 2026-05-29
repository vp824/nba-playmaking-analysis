# UNASSISTED 🏀
### How teammate quality shapes NBA playmaking

[![Tableau](https://img.shields.io/badge/Tableau-Public-blue)](YOUR_TABLEAU_URL)
[![Python](https://img.shields.io/badge/Python-3.x-blue)](https://python.org)
[![Data](https://img.shields.io/badge/Data-NBA.com%2Fstats-orange)](https://nba.com/stats)

---

## Research Question

Which players consistently improve teammates' shooting the most, and how stable is the relationship between teammate quality and assist numbers across multiple NBA seasons?

---

## Dashboard

🔗 [View the Tableau Public Dashboard](YOUR_TABLEAU_URL)

![Dashboard Preview](YOUR_SCREENSHOT.png)

---

## Project Overview

This project analyses NBA playmaking quality across four regular seasons (2022-23 to 2025-26), moving beyond raw assist numbers to measure how much elite creators genuinely improve their teammates' shooting.

---

## Methodology

### Creator Sample
22-31 elite creators identified per season using these thresholds:
- Games Played ≥ 58
- Potential Assists ≥ 10 per game
- Actual Assists ≥ 5 per game
- Minutes ≥ 28 per game

Sample size varies by season reflecting natural variation in players meeting all qualifying thresholds each year.

---

## Key Metrics

### ACR — Assist Conversion Rate
Assists divided by potential assists. Measures how efficiently a creator converts scoring opportunities into assists.

### TQI — Teammate Quality Index
Weighted average true shooting percentage of a creator's primary recipients (minimum 50 passes). Measures the finishing quality of the teammates a creator passes to most.

### ACR Residual
Actual ACR minus the ACR expected given the quality of a player's teammates. Expected ACR is derived from a linear regression of ACR against TQI across all creators in that season.
- Positive = outperforms teammate quality expectations
- Negative = underperforms teammate quality expectations

### CAS Lift — Catch and Shoot Lift
FG percentage on a creator's passes minus the recipient's catch and shoot baseline (touch < 2 seconds).
- Positive = creator improves teammate shooting above their baseline
- Negative = creator below teammate baseline

---

## Quadrant Definitions

| Quadrant | TQI | CAS Lift | Interpretation |
|---|---|---|---|
| Elite Playmaker | Below median | Above median | Creates quality looks despite below-average finishing teammates |
| Volume Creator | Above median | Above median | Creates quality looks AND passes to elite finishing teammates |
| Tough Environment | Below median | Below median | Below average shooting improvement with below average finishing teammates |
| Benefiting from Teammates | Above median | Below median | High quality teammates but not improving their shooting above baseline |

---

## Dashboard Features

### Three Analytical Panels
- **Quadrant View** — Where does each creator sit in 2025-26?
- **Metric Comparison** — How do they rank across TQI, ACR Residual and CAS Lift?
- **Rank Stability** — How consistent have they been across four seasons?

### Interactivity
- Choose a player dropdown highlights across all three panels simultaneously
- Sort by parameter on metric comparison chart
- Metric selector on rank stability bump chart
- Hover tooltips with dynamic rank labels per season

---

## Limitations

- Season-level analysis only. Player metrics reflect full season totals regardless of team changes during the season
- Top recipient reflects cumulative season pass data. A recipient's current team may differ from when passes occurred
- CAS Lift uses touch < 2 seconds as a catch-and-shoot proxy
- Bump chart shows players with 3+ qualifying seasons only

---

## Data Source & Tools

| Tool | Purpose |
|---|---|
| Python | Data pipeline and metric engineering |
| nba_api | NBA.com/stats data extraction |
| pandas | Data manipulation and analysis |
| numpy | OLS regression for ACR Residual |
| Tableau Public | Dashboard visualisation |

**Data:** NBA.com/stats · Regular Season · 2022-23 to 2025-26

---

## Repository Structure
```
nba-playmaking-analysis/
│
├── README.md
├── notebooks/
│   └── nba_playmaking_pipeline.ipynb
├── data/
│   └── nba_playmaking_all_seasons.csv
└── dashboard/
    └── unassisted.twbx
```

---

## Key Findings

**Shai Gilgeous-Alexander** consistently 
ranks last in ACR Residual but second in 
CAS Lift across all four seasons. He creates 
quality catch-and-shoot looks that his 
below-average finishing teammates fail to 
convert, making him the most analytically 
underrated creator in the sample.

**Nikola Jokić** is a consistent Volume 
Creator across all four seasons with one 
Elite Playmaker season in 2023-24 when his 
teammates dropped below the finishing quality 
median. He still improved their shooting that 
season, making it his most impressive 
playmaking campaign.

**Stephon Castle** leads all 2025-26 creators 
in CAS Lift driven by Luke Kornet as his top 
recipient. Notably Wembanyama shows negative 
shooting lift on Castle's passes, suggesting 
Castle's elite lift score is recipient 
dependent rather than a broad playmaking trait.

**James Harden** shows a sharp decline in 
ACR Residual in 2025-26 after joining 
Cleveland, dropping from rank #1 in 2024-25 
to #11. This suggests his elite playmaking 
was partly system and context dependent 
rather than a stable individual trait.

**Jamal Murray** consistently ranks #1 in 
TQI across all four seasons with Nikola 
Jokić as his primary recipient. Yet he posts 
the worst ACR Residual in the sample, 
confirming his assists are the most 
teammate dependent in the dataset.

---

## Author

Made by Vinze Perez
[LinkedIn](YOUR_LINKEDIN_URL) · [Tableau Public](YOUR_TABLEAU_URL)
