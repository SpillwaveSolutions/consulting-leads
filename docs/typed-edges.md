# Typed edges — Consulting Leads

Direction matters. Packs follow outbound edges by default.

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

Unknown `rel` values are treated as `info` by validation. Do not invent new names in this plugin.
