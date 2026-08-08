# Storage Layer Contract

## Producer
- Storage Layer

## Consumer
- Compute Layer
- Knowledge Layer

## Input
- Read/write requests
- Storage metadata requests
- Column and segment operations

## Output
- Read results
- Write acknowledgements
- Storage status

## Data Ownership
- Storage Layer owns physical storage layout and storage lifecycle
- Knowledge Layer owns semantic interpretation of stored data

## Lifecycle
- Data is read, written, versioned, and retained through storage lifecycle stages

## Error Semantics
- Storage failures must be explicit and auditable

## Concurrency Assumptions
- Concurrent storage operations must preserve consistency and version discipline

## Compatibility Requirements
- Storage interfaces must remain stable for the contract to remain valid

## Performance Expectations
- Columnar access should remain efficient and deterministic

## Status
- Mapped from SUBSYSTEM-CONTRACTS.md
