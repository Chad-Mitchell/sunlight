# sunlight (private)

A quiet tool to bring clear light to local government in Knoxville—so that families, small businesses, neighborhoods, and the whole city can make better decisions and flourish together.

Knoxville is the first living prototype.

## The intuition
When relationships, money, appointments, and salaries are gently made visible, trust grows naturally.  
People self-correct.  
Communities coordinate.  
Good ideas win without force.

There is no enemy here—only shadows that dissolve in ordinary daylight.

## The only four public data sources we need
1. Government contracts & bid awards (money flow)
2. Campaign contribution reports  (influence flow)
3. Board/commission appointments + meeting minutes (power flow) 
4. Organizational charts + public salary database  (extraction flow)

Connected simply, these four create a shared map that any resident or business owner can read in seconds.

## Current status
Private workshop.  
Building slowly and carefully until the light is clean, kind, and undeniably useful.

When it’s ready, we’ll open the window and let the sun in.

No drama.  
Just daylight.

## TODO (Pareto Sequence – Christmas 2025 MVP)
Follow the 12-action flow: Ingest → Graph → Query. Seed with Boyd stadium as test cluster (public PDFs from knoxvilletn.gov Purchasing/iQM2; prompt Grok: "Extract edges: official→awards→vendor:amount, anonymize").

1. API Setup & Test Pull  
2. Ingest Source 1 (Contracts) – Start with stadium bids (e.g., $114M breakdown PDFs)  
3. Build Base Graph CSV  
4. Ingest Source 2 (Campaign Finance) – Cross Boyd donations  
5. Cross-Link Sources 1-2 – Flag TIF loops  
6. Early Query Test – "Patterns in sports subsidies?"  
7. Ingest Source 3 (Appointments/Minutes) – UT/ECD ties  
8. Enhance Graph with Source 3  
9. Ingest Source 4 (Org/Salaries) – Weight by pay premiums  
10. Full Graph Polish – Anonymize outputs  
11. Build Query Dashboard  
12. Anonymize & Demo – Test with 2-3 neutrals  

Status: [Your note here] – e.g., "Day 1: API live, stadium PDF parsed."
