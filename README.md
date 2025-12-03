# Sunlight

A quiet, automated tool that turns four public data sources into one living graph of money and power flows in Knoxville & Knox County.

The goal is simple:  
When ordinary daylight falls on relationships, money, appointments, and salaries, trust grows, communities coordinate, and people flourish — without anyone having to fight.

Knoxville is the first prototype. The pattern is designed to be copied by any city in one weekend.

## Companion data repo (public, automated, no gatekeeper)
→ https://github.com/Chad-Mitchell/knox-sunlight-data  
First real data drop: **2025-12-22** — then every Sunday forever.

## The only four public data sources we use
1. Government contracts & bid awards → direct money flow  
2. Campaign contribution reports → influence via money flow  
3. Board/commission appointments + meeting minutes → power structure flow  
4. Org charts + public salary database → extraction via hierarchy flow  

These four, connected into a single edge list, are sufficient for the light to do its work.

## How it works (fully automated after Christmas 2025)
- n8n pulls fresh PDFs → Grok extracts clean entities & relationships  
- One CSV edge list is built  
- CSV is pushed to `knox-sunlight-data` every Sunday at 03:00 UTC  
- Anyone can fork, query, visualize, or post findings — no permission needed  

## Current status (one-liner, updated on every push)
Status: 2025-12-03 – repo public, data repo live, ingestion pipeline starting

## Pareto TODO → Christmas 2025 MVP

1. xAI API setup + first PDF → JSON test  
2. Ingest Source 1 (largest recent contracts & development awards)  
3. Build base edge-list CSV  
4. Ingest Source 2 (campaign contributions)  
5. Cross-link 1→2 – watch natural clusters appear  
6. Early query test in terminal / notebook  
7. Ingest Source 3 (appointments + minutes)  
8. Ingest Source 4 (org charts + salaries)  
9. Full graph polish & anonymization defaults  
10. Wire n8n → auto-commit to `knox-sunlight-data` every Sunday  
11. Static query.html in data repo loads latest CSV in-browser  
12. December 22 – merge to main and v2 expansions
