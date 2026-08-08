# Compute Layer Contract

## Producer
- Compute Layer

## Consumer
- Storage Layer

## Input
- Query plans
- Semantic references
- Execution parameters

## Output
- Evaluation results
- Reasoning traces
- Execution summaries

## Data Ownership
- Compute Layer owns execution behavior
- Knowledge Layer owns semantic inputs
- Storage Layer owns physical access

## Lifecycle
- Execution requests are evaluated against deterministic rules

## Error Semantics
- Execution failures must be explicit and not silently succeed

## Concurrency Assumptions
- Execution results must remain deterministic under equivalent inputs

## Compatibility Requirements
- Contracts must remain stable for determinism

## Performance Expectations
- Execution should remain bounded and reproducible

## Status
- Mapped from SUBSYSTEM-CONTRACTS.md
