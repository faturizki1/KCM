# BOUNDED SUBSYSTEMS

## Purpose
This document defines the bounded subsystems for KCM using only the responsibilities and architecture concepts stated in KCM-WHITEPAPER.md. No implementation structure is introduced beyond this blueprint.

## Traceability Rule
Every subsystem below is derived from one or more whitepaper concepts:
- Knowledge-first paradigm
- Layered architecture
- Columnar-native storage
- Deterministic reasoning
- Provenance-aware, temporal-aware, and version-aware semantics

## Governance Rule
If a detail is not explicitly defined by the whitepaper, it is marked as ASSUMPTION and must not be treated as architectural truth.

## Final Bounded Subsystems

### 1. Application Layer
- Purpose: Provide the interface by which users and systems interact with KCM.
- Responsibilities: Query language, API exposure, UI interaction, reasoning interface.
- Ownership boundary: One subsystem owner responsible for interface semantics and user-facing contract stability.
- Data owned: Request/response semantics, interface metadata, query intent, reasoning entry points.
- API/interface: Abstract interface contract for query submission and result publication.
- Input: Query intent, context, request parameters.
- Output: Structured results, error responses, provenance-aware result envelopes.
- Dependency: Depends on Knowledge Layer for semantic interpretation.
- Dependency forbidden: Must not bypass Knowledge Layer to directly manipulate canonical knowledge semantics.
- Invariant: Must preserve deterministic interpretation of requests and results.
- Error boundary: Must surface interface-level errors without mutating canonical knowledge state.
- Performance responsibility: Must keep request/response overhead bounded and observable.
- Testing responsibility: Verify contract compatibility and response semantics.
- Documentation responsibility: Document interface behavior and expected result shapes.
- Traceability: Whitepaper sections on layered architecture and knowledge-first paradigm.

### 2. Knowledge Layer
- Purpose: Preserve the canonical knowledge model and its semantics.
- Responsibilities: Schema engine, entity system, fact system, evidence tracking, provenance, temporal mapping.
- Ownership boundary: One subsystem owner responsible for the integrity of the knowledge model.
- Data owned: Knowledge artifacts, schema semantics, provenance links, temporal state, version lineage.
- API/interface: Abstract contract for creating, validating, retrieving, and relating knowledge artifacts.
- Input: Knowledge artifacts, schema constraints, evidence references, context metadata.
- Output: Validated knowledge artifacts, references, provenance-aware records.
- Dependency: Depends on Compute Layer for reasoning execution and on Storage Layer for persistence access.
- Dependency forbidden: Must not depend on application-layer presentation details or bypass deterministic reasoning rules.
- Invariant: Knowledge artifacts must remain semantically consistent, traceable, and version-aware.
- Error boundary: Must reject invalid or inconsistent knowledge updates.
- Performance responsibility: Must keep validation and retrieval efficient without sacrificing determinism.
- Testing responsibility: Verify schema correctness, provenance integrity, and semantic consistency.
- Documentation responsibility: Document artifact semantics, lifecycle, and ownership rules.
- Traceability: Whitepaper sections on knowledge-first paradigm, layered architecture, and deterministic reasoning.

### 3. Compute Layer
- Purpose: Execute retrieval, query evaluation, reasoning, and graph operations.
- Responsibilities: Query execution, retrieval engine, reasoning engine, graph operations, SIMD filters, aggregation.
- Ownership boundary: One subsystem owner responsible for execution semantics and deterministic evaluation.
- Data owned: Execution plans, intermediate reasoning state, query evaluation state.
- API/interface: Abstract contract for evaluation requests and execution results.
- Input: Query plans, knowledge references, execution parameters.
- Output: Computed results, reasoning traces, execution summaries.
- Dependency: Depends on Knowledge Layer for semantic inputs and on Storage Layer for physical access.
- Dependency forbidden: Must not introduce probabilistic or non-deterministic execution paths.
- Invariant: Repeated execution over the same inputs must produce the same result.
- Error boundary: Must report execution failures without silently producing partial results.
- Performance responsibility: Must honor performance expectations for predicate filtering and vectorized execution where applicable.
- Testing responsibility: Verify deterministic output and failure handling.
- Documentation responsibility: Document execution semantics, assumptions, and limitations.
- Traceability: Whitepaper sections on deterministic reasoning and layered architecture.

### 4. Storage Layer
- Purpose: Provide the physical structure for storing knowledge data and metadata.
- Responsibilities: Column store, index pool, compression, WAL, version/history store, snapshot manager.
- Ownership boundary: One subsystem owner responsible for storage layout and persistence semantics.
- Data owned: Segment metadata, column structures, indexing metadata, WAL state, version history references.
- API/interface: Abstract contract for read/write/compact/snapshot operations.
- Input: Logical requests from Compute Layer and metadata requests from Knowledge Layer.
- Output: Read results, write acknowledgements, storage status, immutable segment references.
- Dependency: Depends on Memory Layer for buffering and on Persistence Layer for durabilty tiering.
- Dependency forbidden: Must not expose storage implementation details to Application Layer.
- Invariant: Storage must preserve consistency and support immutable or versioned segment behavior.
- Error boundary: Must detect and report corruption, write failure, and recovery issues.
- Performance responsibility: Must support efficient column access, compression, and index usage.
- Testing responsibility: Verify durability and read/write correctness.
- Documentation responsibility: Document storage layout assumptions and lifecycle semantics.
- Traceability: Whitepaper sections on columnar-native storage and storage hierarchy.

### 5. Memory Layer
- Purpose: Provide transient memory management for hot-path access and buffering.
- Responsibilities: Buffer pool, page cache, prefetch coordination.
- Ownership boundary: One subsystem owner responsible for cache behavior and memory pressure policies.
- Data owned: In-memory pages, cache metadata, prefetch plans.
- API/interface: Abstract contract for page allocation, cache admission, and eviction signals.
- Input: Access requests from Storage Layer and execution hints from Compute Layer.
- Output: Cached pages, cache misses, eviction decisions.
- Dependency: Depends on Storage Layer for source data and on Persistence Layer for durability fallback.
- Dependency forbidden: Must not become a hidden state store for business semantics.
- Invariant: Memory state must not be treated as source of truth beyond transient access optimization.
- Error boundary: Must degrade gracefully on cache miss or memory pressure.
- Performance responsibility: Must optimize locality and reduce hot-path latency.
- Testing responsibility: Verify cache behavior under pressure and miss scenarios.
- Documentation responsibility: Document cache policy and assumptions.
- Traceability: Whitepaper sections on memory layer and storage hierarchy.

### 6. Persistence Layer
- Purpose: Provide long-term durability and tiered persistence.
- Responsibilities: NVMe hot tier, HDD archive, cloud object store for cold data.
- Ownership boundary: One subsystem owner responsible for durability policy and tiering rules.
- Data owned: Durability state, tier metadata, archive state, snapshot retention references.
- API/interface: Abstract contract for durable write, archive, restore, and retention operations.
- Input: Durable write requests from Storage Layer.
- Output: Persisted references, tiering outcomes, durability acknowledgements.
- Dependency: Depends on Storage Layer as the producer of data to be durably stored.
- Dependency forbidden: Must not be used as a direct semantic knowledge store for application logic.
- Invariant: Persistence must preserve data consistency across tiers and retain the correct version lineage.
- Error boundary: Must report archival and restore failures explicitly.
- Performance responsibility: Must manage tiering without disrupting core execution semantics.
- Testing responsibility: Verify restore and retention behavior.
- Documentation responsibility: Document tiering, retention, and restore guarantees.
- Traceability: Whitepaper sections on persistence layer and storage hierarchy.
