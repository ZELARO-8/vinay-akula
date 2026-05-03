# 🐰 BUNNY — Morning Brief Workflow Spec

**Workflow name:** `bunny-morning-brief-v1`
**Owner:** BUNNY (Tier 0)
**Schedule:** Daily 6:00 AM ET
**Delivery:** 7:00 AM ET to Gmail + Slack #founder-brief
**Platform:** n8n (zelaro8.app.n8n.cloud)

## Nodes

| # | Node | Type | Action |
|---|---|---|---|
| 1 | Cron Trigger | Schedule | Daily 06:00 America/New_York |
| 2 | Read LEDGER | Notion | Query last 24hr entries from data source `2ee452f0-ff57-471e-8d3b-e1d4db7f6e5b` |
| 3 | Read Week Tasks | Notion | Query data source `f8d0fa64-a4e5-47b3-b715-0a2f47584a92` for today |
| 4 | Pull Market Signals | HTTP | Perplexity API: trends, competitors, news |
| 5 | Board of Minds | Claude | Run simulation if strategic flag set |
| 6 | Compose Brief | Claude | Format: wins/blockers/today/strategic |
| 7 | Quality Check | Claude | QUALITY junior validates output |
| 8 | Send Gmail | Gmail | To: vinay@zelaro.net, Subject: [BUNNY] Founder Brief MM/DD |
| 9 | Send Slack | Slack | Channel: #founder-brief |
| 10 | Log to LEDGER | Notion | Insert row: Action=Morning Brief, Status=Done |

## Brief Format

```
[BUNNY] Founder Brief — {{ $today }}

🟢 WINS (last 24h):
- {bullet from LEDGER}

🔴 BLOCKERS:
- {bullet}

📋 TODAY'S P0:
- {tasks due today, priority P0}

📊 NUMBERS:
- Revenue: $X | Followers: X | Email subs: X

🎯 STRATEGIC (if any):
- {Board of Minds output}

— BUNNY
```

## 4hr Pulse (Sub-workflow)

Triggers every 4 hours. Only fires if delta detected.
3 bullets max.

## Sunday 9PM Master Pack

Separate workflow `bunny-monday-master-pack`. Compiles week.
