# Compute Layer Dependencies

## DIRECT DEPENDENCIES
- Knowledge Layer
- Storage Layer

## INDIRECT DEPENDENCIES
- None defined at bootstrap phase

## OPTIONAL DEPENDENCIES
- Memory Layer for hot-path access optimization only if explicitly required

## FORBIDDEN DEPENDENCIES
- Direct bypass of Knowledge Layer semantics
- Direct dependency on persistence semantics as a substitute for Storage Layer

## DEPENDENT SUBSYSTEMS
- Knowledge Layer

## Status
- Consistent with DEPENDENCY-GRAPH.md
