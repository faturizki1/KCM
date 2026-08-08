# Application Layer Contract

## Producer
- Application Layer

## Consumer
- Knowledge Layer

## Input
- Query intent
- Request context
- Interface parameters

## Output
- Structured results
- Error responses
- Interface-level envelopes

## Data Ownership
- Application Layer owns request semantics
- Knowledge Layer owns canonical knowledge semantics

## Lifecycle
- Request is submitted, validated, and handed to the knowledge-aware contract

## Error Semantics
- Invalid requests must return explicit contract errors

## Concurrency Assumptions
- Concurrent requests must not corrupt knowledge semantics

## Compatibility Requirements
- Request contract changes must be versioned

## Performance Expectations
- Request handling must remain bounded and observable

## Status
- Mapped from SUBSYSTEM-CONTRACTS.md
