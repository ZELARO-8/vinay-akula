# 🔱 MAHESHWARA — Empire Router Workflow

**Schedule:** Triggered on directive from Vinay or BUNNY
**Purpose:** Route every task to the correct main agent. Prevent duplicate work.

## Nodes
1. Webhook trigger (from Slack mention or Notion form)
2. Claude classifier: identify company + function + agent
3. Notion lookup: check current ownership in 54-week plan
4. Conflict check: does another agent own this?
5. Route via Slack DM to main agent + log to Notion
6. LEDGER entry

## Sub-agents driven
- ATLAS: 54-week plan tracker
- COSMOS: cross-company dependency watcher
- GRID: resource allocation map
