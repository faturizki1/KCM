# CONFLICTS

## Purpose
This document records contradictions or unresolved points discovered during bootstrap so they are not silently resolved by assumption.

## Open Conflicts

### CONFLICT-001
- TYPE: Ownership ambiguity
- SOURCE-A: REPOSITORY-INVENTORY.md
- SOURCE-B: OWNERSHIP-MATRIX.md
- DESCRIPTION: Several documents are currently documented as shared governance artifacts but do not yet have a designated primary owner.
- WHITEPAPER-REFERENCE: KCM-WHITEPAPER.md sections on architecture and subsystem boundaries
- IMPACT: Future engineering work may assign conflicting ownership.
- PROPOSED-RESOLUTION: Assign a primary owner for documentation artifacts through architecture review.
- STATUS: OPEN

### CONFLICT-002
- TYPE: Contract incompleteness
- SOURCE-A: SUBSYSTEM-CONTRACTS.md
- SOURCE-B: Whitepaper architecture sections
- DESCRIPTION: The whitepaper defines architecture layers and principles, but not concrete subsystem wire formats or schemas.
- WHITEPAPER-REFERENCE: KCM-WHITEPAPER.md sections on layered architecture and deterministic reasoning
- IMPACT: Concrete implementation contracts remain undefined.
- PROPOSED-RESOLUTION: Keep these as BLOCKED/UNDEFINED until a later architecture review.
- STATUS: OPEN
