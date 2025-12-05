# Knox Sunlight

A quiet, automated tool that turns publicly available government data into a single, living network graph of money and influence in Knoxville & Knox County.

Daylight on relationships and flows helps everyone — residents, journalists, officials, and researchers — understand how decisions are made. No accusations, no editorials, just connected facts.

The pattern is intentionally simple so any city can copy it in a weekend.

**Live graph (coming soon)** → https://knoxsun.com  
**Raw data repository** → https://github.com/Chad-Mitchell/knox-sunlight-data  
First automated update target: January 2026

## What we show (all from official public sources)

| Dataset                            | Source                                      | Update cadence | Purpose                              |
|------------------------------------|---------------------------------------------|----------------|--------------------------------------|
| Tax-increment financing (TIF) & payment-in-lieu-of-taxes (PILOT) projects | City of Knoxville / Knox County records     | Quarterly → Weekly | Show which entities receive incentives |
| Campaign contributions (≥ $1,000)  | Tennessee Registry of Election Finance      | Quarterly      | Document disclosed political donations |
| City Council & County Commission voting records | iQM2 agendas & minutes                      | Weekly         | Record who sponsored and supported each item |
| Major contracts & bid awards       | City Purchasing / KnoxBuys                | Monthly        | Track public spending flows (phase 2) |

These four datasets, linked together, are sufficient for meaningful daylight.

## Visualizations (live at knoxsun.com when launched)

Three neutral views that auto-update every Sunday. All data from official public sources only.

| View                        | Best for                          | Example insight (multi-use sports stadium)                              | Tech (one file)      |
|-----------------------------|-----------------------------------|--------------------------------------------------------------------------|----------------------|
| Follow the Money Sankey     | General public (instant impact)   | Large public incentive → private development entity → political donations → elected officials who approved the project | D3.js + Observable   |
| Connection Score Leaderboard| Journalists & non-visual readers  | Top 10 public incentive projects ranked by strength of financial-political links | HTML table + Tailwind|
| Interactive Network Graph   | Researchers & detailed analysis   | Click any project or official → see exact dollar amounts, dates, and recorded votes | vis-network.js       |

All visualizations are mobile-friendly, require no login, and are designed to be shared or screenshot.
Preview versions will appear in `/viz` as soon as the first datasets are processed.

## Example insight (currently in development)

A recent multi-use sports stadium project received approximately $65 million in combined public financing and tax incentives.  
The same development network made roughly $X in disclosed political contributions (2020–2025) to elected officials who voted on the project.

This pattern appears as the current #1 entry on the Connection Score Leaderboard (preview coming January 2026).


## Automation (n8n workflow — runs forever)

Single, low-maintenance workflow (≤12 nodes) on the free n8n tier:

1. Schedule Trigger → Every Sunday 03:00 ET  
2. HTTP Request → Latest public incentive project list  
3. HTTP Request → State campaign finance bulk export  
4. HTTP Request → New council/commission agenda and minute packets  
5. LLM node (Grok-4 or OpenAI) → Structured extraction from new documents  
6. Merge → Append to master datasets  
7. GitHub → Commit updated CSVs and edge list  
8. Webhook → Trigger site rebuild at knoxsun.com  
9. Optional notification → “Weekly update complete — X new connections added”

Full workflow JSON will live at `/automation/n8n-workflow.json`.

## Philosophy

> “When ordinary daylight falls on relationships, money, appointments, and salaries, trust grows, communities coordinate, and people flourish — without anyone having to fight.”

No commentary is added. The graph speaks for itself.

## Current status (December 2025)

- Repository and data structure public  
- Initial datasets being assembled from official PDFs and exports  
- Live site (knoxsun.com) in development — first public graph expected January 2026  
- All code and data remain openly licensed (MIT) and forkable by any Tennessee city

## Get involved (no cost, no drama)

- Star / watch the repo for updates  
- Submit missing public documents via Issues or PRs  
- Fork for Chattanooga, Nashville, Memphis, etc.

Questions? Open an issue. We respond to every good-faith request.

— Just sunlight. Nothing more, nothing less.