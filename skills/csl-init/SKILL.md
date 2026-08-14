---
name: csl-init
description: Scaffold the Consulting Leads catalogs in a shared second-brain bundle.
---

# csl-init

Create the catalogs this plugin owns inside a shared knowledge root.

## Process

1. Confirm target (default `knowledge/`).
2. Run:

```bash
python3 "${CLAUDE_PLUGIN_ROOT}/scripts/csl_common.py" init-bundle \
  --bundle knowledge \
  --title "Consulting Leads" \
  --catalogs "consulting-leads,engagements,discovery-calls,proposals,scopes"
```

3. Point the user at `sample-knowledge/` for a fictional demo.

## Done when

- `knowledge/index.md` exists
- Each owned catalog has `index.md`
