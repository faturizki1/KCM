# DEPENDENCY GRAPH

## Purpose
This document defines the official dependency graph for the bounded subsystems derived from the whitepaper. It distinguishes allowed, forbidden, circular, optional, and infrastructure dependencies.

## Official Dependency Graph
```text
Application Layer
  -> Knowledge Layer
  -> (optional) Compute Layer for execution-aware workflows

Knowledge Layer
  -> Compute Layer
  -> Storage Layer

Compute Layer
  -> Storage Layer
  -> Memory Layer (for hot-path access optimization)

Storage Layer
  -> Memory Layer
  -> Persistence Layer

Memory Layer
  -> Storage Layer
  -> Persistence Layer
```

## Allowed Dependencies
- Application Layer -> Knowledge Layer
- Knowledge Layer -> Compute Layer
- Knowledge Layer -> Storage Layer
- Compute Layer -> Storage Layer
- Storage Layer -> Memory Layer
- Storage Layer -> Persistence Layer
- Memory Layer -> Storage Layer
- Memory Layer -> Persistence Layer

## Forbidden Dependencies
- Application Layer -> Storage Layer directly for canonical semantic operations
- Knowledge Layer -> Persistence Layer directly for canonical knowledge semantics
- Compute Layer -> Persistence Layer directly as a substitute for Storage Layer
- Memory Layer -> Application Layer for semantic state propagation
- Any subsystem -> another subsystem in a way that bypasses the defined contract

## Circular Dependency Rules
- No circular dependency is allowed among the core architecture layers.
- Any future cross-cutting concern must be expressed through an integration boundary rather than a circular dependency.

## Optional Dependencies
- Application Layer may optionally use execution-adjacent services from Compute Layer when workflow context requires it.
- Memory Layer is optional for performance optimization and should not be considered mandatory for correctness semantics.

## Infrastructure Dependency
- Persistence Layer is an infrastructure dependency of Storage Layer and Memory Layer for durability and recovery.
- Storage Layer is an infrastructure dependency of Knowledge Layer and Compute Layer for physical access.

## Assumptions and Blocked Decisions
- The whitepaper does not define an explicit direct dependency from Application Layer to Storage Layer; this is marked as ASSUMPTION and is not adopted as a core rule.
- The whitepaper does not define a concrete implementation mechanism for memory prefetch coordination; this remains an implementation assumption and is not treated as architectural truth.
