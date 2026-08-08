# ERROR CONTRACT

## Purpose
This document establishes the required error-handling posture for all future implementation work so that failures remain explicit and auditable.

| Error Class | Trigger | Required Handling | Owner | Severity |
|---|---|---|---|---|
| Contract Violation | A subsystem receives input that violates a documented contract | Return explicit contract error and log the violation | Respective subsystem owner | High |
| Provenance Loss | A derived artifact cannot be traced to its source | Reject the operation unless provenance is restored | Knowledge Layer | High |
| Determinism Breach | An execution path produces nondeterministic output | Mark the operation as invalid and prevent acceptance | Compute Layer | High |
| Durability Failure | A persistence operation cannot guarantee durability | Surface a durable-write failure and halt dependent processing | Persistence Layer | High |
| Storage Inconsistency | Storage and persistence disagree on a record state | Reject the operation and raise a consistency error | Storage Layer | High |
| Memory Staleness | Memory state is older than the authoritative source | Invalidate or refresh before use | Memory Layer | Medium |

## Error Rule
All implementation work must preserve explicit error surfaces and avoid silent retries or silent drop of errors.
