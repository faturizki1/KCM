# Persistence Layer Contract

## Producer
- Persistence Layer

## Consumer
- Storage Layer
- Memory Layer

## Input
- Durable writes
- Archive requests
- Restore requests

## Output
- Durability acknowledgements
- Tiering results
- Retention state

## Data Ownership
- Persistence Layer owns durable retention state
- Storage Layer owns physical storage representation
- Memory Layer owns transient staging state

## Lifecycle
- Data is staged, persisted, archived, and restored according to tier policy

## Error Semantics
- Persistence failures must be explicit and auditable

## Concurrency Assumptions
- Concurrent durability operations must preserve correct version lineage

## Compatibility Requirements
- Durability policy changes must not break the contract without review

## Performance Expectations
- Tiering must not introduce unbounded latency into core execution paths

## Status
- Mapped from SUBSYSTEM-CONTRACTS.md
