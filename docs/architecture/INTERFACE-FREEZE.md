# INTERFACE FREEZE

## Purpose
This document records the interface boundaries that must remain stable before implementation begins. Any change requires an architecture review and a registered proposal.

| Interface | Direction | Contract Owner | Stability Level | Notes |
|---|---|---|---|---|
| Application -> Knowledge | Outbound | Application Layer | FROZEN | Request semantics must remain aligned with knowledge artifact contracts |
| Knowledge -> Compute | Outbound | Knowledge Layer | FROZEN | Reasoning requests must be deterministic and provenance-aware |
| Compute -> Storage | Outbound | Compute Layer | FROZEN | Execution must not bypass storage semantics |
| Storage -> Persistence | Outbound | Storage Layer | FROZEN | Storage layout must remain compatible with persistence boundaries |
| Memory -> Storage | Outbound | Memory Layer | FROZEN | Memory optimization must not alter durable record semantics |
| Persistence -> Storage | Outbound | Persistence Layer | FROZEN | Durability semantics must be preserved |

## Freeze Rule
No interface may be changed, expanded, or narrowed without an approved change proposal and explicit contract update.
