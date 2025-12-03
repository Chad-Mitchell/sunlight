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

## Pareto Gameplan: Sequence of 12 Core Actions

This is the 80/20 path: Prioritize contracts (money core) → link to finance → add power flows → surface light. Each action builds a testable piece; run queries after #6 for early wins. Use n8n for pulls/orchestration, Supabase/Airtable for raw storage, CSV for graph, Grok API for parsing/queries. Commit to repo after each.

1. [] **API Setup & Test Pull**: Get xAI API key; in n8n, build/test HTTP node to Grok 4.1 endpoint (upload sample PDF from knoxvilletn.gov Purchasing, prompt: "Extract bids: vendor, amount, date, awarding official as JSON"). Confirm structured output.

2. [] **Ingest Source 1 (Contracts)**: Cron n8n workflow: Webhook to Purchasing portal/TPRA form → Download recent 2024-2025 PDFs → Send to Grok API for entity/relation extraction (e.g., "Map: official → awards → vendor:amount") → Append JSON to Supabase table.

3. [] **Build Base Graph CSV**: Python script (local or n8n code node): Load contracts JSON → Pandas to edge list CSV (columns: source, target, type, weight=amount, timestamp). Test basic NetworkX load/visual (matplotlib plot of top nodes).

4. [] **Ingest Source 2 (Campaign Finance)**: n8n cron: Pull reports from knoxcounty.org/election PDFs → Grok API parse ("Extract: donor → official:amount, date") → Merge edges into graph CSV (update script: append + dedupe by ID).

5. [] **Cross-Link Sources 1-2**: Update script: NetworkX join on shared entities (e.g., fuzzy name match via difflib) → Flag initial cycles (e.g., donor-to-awarder loops) → Output sample CSV viz (top 5 clusters).

6. [] **Early Query Test**: n8n webhook: Input text query (e.g., "Connections around Mayor?") → Grok API prompt on CSV subset ("Analyze edges: summarize paths, anonymize names as 'Cluster A'") → Return JSON summary. Test 3 real queries.

7. [] **Ingest Source 3 (Appointments/Minutes)**: n8n: iQM2 portal scrape (HTTP + Cheerio) → PDF minutes to Grok ("Extract: official → appoints → person:board, date") → Append edges to CSV.

8. [] **Enhance Graph with Source 3**: Script update: Add appointment edges → Re-run NetworkX (degree centrality for influence) → Test query expansion (e.g., "Appointment trails to contracts?").

9. [] **Ingest Source 4 (Org/Salaries)**: n8n: Pull Feb 2025 org PDF + apps.tn.gov salary query → Grok parse ("Hierarchy: role → reports_to:salary") → Weight edges by pay premium (vs. median).

10. [] **Full Graph Polish**: Script: Integrate all edges → Basic anomaly flags (e.g., shared names + high weight > threshold) → Export anonymized JSON for dashboard.

11. [] **Build Query Dashboard**: Bubble/Next.js basics: Text input → n8n webhook to Grok (prompt on full CSV: "Gentle summary: patterns in [query], warm/light tone") → Render viz (simple table + network embed).

12. [] **Anonymize & Demo**: Add Grok prompt layer for outputs ("Frame as: 'Here are natural connections...' no accusations") → Test end-to-end with 2-3 users (e.g., trusted SMB owner) → Repo freeze, Christmas wrap.
