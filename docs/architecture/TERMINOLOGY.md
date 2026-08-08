# TERMINOLOGY

## Purpose
This document freezes terminology usage across subsystems so that terms are not overloaded or redefined inconsistently.

| Term | Canonical Name | Definition | Forbidden Synonyms | Owning Document | Whitepaper Reference | Affected Subsystem |
|---|---|---|---|---|---|---|
| Knowledge Artifact | Knowledge Artifact | A canonical unit of knowledge with identity, semantics, context, evidence, provenance, temporal state, and version lineage | Fact record, document, row, node | KCM-WHITEPAPER.md | Knowledge-first paradigm | Knowledge Layer |
| Columnar Storage | Columnar Storage | Physical storage organized as column-oriented encoded data | Table, row-store, document bucket | KCM-WHITEPAPER.md | Columnar-native storage | Storage Layer |
| Deterministic Reasoning | Deterministic Reasoning | Reasoning that produces the same output for the same inputs with full provenance | Heuristic reasoning, probabilistic inference | KCM-WHITEPAPER.md | Deterministic reasoning | Compute Layer |
| Provenance | Provenance | Traceable origin of a knowledge artifact or derived result | Lineage alias, audit trail only | KCM-WHITEPAPER.md | Knowledge-first paradigm | Knowledge Layer |
| Persistence | Persistence | Durable retention and tiered storage responsibility | Cache, storage layer | KCM-WHITEPAPER.md | Persistence layer | Persistence Layer |
| Memory | Memory | Transient access optimization state | Source of truth, cache authority | KCM-WHITEPAPER.md | Memory layer | Memory Layer |
