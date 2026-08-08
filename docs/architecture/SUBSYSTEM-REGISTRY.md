# SUBSYSTEM REGISTRY

## Purpose
This registry maps each bounded subsystem to ownership, boundary, dependency, contract, and workspace status without introducing implementation changes.

## Registry Entries

### SUBSYSTEM-ID: APP-001
- NAME: Application Layer
- RESPONSIBILITY: Interface semantics, query request handling, result publication
- OWNER: Application Steward
- BOUNDARY: Must not own canonical knowledge semantics or storage behavior
- INPUTS: Query intent, request context, interface parameters
- OUTPUTS: Structured results, error responses, interface-level envelopes
- PUBLIC-CONTRACTS: Application Layer -> Knowledge Layer
- DEPENDENCIES: Knowledge Layer
- DEPENDENTS: None in this bootstrap phase
- OWNED-PATHS: agents/application/**, docs/architecture/**, docs/engineering/**
- SHARED-PATHS: docs/architecture/**, docs/engineering/**
- FORBIDDEN-PATHS: knowledge/**, compute/**, memory/**, storage/**, persistence/**
- STATUS: PLANNED

### SUBSYSTEM-ID: KNL-001
- NAME: Knowledge Layer
- RESPONSIBILITY: Canonical knowledge semantics, provenance, temporal awareness, version lineage
- OWNER: Knowledge Model Steward
- BOUNDARY: Must not own interface presentation or storage layout semantics
- INPUTS: Knowledge artifacts, schema constraints, evidence references
- OUTPUTS: Validated knowledge artifacts, provenance-aware records
- PUBLIC-CONTRACTS: Knowledge Layer -> Compute Layer, Knowledge Layer -> Storage Layer
- DEPENDENCIES: Compute Layer, Storage Layer
- DEPENDENTS: Application Layer
- OWNED-PATHS: agents/knowledge/**
- SHARED-PATHS: docs/architecture/**
- FORBIDDEN-PATHS: application/**, compute/**, memory/**, storage/**, persistence/**
- STATUS: PLANNED

### SUBSYSTEM-ID: CMP-001
- NAME: Compute Layer
- RESPONSIBILITY: Deterministic query execution, retrieval, reasoning, graph operations
- OWNER: Execution Steward
- BOUNDARY: Must not own business semantics or persistence policy
- INPUTS: Query plans, semantic references, execution parameters
- OUTPUTS: Evaluation results, reasoning traces, execution summaries
- PUBLIC-CONTRACTS: Compute Layer -> Storage Layer
- DEPENDENCIES: Knowledge Layer, Storage Layer
- DEPENDENTS: Knowledge Layer
- OWNED-PATHS: agents/compute/**
- SHARED-PATHS: docs/architecture/**
- FORBIDDEN-PATHS: application/**, knowledge/**, memory/**, persistence/**
- STATUS: PLANNED

### SUBSYSTEM-ID: STG-001
- NAME: Storage Layer
- RESPONSIBILITY: Columnar storage layout, indexing, read/write lifecycle, versioned storage behavior
- OWNER: Storage Steward
- BOUNDARY: Must not own application semantics or reasoning semantics
- INPUTS: Storage requests from Compute Layer, metadata requests from Knowledge Layer
- OUTPUTS: Read results, write acknowledgements, storage status
- PUBLIC-CONTRACTS: Storage Layer -> Memory Layer, Storage Layer -> Persistence Layer
- DEPENDENCIES: Memory Layer, Persistence Layer
- DEPENDENTS: Compute Layer, Knowledge Layer
- OWNED-PATHS: agents/storage/**
- SHARED-PATHS: docs/architecture/**
- FORBIDDEN-PATHS: application/**, knowledge/**, compute/**, memory/**, persistence/**
- STATUS: PLANNED

### SUBSYSTEM-ID: MEM-001
- NAME: Memory Layer
- RESPONSIBILITY: Buffering, page cache, prefetch coordination
- OWNER: Memory Steward
- BOUNDARY: Must not own canonical knowledge semantics or durability policy
- INPUTS: Access requests, hints, page references
- OUTPUTS: Cached pages, miss signals, eviction decisions
- PUBLIC-CONTRACTS: Memory Layer -> Storage Layer, Memory Layer -> Persistence Layer
- DEPENDENCIES: Storage Layer, Persistence Layer
- DEPENDENTS: Storage Layer
- OWNED-PATHS: agents/memory/**
- SHARED-PATHS: docs/architecture/**
- FORBIDDEN-PATHS: application/**, knowledge/**, compute/**, storage/**, persistence/**
- STATUS: PLANNED

### SUBSYSTEM-ID: PRS-001
- NAME: Persistence Layer
- RESPONSIBILITY: Durability policy, tiering, archive, retention
- OWNER: Durability Steward
- BOUNDARY: Must not own application interface or reasoning semantics
- INPUTS: Durable write requests, archive requests, restore requests
- OUTPUTS: Durability acknowledgements, tiering results, retention state
- PUBLIC-CONTRACTS: Persistence Layer -> Storage Layer, Persistence Layer -> Memory Layer
- DEPENDENCIES: Storage Layer, Memory Layer
- DEPENDENTS: Storage Layer, Memory Layer
- OWNED-PATHS: agents/persistence/**
- SHARED-PATHS: docs/architecture/**
- FORBIDDEN-PATHS: application/**, knowledge/**, compute/**, storage/**, memory/**
- STATUS: PLANNED
