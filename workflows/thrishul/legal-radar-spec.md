# ⚡ THRISHUL — Legal Radar Workflow

**Schedule:** Daily 9:00 AM ET + on-demand contract review
**Purpose:** Cover legal across 8 companies. Flag risks within 2 hours.

## Nodes
1. Cron 9AM + webhook for contract upload
2. KAVACH: pull state THC + smokeshop rule updates
3. DHARMA: scan any new contracts in Drive
4. SCAN sub-agent: clause analysis
5. FLAG: if risk found, immediate Slack ping + #zelaro-legal
6. ZONE: jurisdiction matrix update
7. VEIL: IP + trademark watch
8. LEDGER entry
