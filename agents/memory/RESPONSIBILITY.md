# Memory Layer Responsibility

## WHAT THIS SUBSYSTEM OWNS
- Buffer pool and page cache policy
- Prefetch coordination
- Transient access optimization behavior

## WHAT THIS SUBSYSTEM DOES NOT OWN
- Canonical knowledge semantics
- Durability policy
- Application interface semantics
- Storage layout semantics

## STATUS
- Boundary defined from architecture documents
- Overlap check: none identified in bootstrap phase
