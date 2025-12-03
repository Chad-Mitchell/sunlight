# Sunlight

A quiet, automated tool that turns four public data sources into one living graph of money and power flows in Knoxville & Knox County.

The goal is simple:  
When ordinary daylight falls on relationships, money, appointments, and salaries, trust grows, communities coordinate, and people flourish — without anyone having to fight.

Knoxville is the first prototype. The pattern is designed to be copied by any city in one weekend.

## Companion data repo (public, automated, no gatekeeper)
→ https://github.com/Chad-Mitchell/knox-sunlight-data  
First real data drop: **2025-12-22** — then every Sunday.

## The only four public data sources we use
1. Government contracts & bid awards → direct money flow  
2. Campaign contribution reports → influence via money flow  
3. Board/commission appointments + meeting minutes → power structure flow  
4. Org charts + public salary database → extraction via hierarchy flow  

These four, connected into a single edge list, are sufficient for the light to do its work.

The physics problem is (Elon Algorithm / First principles lens): make the four money+power flows visible to any citizen faster than the insiders can hide them.

## Legal context (why certain flows are allowed in Tennessee)

All edges in the graph are created by laws that are already public.  
The most common statutes you will see in practice:

| Statute                                | What it permits                                      | Typical graph pattern it creates                     |
|----------------------------------------|-------------------------------------------------------|------------------------------------------------------|
| T.C.A. § 7-53-101 et seq.              | Industrial Development Boards (IDBs)                  | Public → private corporation → PILOT / tax abatement |
| T.C.A. § 7-88-101 et seq.              | Sports & tourism authorities                          | Public → private stadium / venue → tax diversion     |
| T.C.A. § 13-20-201 et seq. & § 13-28-101 | Tax Increment Financing (TIF)                            | Public → TIF district → private developer uplift     |
| T.C.A. § 6-54-111 & § 7-54-111          | Municipal appropriations to “economic development” nonprofits | Public → nonprofit → private beneficiary             |
| Tennessee Public Records Act (T.C.A. § 10-7-503) | Guarantees citizen access to every document we ingest | No permission needed — we just automate what is already yours |

These laws are not opinions — they are the physics engine of the graph.  
When a cluster appears, the relevant statute is usually only one click away in the original PDF.

## Concrete Knoxville/Knox County starting points (all public, updated regularly)

| # | Data source                                      | Where to find the real files (2025 links) & examples |
|---|--------------------------------------------------|------------------------------------------------------|
| 1 | **Government contracts & bid awards** (direct money flow) | • City of Knoxville Purchasing bids & awards: https://www.knoxvilletn.gov/government/city_departments_offices/purchasing/bid___contracting_opportunities (e.g., "Pedestrian Mall Revitalization Project" bid tabulation PDF, awarded Oct 2025, $2.1M; check for addenda)<br>• Knox County Purchasing (includes TIF & IDB awards): https://www.knoxcounty.org/purchasing/ (e.g., "Urban Development Infrastructure" RFP, due Dec 2025; use "Solicitations" dropdown for archives)<br>• Knoxville-Knox County Sports Authority packets (stadium, etc.): Search at https://knoxvillecitytn.iqm2.com/Citizens/Default.aspx (e.g., Nov 2025 meeting packet on venue maintenance contracts, $500K award) |
| 2 | **Campaign contribution reports** (influence via money flow) | • Knox County Election Commission filings (local races): https://www.knoxcounty.org/election/candidate_info/index.php (e.g., Q4 2025 report for City Council candidates, searchable by name; sample: $15K total contributions)<br>• Tennessee Registry of Election Finance (state-level crossover): https://apps.tn.gov/tncamp/ (e.g., search "Knoxville" for 2025 filings; sample: Local donor report to county officials, $8K in Q3) |
| 3 | **Board/commission appointments + meeting minutes** (power structure flow) | • All boards & commissions agendas/minutes (including TIF boards, IDB, Sports Authority): https://knoxvillecitytn.iqm2.com/Citizens/Default.aspx (e.g., filter "Sports Authority" for Dec 2025 agenda on appointments; Nov 2025 TIF board minutes PDF with 3 new member approvals)<br>• Knox County Commission & committee packets: https://www.knoxcounty.org/clerk/commission_minutes.php (e.g., Oct 2025 packet with commission appointment votes, downloadable ZIP; audio/video via phone 865-215-2683) |
| 4 | **Org charts + public salary database** (extraction via hierarchy flow) | • City of Knoxville org chart (latest PDF): https://cdnsm5-hosted.civiclive.com/UserFiles/Servers/Server_109478/File/MayorsOffice/City-Org-Chart.pdf (Feb 2025 update, 50+ roles from Mayor to dept heads; e.g., Chief of Staff → Finance Director)<br>• Knox County employee salaries (searchable): https://www.knoxcounty.org/finance/paying_employees.php (e.g., search "Director" for 2025 ranges: $120K-$180K median; payroll summaries via Clerk financials at https://www.knoxcounty.org/clerk/financials.php)<br>• State-wide salary lookup (for UT, state appointees, etc.): https://salary.app.tn.gov/public/searchsalary (e.g., query "University of Tennessee Knoxville" for exec salaries, avg $150K+) |

These URLs are the actual firehose we automate from. They are not the full set of data sources, only the initial set identified as a starting point. We will continue to expand and improve this list over time. Ideally, all the relevant data sources would be available via API or programatically accessible in the future.   

If any link moves, a 2-minute web search will find the new one—the data is required by law to stay public.

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
