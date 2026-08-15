---
name: csl-capture
description: Capture a Consulting Leads noun into the shared second brain via the deterministic write helper.
---

# csl-capture

## Process

1. Identify the noun type from the allowed list (see README).
2. Resolve identity: run `whoami`. If unclaimed, ask the user what to sign as, then `whoami --claim`. Do not invent a Grok Bot name.
3. Collect title, status, and optional typed links.
3. Write with the helper — do not hand-author frontmatter unless the user insists:

```bash
python3 "${CLAUDE_PLUGIN_ROOT}/scripts/csl_common.py" write \
  --bundle knowledge \
  --type ConsultingLead \
  --folder consulting-leads \
  --title "Example ConsultingLead" \
  --author "${SECOND_BRAIN_IDENTITY:?claim an identity first: brain.py whoami --claim}" \
  --tags "csl"
```

4. Add typed links in a follow-up edit if needed (`rel` values from `docs/typed-edges.md`).
5. Validate.

Allowed types: ConsultingLead, EngagementType, Scope, BudgetRange, Timeline, DecisionMaker, QualificationNote, Proposal, StatementOfWork, DiscoveryCall, Objection, Competitor, WinLossReason, ReferralSource, CapabilityMatch.
