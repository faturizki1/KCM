# OWNERSHIP MATRIX

## Purpose
This matrix assigns explicit ownership to each bounded subsystem without overlapping responsibility. The ownership model is a blueprint only and does not create implementation code.

| Subsystem | Primary Owner | Bounded Scope | Data Ownership | Contract Responsibility | Testing Boundary | Documentation Boundary |
|---|---|---|---|---|---|---|
| Application Layer | Application Steward | Interface semantics and user-facing interaction contract | Request/response semantics | Must maintain stable interface contract | Validate request/response compatibility | Document interface behavior and expected outputs |
| Knowledge Layer | Knowledge Model Steward | Canonical knowledge semantics and provenance integrity | Knowledge artifacts, schema semantics, provenance, temporal state | Must preserve knowledge invariants and contracts | Validate semantic consistency and provenance correctness | Document artifact semantics, lifecycle, and invariants |
| Compute Layer | Execution Steward | Deterministic reasoning and execution semantics | Execution plans and reasoning state | Must preserve deterministic evaluation boundaries | Validate determinism and error behavior | Document execution semantics and limitations |
| Storage Layer | Storage Steward | Physical layout, indexing, and storage lifecycle | Segment metadata, column storage, WAL, version history | Must preserve storage contract and consistency | Validate read/write correctness and storage lifecycle | Document storage layout and lifecycle assumptions |
| Memory Layer | Memory Steward | Cache behavior and transient access optimization | Cache metadata and transient page state | Must preserve cache contract and avoid semantic state ambiguity | Validate hit/miss and pressure behavior | Document cache policy and assumptions |
| Persistence Layer | Durability Steward | Tiered durability, archive, and retention | Durability state, tier metadata, retention state | Must preserve durability contract and recovery guarantees | Validate restore and retention behavior | Document tiering, retention, and restore guarantees |

## Ownership Guardrails
- No two owners share the same subsystem scope.
- No subsystem is left without an explicit owner.
- Integration boundaries are the only acceptable overlap and must be documented explicitly.
- Any future implementation must be assigned to one subsystem owner and one owner only.

## Blocked Ownership Decisions
- The whitepaper does not define a named person or team for each subsystem. These owners are documented as role-based architectural owners rather than named individuals.
- The whitepaper does not define a concrete implementation team structure; this remains an ASSUMPTION for future organizational planning.
