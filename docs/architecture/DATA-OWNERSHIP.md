# DATA OWNERSHIP

## Purpose
This document freezes authoritative ownership of major data concepts so that no two subsystems claim authority over the same data without explicit review.

| Data Concept | Producer | Owner | Readers | Writers | Lifecycle Owner | Persistence Owner | Mutation Authority | Serialization Responsibility | Compatibility Responsibility |
|---|---|---|---|---|---|---|---|---|---|
| Knowledge Artifact | Knowledge Layer | Knowledge Layer | Application Layer, Compute Layer, Storage Layer | Knowledge Layer | Knowledge Layer | Storage Layer | Knowledge Layer | Knowledge Layer | Knowledge Layer |
| Query Intent | Application Layer | Application Layer | Knowledge Layer, Compute Layer | Application Layer | Application Layer | None | Application Layer | Application Layer | Application Layer |
| Execution Result | Compute Layer | Compute Layer | Application Layer, Knowledge Layer | Compute Layer | Compute Layer | None | Compute Layer | Compute Layer | Compute Layer |
| Storage Record | Storage Layer | Storage Layer | Compute Layer, Knowledge Layer | Storage Layer | Storage Layer | Storage Layer | Storage Layer | Storage Layer | Storage Layer |
| Cache Page | Memory Layer | Memory Layer | Storage Layer | Memory Layer | Memory Layer | None | Memory Layer | Memory Layer | Memory Layer |
| Durable Record | Persistence Layer | Persistence Layer | Storage Layer, Memory Layer | Persistence Layer | Persistence Layer | Persistence Layer | Persistence Layer | Persistence Layer | Persistence Layer |

## Ownership Rule
One authoritative owner is assigned per data concept. Other subsystems may consume the data but must not claim ownership over it.
