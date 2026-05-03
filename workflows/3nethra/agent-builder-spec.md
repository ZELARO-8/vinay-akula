# 👁 3NETHRA — Agent Builder Workflow

**Schedule:** On-demand (new agent request)
**Purpose:** SPARK designs spec → FORGE builds n8n → BRIDGE connects tools

## Nodes
1. Webhook: agent request from MAHESHWARA
2. SPARK: Claude generates identity doc + spec
3. FORGE: build n8n nodes + triggers
4. TEST: WIRE-by-WIRE QA
5. BRIDGE: connect APIs (Slack, Notion, GitHub, Gmail)
6. Deploy to zelaro8.app.n8n.cloud
7. Save JSON to GitHub workflows/
8. Notion doc + LEDGER entry
