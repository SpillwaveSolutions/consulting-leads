# Consulting Leads

Inbound consulting-lead ContentPack: engagement types, qualification notes, discovery calls, scopes, and capability matches.

MIT. Dual-host: **Claude Code**, **Grok Build**, and **Codex** (Agent Skill Standard). Writes OKF Markdown + YAML into a shared second-brain bundle so other agents and local jobs can read the same graph.

## Install

```bash
# Claude Code
/plugin marketplace add SpillwaveSolutions/consulting-leads
/plugin install consulting-leads@SpillwaveSolutions

# Skilz CLI
skilz install SpillwaveSolutions/consulting-leads
```

Point the plugin at a shared knowledge root (default `knowledge/`). All sibling ContentPack plugins write into the same tree.

## Skills

| Skill | What it does |
|-------|----------------|
| `/csl-init` | Scaffold the catalogs this plugin owns |
| `/csl-capture` | Capture a noun into the shared second brain (deterministic write) |
| `/csl-pack` | Build a bounded ContextPack from a root concept |
| `/csl-validate` | Validate frontmatter, types, and links |
| `/csl-doctor` | Health check of the bundle this plugin owns |

## Nouns this plugin may write

| Type | Meaning |
|------|---------|
| `ConsultingLead` | Inbound consulting interest |
| `EngagementType` | Resident architect, harness sprint, advisory, etc. |
| `Scope` | Proposed work boundary |
| `BudgetRange` | Budget signal |
| `Timeline` | Desired start and duration |
| `DecisionMaker` | Buyer on the consulting side |
| `QualificationNote` | Fit assessment |
| `Proposal` | Consulting proposal |
| `StatementOfWork` | SOW draft or signed |
| `DiscoveryCall` | Qualification or discovery conversation |
| `Objection` | Why they might not buy |
| `Competitor` | Other firm or internal team |
| `WinLossReason` | Outcome reason |
| `ReferralSource` | How they found you |
| `CapabilityMatch` | How the ask maps to offers |

## Relationships

| `rel` | Meaning |
|-------|---------|
| `owned_by` | Consulting liaison identity |
| `typed_as` | Lead is an engagement type |
| `qualified_by` | Has a qualification note |
| `discovered_in` | Came from a discovery call |
| `matches` | Maps to a capability or offer |
| `originates_from` | Referral or inbound source |
| `related_to` | Soft association |
| `proposed_as` | Has a proposal or SOW |

## Catalogs

- `consulting-leads/`
- `engagements/`
- `discovery-calls/`
- `proposals/`
- `scopes/`

## Deterministic write boundary

The model proposes. Schema-enforced scripts commit:

```bash
python3 scripts/csl_common.py write \
  --bundle knowledge \
  --type ConsultingLead \
  --folder consulting-leads \
  --title "Example" \
  --author "Grok Bot: Consulting Leads"
```

Never invent `rel` values. Never write types owned by another plugin.



## Related plugins

- [second-brain-core](https://github.com/SpillwaveSolutions/second-brain-core) — shared pack engine and typed-edge conventions
- [project-knowledge-capture](https://github.com/SpillwaveSolutions/project-knowledge-capture) — the “why” second brain
- [system-architecture-capture](https://github.com/SpillwaveSolutions/system-architecture-capture) — the “what is running” second brain
- [wiki_ticket_sdd](https://github.com/SpillwaveSolutions/wiki_ticket_sdd) — visible work log

## License

MIT. Copyright 2026 Rick Hightower / contributors.
