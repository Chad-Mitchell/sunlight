# MVP – The gentlest possible sunlight

Success = one calm, clear view that lets any Knoxvillian see, in under 10 seconds:

• “Here are the connections between recent contracts and the people who awarded them”  
• “Here are the appointment and salary patterns in this department”  
• “Here is how money and influence flowed around this decision”

Four public sources → one honest map → flourishing follows naturally.

Sources (all public under Tennessee law):
1. Contracts & purchase orders  
2. Campaign finance reports  
3. Appointments + iQM2 minutes  
4. Org chart + public salary database

Tech keeps it simple and cheap:
– n8n → ingestion  
– Postgres + vectors → storage  
– Neo4j or simple graph → relationships  
– Minimal, peaceful frontend later

Nothing extra until the light feels warm and trustworthy.
