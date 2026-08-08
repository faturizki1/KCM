# ASSUMPTION REGISTER

## Purpose
This register records assumptions that were introduced during bootstrap and need explicit review before they can be treated as architectural truth.

| ASSUMPTION-ID | SUBSYSTEM | ASSUMPTION | WHY-NEEDED | WHITEPAPER-COVERAGE | RISK | AFFECTED-CONTRACT | AFFECTED-TASK | STATUS |
|---|---|---|---|---|---|---|---|---|
| ASM-001 | Application Layer | A request/response envelope can be defined as a future contract artifact | Needed for interface clarity | Partial: whitepaper defines layered architecture but not a concrete wire format | Medium | Application -> Knowledge contract | Interface task | PROPOSED |
| ASM-002 | Knowledge Layer | Knowledge artifacts can be represented by a future schema contract | Needed for semantic exchange clarity | Partial: whitepaper defines knowledge artifacts but not a concrete serialization format | Medium | Knowledge -> Compute / Storage contract | Artifact contract task | PROPOSED |
| ASM-003 | Compute Layer | Deterministic execution can be expressed through a future execution envelope | Needed for implementation planning | Partial: whitepaper defines deterministic reasoning | Medium | Compute -> Storage contract | Execution task | PROPOSED |
| ASM-004 | Storage Layer | Storage can be represented by a future physical contract | Needed for storage responsibility clarity | Partial: whitepaper defines columnar-native storage | Medium | Storage -> Memory / Persistence contract | Storage task | PROPOSED |
| ASM-005 | Memory Layer | Cache policy can be represented by a future memory contract | Needed for boundary clarity | Partial: whitepaper defines memory layer | Medium | Memory -> Storage / Persistence contract | Cache task | PROPOSED |
| ASM-006 | Persistence Layer | Tiering and retention can be expressed through a future durability contract | Needed for durability clarity | Partial: whitepaper defines persistence layer | Medium | Persistence -> Storage / Memory contract | Durability task | PROPOSED |
