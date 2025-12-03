# Sunlight

A quiet tool to bring clear light to local government in Knoxville—so that families, small businesses, neighborhoods, and the whole city can make better decisions and flourish together.

Knoxville is the first living prototype.

## The intuition
When relationships, money, appointments, and salaries are gently made visible, trust grows naturally.  
People self-correct.  
Communities coordinate.  
Good ideas win without force.

There is no enemy here—only shadows that dissolve in ordinary daylight.

## The only four public data sources we need
1. Government contracts & bid awards (direct money flow): Outflows from public to private (e.g., TIF bonds as edges).
2. Campaign contribution reports (influence via money flow): Inputs that bend decisions (e.g., donor → policy nudge).
3. Board/commission appointments + meeting minutes (power structure flow): Who holds levers (e.g., TIF board picks).
4. Organizational charts + public salary database (extraction via hierarchy flow): Value siphoned up (e.g., appointee pay weights).

Connected simply, these four create a shared map that any resident or business owner can read in seconds.

## Current status (one-liner, updated whenever you push)
- 12.03.25 – repo seeded, four sources locked, ready for first PDF ingest

## TODO (Pareto Sequence – Christmas 2025 MVP)

Follow the 12-action flow: Ingest → Graph → Query.  
The data itself will surface whatever naturally wants to be seen (TIF districts, stadium financing, large real-estate deals, etc.) without us ever naming a specific project or person up front.

1. API Setup & Test Pull  
2. Ingest Source 1 (Contracts & bid awards – direct money flow)  
   – Start with the largest recent public-works and development PDFs from knoxvilletn.gov Purchasing and Sports Authority packets  
3. Build Base Graph CSV (edge list: source → target : amount : date : type)  
4. Ingest Source 2 (Campaign contribution reports – influence via money flow)  
5. Cross-Link Sources 1–2 – let cycles and clusters emerge on their own  
6. Early Query Test – e.g. “Show me the strongest money ↔ influence loops in the last 36 months”  
7. Ingest Source 3 (Appointments + meeting minutes – power structure flow)  
8. Enhance Graph with Source 3  
9. Ingest Source 4 (Org charts + public salary database – extraction via hierarchy flow)  
10. Full Graph Polish – dedupe entities, add gentle weights, anonymize by default  
11. Build Query Dashboard (simple text box → warm, neutral summary + optional network viz)  
12. Anonymize & Demo – share with 2–3 trusted, neutral testers before Christmas  
