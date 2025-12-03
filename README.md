# Sunlight

A quiet, automated tool that turns four public data sources into one living graph of money and power flows in Knoxville & Knox County.

When ordinary daylight falls on relationships, money, appointments, and salaries, trust grows, communities coordinate, and people flourish — without anyone having to fight.

Knoxville is the first prototype. The pattern is designed to be copied by any city in one weekend.

## Live data (public, no gatekeeper)
→ https://github.com/Chad-Mitchell/knox-sunlight-data
First real data drop: **2025-12-22** — then every Sunday.

## The four public sources we use
1. Government contracts & bid awards → direct money flow  
2. Campaign contribution reports → influence via money flow  
3. Board/commission appointments + meeting minutes → power structure flow  
4. Org charts + public salary database → extraction via hierarchy flow  

These four, connected into a single edge list, are sufficient for the light to do its work.

## Concrete starting points (Knoxville 2025)

| # | Data source                                      | Links & examples |
|---|--------------------------------------------------|------------------|
| 1 | Contracts & bid awards                           | City Purchasing · County Purchasing · iQM2 search |
| 2 | Campaign contributions                           | Knox County filings · TN Registry of Election Finance |
| 3 | Appointments & minutes                           | iQM2 portal · County Commission packets |
| 4 | Org charts & salaries                            | City org chart PDF · County payroll · State salary search |

Full URLs and live examples are kept up-to-date in the repo history.

## How the data appears (reality check)

Right now the sources are scattered PDFs with no APIs.

- First drops (Dec 22 onward) are built from manually downloaded files.  
- Starting 2026 we automate one source per month until everything runs without a human.

The weekly CSV still lands every Sunday either way.

## Automation roadmap (no dates promised)

| Source                    | 2025 method            | 2026+ method                     |
|---------------------------|------------------------|----------------------------------|
| Contracts & bids          | Manual + Grok          | Puppeteer scraper                |
| Campaign finance          | Manual + Grok          | Direct CSV export                |
| Appointments & minutes    | Manual + Grok          | Calendar scraper                 |
| Org charts & salaries     | Quarterly TPRA request | Scheduled auto-parse             |

The graph stays live and public the entire time.

## Current status
2025-12-03 – repo public, data repo live, first manual drop in progress

Fork it, run it, post what you see. No permission needed.
