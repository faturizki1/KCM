# Persistence Layer Responsibility

## WHAT THIS SUBSYSTEM OWNS
- Durability policy
- Tiering and archival behavior
- Retention and restore responsibility

## WHAT THIS SUBSYSTEM DOES NOT OWN
- Application interface semantics
- Knowledge semantics
- Deterministic reasoning execution
- Storage layout semantics

## STATUS
- Boundary defined from architecture documents
- Overlap check: none identified in bootstrap phase
