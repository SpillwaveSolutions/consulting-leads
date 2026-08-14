---
name: csl-validate
description: Validate Consulting Leads concepts: required fields, types, and in-bundle links.
---

# csl-validate

```bash
python3 "${CLAUDE_PLUGIN_ROOT}/scripts/csl_common.py" validate --bundle knowledge
```

Fail on missing `type`/`title` or broken absolute links.
