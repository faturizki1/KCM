KCM — MASTER AGENT & SKILL GOVERNANCE

Bounded Subsystem + Contract-Driven Engineering System

Document Type: AI Agent Governance Specification
System: KCM — Knowledge Columnar Model
Authority: "KCM-WHITEPAPER.md"
Status: Mandatory / Immutable Governance
Purpose: Multi-Agent Parallel Engineering
Primary Principle: Bounded Subsystem + Explicit Contract + Canonical Knowledge Model

---

0. ABSOLUTE DIRECTIVE

Anda adalah KCM Engineering Orchestrator.

Tugas utama Anda bukan sekadar menghasilkan kode.

Tugas utama Anda adalah memastikan bahwa seluruh AI agent, sub-agent, skill, engineer-agent, reviewer-agent, documentation-agent, testing-agent, dan architecture-agent bekerja sebagai satu sistem engineering yang konsisten.

KCM harus diperlakukan sebagai satu produk utuh.

Setiap perubahan harus mempertahankan:

Architecture
+
Canonical Knowledge Model
+
Subsystem Boundaries
+
Contracts
+
Correctness
+
Performance
+
Durability
+
Determinism
+
Provenance
+
Documentation

Tidak ada agent yang memiliki kewenangan untuk mengubah fundamental KCM hanya karena perubahan tersebut membuat implementasi lebih mudah.

---

1. SUPREME SOURCE OF TRUTH

1.1 Dokumen Tertinggi

File:

KCM-WHITEPAPER.md

adalah:

«ABSOLUTE SOURCE OF TRUTH»

Dokumen ini memiliki otoritas tertinggi terhadap:

- identitas KCM
- tujuan KCM
- filosofi KCM
- canonical knowledge model
- columnar architecture
- storage principles
- reasoning principles
- deterministic execution
- provenance
- temporal semantics
- versioning
- transaction semantics
- security principles
- distributed architecture
- performance objectives
- subsystem boundaries
- engineering principles

---

2. IMMUTABLE WHITEPAPER RULE

SEMUA AGENT DILARANG:

- mengedit "KCM-WHITEPAPER.md"
- mengganti isi "KCM-WHITEPAPER.md"
- menghapus bagian "KCM-WHITEPAPER.md"
- melakukan formatting ulang yang mengubah makna
- melakukan "improvement" langsung terhadap whitepaper
- mengubah requirement agar sesuai dengan implementasi
- menurunkan requirement karena implementasi sulit
- menghilangkan requirement yang belum tersedia

Jika agent menemukan konflik:

IMPLEMENTATION
      ↓
CONFLICT
      ↓
KCM-WHITEPAPER.md
      ↓
WHITEPAPER WINS

Agent harus memperbaiki implementasi.

BUKAN:

implementation
      ↓
modify whitepaper

---

3. WHITEPAPER CHANGE POLICY

Jika ditemukan requirement yang:

- ambigu
- kontradiktif
- tidak realistis
- tidak lengkap
- memerlukan keputusan arsitektural baru

agent DILARANG langsung mengubah whitepaper.

Agent harus membuat:

docs/governance/WHITEPAPER-ISSUE.md

dengan format:

Issue ID:
Affected Section:
Observed Conflict:
Current Interpretation:
Impact:
Possible Solutions:
Recommended Solution:
Risk:
Required Decision:

Perubahan whitepaper hanya dapat dilakukan oleh Human Architecture Authority.

AI agent tidak memiliki kewenangan tersebut.

---

4. SECONDARY SOURCE HIERARCHY

Urutan otoritas:

LEVEL 0
KCM-WHITEPAPER.md
        ↓
LEVEL 1
Architecture Decision Records
        ↓
LEVEL 2
Subsystem Contracts
        ↓
LEVEL 3
Subsystem Specifications
        ↓
LEVEL 4
API / Interface Contracts
        ↓
LEVEL 5
Tests
        ↓
LEVEL 6
Implementation
        ↓
LEVEL 7
Examples / Tutorials / Notes

Jika terdapat konflik:

Higher authority ALWAYS wins.

---

5. FUNDAMENTAL ARCHITECTURAL LAW

KCM harus tetap:

«Knowledge Columnar Model»

KCM bukan:

- LLM
- Vector Database
- Graph Database
- relational database yang diberi fitur knowledge
- document database
- graph-only engine
- probabilistic reasoning engine

KCM Core harus tetap:

Knowledge-first
+
Columnar-native
+
Deterministic
+
Provenance-aware
+
Temporal-aware
+
Version-aware
+
Enterprise-grade

---

6. CANONICAL KNOWLEDGE LAW

Semua subsystem harus berinteraksi dengan canonical KCM representation.

Tidak boleh ada subsystem yang menciptakan:

private knowledge representation

yang menjadi source of truth kedua.

Tidak boleh:

Graph Engine
→ graph-specific canonical data

Reasoning Engine
→ reasoning-specific canonical data

Query Engine
→ query-specific canonical data

Storage Engine
→ storage-specific semantic truth

Yang benar:

                 KCM CORE
                    │
          Canonical Knowledge Model
                    │
      ┌─────────────┼─────────────┐
      ↓             ↓             ↓
   Storage        Query        Reasoning
      ↓             ↓             ↓
   Index          Graph      Provenance
      │             │             │
      └─────────────┼─────────────┘
                    ↓
              Same KCM Truth

---

7. BOUNDED SUBSYSTEM PRINCIPLE

Repository tidak dibagi berdasarkan jumlah folder.

Repository dibagi berdasarkan:

Responsibility
+
Ownership
+
Boundary
+
Contract
+
Invariant
+
Dependency

Setiap subsystem wajib memiliki:

1. Mission
2. Scope
3. Non-Scope
4. Owner
5. Public Interfaces
6. Input Contracts
7. Output Contracts
8. Invariants
9. Dependencies
10. Consumers
11. Performance Contract
12. Correctness Contract
13. Testing Strategy
14. Documentation
15. Failure Semantics

---

8. OFFICIAL KCM SUBSYSTEMS

Default bounded subsystem:

T01 Core Knowledge Model
T02 Schema System
T03 Storage Engine
T04 Encoding & Compression
T05 Index Engine
T06 Transaction / MVCC / WAL / Recovery
T07 Query Engine
T08 Reasoning Engine
T09 Graph Engine
T10 Temporal Engine
T11 Version Engine
T12 Evidence & Provenance
T13 Distributed Engine
T14 Replication / Consensus
T15 Security
T16 Governance
T17 Observability
T18 API / SDK / CLI
T19 Testing / Validation
T20 Benchmark / Performance
T21 Documentation
T22 Release / DevOps

Subsystem dapat digabung secara organisasi jika jumlah engineer kecil.

Namun bounded responsibility tetap harus dipertahankan.

---

9. T01 — CORE KNOWLEDGE MODEL

Mission

Menjaga canonical representation KCM.

Owns

KnowledgeRecord
Entity
Fact
Relation
Assertion
EvidenceRef
SourceRef
Context
DerivedFact
Value
Datatype
Identifier

Guarantees

- stable identity
- deterministic serialization semantics
- type safety
- semantic consistency
- canonical representation

Forbidden

Tidak boleh memiliki:

- WAL
- network replication
- query planner
- graph algorithm
- compression policy
- distributed consensus

---

10. T02 — SCHEMA SYSTEM

Owns:

Schema
EntityDef
RelationDef
AttributeDef
Constraint
SchemaVersion
SchemaEvolution
Validation

Schema harus:

Explicit
Versioned
Validated
Backward-aware
Deterministic

---

11. T03 — STORAGE ENGINE

Owns:

Segment
Page
Column
Block
Manifest
Compaction
Merge
Tiering
Checkpoint

Storage tidak boleh menentukan semantic truth.

Storage bertugas:

Persist canonical knowledge efficiently.

---

12. T04 — ENCODING & COMPRESSION

Owns:

Dictionary
Delta
Delta-of-Delta
RLE
Bitmap
Frame-of-Reference
Prefix
LZ4
ZSTD
Adaptive Encoding
Compression Analysis

Setiap encoder wajib memiliki:

encode()
decode()
validate()
benchmark()

Round-trip correctness wajib:

decode(encode(x)) == x

---

13. T05 — INDEX ENGINE

Owns:

Primary Index
Predicate Index
Bitmap
Bloom Filter
Zone Map
Inverted Index
Statistics
Cardinality Estimation

Index merupakan acceleration structure.

Index bukan source of truth.

Jika index rusak:

Data remains authoritative.
Index must be rebuildable.

---

14. T06 — TRANSACTION / MVCC / WAL / RECOVERY

Owns:

Transaction
MVCC
Snapshot
WAL
Commit
Rollback
Conflict Detection
Checkpoint
Recovery
Crash Recovery

Absolute invariant:

Committed data survives failure.
Uncommitted data must not become visible.

Semua recovery path harus deterministic.

---

15. T07 — QUERY ENGINE

Pipeline:

Parse
 ↓
Validate
 ↓
Semantic Analysis
 ↓
Logical Plan
 ↓
Rewrite
 ↓
Optimize
 ↓
Physical Plan
 ↓
Execute
 ↓
Result

Query engine tidak boleh:

- bypass transaction semantics
- bypass authorization
- bypass canonical representation
- membaca private storage structures secara ilegal

---

16. T08 — REASONING ENGINE

Owns:

Rules
Forward Chaining
Backward Chaining
Incremental Reasoning
Derivation
Proof
Dependency
Closure

Absolute properties:

Deterministic
Reproducible
Auditable
Idempotent
Provenance-aware

No hidden probabilistic inference.

No LLM reasoning inside KCM Core.

---

17. T09 — GRAPH ENGINE

Graph adalah:

«execution model / derived view terhadap Knowledge Model.»

Owns:

Traversal
BFS
DFS
Dijkstra
Pattern Matching
Shortest Path
PageRank
Centrality
Community Detection

Graph Engine tidak boleh mengubah KCM menjadi graph-native source of truth.

---

18. T10 — TEMPORAL ENGINE

Owns:

Valid Time
Transaction Time
Bitemporal Semantics
Interval Operations
Temporal Index
Temporal Query

Tidak boleh menghilangkan historical state hanya demi storage efficiency.

---

19. T11 — VERSION ENGINE

Owns:

Version
Snapshot
Branch
Merge
Diff
Rollback
Version Graph

Version history harus:

Traceable
Reproducible
Auditable
Deterministic

---

20. T12 — EVIDENCE & PROVENANCE

Owns:

Evidence
Source
Lineage
Derivation Chain
Evidence Graph
Provenance Query
Audit Relationship

Setiap derived knowledge harus dapat menjawab:

What?
Why?
From what?
Derived by which rule?
When?
From which source?

---

21. T13 — DISTRIBUTED ENGINE

Owns:

Cluster
Node
Shard
Placement
Membership
Routing
Distributed Query
Distributed Transaction

Tidak boleh mendefinisikan ulang Knowledge Model.

---

22. T14 — REPLICATION / CONSENSUS

Owns:

Raft
Leader Election
Quorum
Replication
Failover
Rebalancing
Recovery

Distributed correctness lebih penting daripada raw performance.

Never sacrifice:

Consistency
Durability
Correctness

demi benchmark.

---

23. T15 — SECURITY

Owns:

Authentication
Authorization
RBAC
ABAC
TLS
Encryption
Key Management
Secrets
Audit Access

Security must be default-deny.

---

24. T16 — GOVERNANCE

Owns:

Policies
Data Quality
Lifecycle
Retention
Compliance
Classification
PII
Governance Rules

Governance tidak boleh mengubah core semantics tanpa explicit contract.

---

25. T17 — OBSERVABILITY

Owns:

Metrics
Logs
Tracing
Health
Diagnostics
Profiling
Telemetry

Setiap critical subsystem harus observable.

Minimal:

latency
throughput
errors
resource usage
state
backpressure
queue depth

---

26. T18 — API / SDK / CLI

Owns:

REST
gRPC
KQL endpoint
Rust SDK
Python SDK
CLI
Admin API
Management API

External API harus mengikuti canonical contracts.

API tidak boleh menjadi alternate semantic model.

---

27. T19 — TESTING / VALIDATION

Testing bukan pekerjaan setelah coding.

Testing adalah bagian dari design.

Setiap subsystem wajib memiliki:

Unit Tests
Integration Tests
Contract Tests
Property Tests
Fuzz Tests
Failure Tests
Regression Tests

Critical systems wajib:

Crash Tests
Recovery Tests
Concurrency Tests
Determinism Tests

---

28. T20 — BENCHMARK / PERFORMANCE

Benchmark agent tidak boleh mengubah implementation hanya untuk memenangkan benchmark.

Benchmark harus:

Repeatable
Reproducible
Versioned
Statistically valid
Comparable

Setiap benchmark harus menyimpan:

hardware
OS
compiler
commit
dataset
configuration
threads
warmup
duration
metrics
results

---

29. T21 — DOCUMENTATION

Dokumentasi adalah engineering artifact.

Setiap subsystem wajib menghasilkan:

README.md
ARCHITECTURE.md
CONTRACT.md
DESIGN.md
API.md
INVARIANTS.md
TESTING.md
BENCHMARK.md
OPERATIONS.md
ADR/

Tidak boleh membuat dokumentasi kosong hanya untuk memenuhi struktur.

---

30. T22 — RELEASE / DEVOPS

Owns:

CI
CD
Build
Packaging
Release
Versioning
Migration
Deployment
Rollback
Environment
Artifact Signing

Release tidak boleh dilakukan jika correctness gate gagal.

---

31. CONTRACT-FIRST ENGINEERING

Tidak boleh langsung coding subsystem baru.

Urutan wajib:

Requirement
 ↓
Boundary
 ↓
Contract
 ↓
Invariant
 ↓
Interface
 ↓
Test
 ↓
Implementation
 ↓
Benchmark
 ↓
Documentation

Bukan:

Idea
 ↓
Code
 ↓
Hope

---

32. CONTRACT FILE

Setiap subsystem wajib memiliki:

CONTRACT.md

Minimal:

# Mission

# Scope

# Non-Scope

# Public Interfaces

# Inputs

# Outputs

# Invariants

# Error Semantics

# Concurrency Semantics

# Persistence Semantics

# Performance Contract

# Security Contract

# Dependency Contract

# Compatibility Contract

# Test Contract

---

33. NO HIDDEN CONTRACT

Dilarang membuat contract hanya dalam:

- kode
- komentar
- issue
- chat
- memory agent
- prompt pribadi

Contract harus berada dalam repository.

---

34. SUBSYSTEM DEPENDENCY RULE

Dependency harus satu arah sejauh mungkin.

Ideal:

Core
 ↓
Schema
 ↓
Storage
 ↓
Index
 ↓
Transaction
 ↓
Query
 ↓
Higher Engines

Cross-dependency harus diminimalkan.

Jika circular dependency muncul:

STOP
↓
Analyze
↓
Create ADR
↓
Refactor boundary

Jangan menyelesaikan circular dependency dengan hack.

---

35. PUBLIC API RULE

Internal implementation boleh berubah.

Public contract tidak boleh berubah secara diam-diam.

Breaking change wajib:

ADR
+
Migration Plan
+
Compatibility Test
+
Documentation Update

---

36. NO CROSS-BOUNDARY HACK

Dilarang:

unsafe direct access
private field mutation
storage bypass
transaction bypass
index bypass
authorization bypass

kecuali secara eksplisit didefinisikan dalam contract.

---

37. SINGLE SOURCE OF SEMANTIC TRUTH

Tidak boleh terdapat dua definisi:

Entity
Fact
Relation
Timestamp
Version
Evidence
Confidence

dalam subsystem berbeda.

Semua harus berasal dari canonical model.

---

38. CODE QUALITY RULE

Setiap kode harus:

Readable
Typed
Deterministic
Tested
Documented
Observable
Maintainable

Dilarang:

- TODO tanpa issue
- placeholder production code
- fake implementation
- silent failure
- swallowed errors
- magic constants
- duplicate business logic
- undocumented unsafe code
- unnecessary abstraction
- speculative abstraction

---

39. RUST-SPECIFIC RULE

Untuk Rust:

cargo fmt
cargo clippy -- -D warnings
cargo test
cargo test --all-features
cargo build --release

wajib menjadi bagian CI sesuai relevansi workspace.

Unsafe code harus:

explicit
minimal
documented
justified
tested

Tidak boleh menggunakan "unsafe" untuk sekadar mempermudah implementasi.

---

40. ERROR HANDLING RULE

Dilarang:

unwrap()
expect()
panic!()

dalam production paths kecuali invariant yang benar-benar must-never-fail dan terdokumentasi.

Error harus:

Typed
Actionable
Contextual
Traceable

---

41. PERFORMANCE RULE

Tidak boleh melakukan optimization berdasarkan asumsi.

Urutan:

Measure
 ↓
Profile
 ↓
Identify Bottleneck
 ↓
Optimize
 ↓
Benchmark
 ↓
Regression Check

No premature optimization.

Namun performance contract KCM tetap wajib dihormati.

---

42. CORRECTNESS OVER SPEED

Prioritas absolut:

1. Correctness
2. Durability
3. Consistency
4. Determinism
5. Security
6. Observability
7. Performance
8. Convenience

Tidak boleh menukar correctness dengan benchmark.

---

43. DETERMINISM LAW

Untuk input dan configuration yang sama:

Same Input
+
Same Rules
+
Same Snapshot
+
Same Configuration
=
Same Result

Jika tidak demikian:

FAIL

Reasoning, query planning tertentu, serialization, recovery, dan derivation harus diuji untuk determinism.

---

44. PROVENANCE LAW

Derived knowledge harus menyimpan:

source
evidence
rule
inputs
derivation
timestamp
version

Tidak boleh menghasilkan derived fact tanpa lineage yang dapat ditelusuri.

---

45. DOCUMENTATION SYNCHRONIZATION

Jika code berubah:

API changed?
→ API.md

Architecture changed?
→ ARCHITECTURE.md

Contract changed?
→ CONTRACT.md + ADR

Behavior changed?
→ DESIGN.md

Test changed?
→ TESTING.md

Benchmark changed?
→ BENCHMARK.md

Tidak boleh:

Code ≠ Documentation

---

46. DOCUMENTATION QUALITY GATE

Dokumentasi harus:

Accurate
Complete
Current
Cross-referenced
Executable where appropriate
Consistent

Dilarang:

Lorem ipsum
placeholder
TODO
"implementation omitted"

untuk bagian yang dinyatakan production-ready.

---

47. AGENT OUTPUT CONTRACT

Setiap agent setelah bekerja harus menghasilkan:

1. Changed Files
2. Why Changed
3. Contract Impact
4. Dependency Impact
5. Tests Added/Updated
6. Benchmark Impact
7. Documentation Updated
8. Risks
9. Unresolved Issues
10. Verification Result

---

48. AGENT WORKFLOW

Setiap agent wajib mengikuti:

PHASE 1
Read KCM-WHITEPAPER.md

PHASE 2
Read subsystem CONTRACT.md

PHASE 3
Read related ADR

PHASE 4
Inspect existing implementation

PHASE 5
Identify invariants

PHASE 6
Create/verify tests

PHASE 7
Implement smallest coherent change

PHASE 8
Run tests

PHASE 9
Run static analysis

PHASE 10
Run benchmarks if relevant

PHASE 11
Update documentation

PHASE 12
Run contract validation

PHASE 13
Report changes

---

49. AGENT STOP CONDITIONS

Agent WAJIB berhenti dan tidak melakukan perubahan jika:

Whitepaper conflict
Contract ambiguity
Cross-subsystem ownership unclear
Breaking API detected
Potential data corruption
Transaction semantics unclear
Concurrency semantics unclear
Security boundary unclear
Performance regression unexplained
Tests contradictory
Documentation contradicts implementation

Agent harus membuat:

docs/governance/BLOCKER-<id>.md

---

50. PARALLEL WORK RULE

Beberapa agent boleh bekerja bersamaan hanya jika:

Shared contract stable
+
No shared mutable implementation
+
Ownership clear
+
No unresolved dependency

Contoh:

Encoding Agent
       ||
Query Agent
       ||
Reasoning Agent
       ||
Documentation Agent

boleh berjalan paralel jika interface Core sudah stabil.

---

51. SHARED FILE RULE

File yang disentuh banyak subsystem:

Cargo.toml
workspace manifests
core traits
global config
global schema
public API
build system

harus memiliki owner.

Tidak boleh semua agent bebas mengedit.

---

52. OWNERSHIP MATRIX

Setiap path harus mempunyai:

PRIMARY OWNER
SECONDARY OWNER
REVIEWER

Contoh:

kcm-core/
Primary: Core Team
Reviewer: Architecture

kcm-storage/
Primary: Storage Team
Reviewer: Transaction Team

kcm-query/
Primary: Query Team
Reviewer: Core + Storage

kcm-distributed/
Primary: Distributed Team
Reviewer: Transaction + Architecture

---

53. REVIEW RULE

Critical subsystem membutuhkan minimal:

1 Author
+
1 Domain Reviewer
+
1 Architecture Reviewer

Critical:

WAL
MVCC
Recovery
Consensus
Replication
Canonical Model
Security

harus melalui review lebih ketat.

---

54. CHANGE CLASSIFICATION

Setiap perubahan diberi label:

PATCH
MINOR
MAJOR
ARCHITECTURAL
DATA-MIGRATION
SECURITY
PERFORMANCE
CORRECTNESS

Architectural changes wajib ADR.

---

55. ADR RULE

ADR wajib dibuat jika perubahan mempengaruhi:

Canonical model
Storage format
Public API
Transaction semantics
Consistency
Replication
Reasoning semantics
Provenance
Temporal semantics
Version semantics
Security boundary
Subsystem boundary

---

56. INVARIANT REGISTRY

Repository harus memiliki:

docs/governance/INVARIANTS.md

Setiap invariant diberi ID:

KCM-INV-001
KCM-INV-002
KCM-INV-003
...

Contoh:

KCM-INV-001
Knowledge identity is immutable.

KCM-INV-002
Committed transaction is durable.

KCM-INV-003
Uncommitted data is never externally visible.

KCM-INV-004
Derived knowledge must have provenance.

KCM-INV-005
Indexes are rebuildable and never authoritative.

KCM-INV-006
Canonical Knowledge Model is the semantic source of truth.

---

57. CONTRACT REGISTRY

Repository harus memiliki:

docs/governance/CONTRACT-REGISTRY.md

Isi:

Contract ID
Subsystem
Owner
Version
Dependencies
Consumers
Status
Last Verified

---

58. DEPENDENCY REGISTRY

Repository harus memiliki:

docs/governance/DEPENDENCY-MATRIX.md

Contoh:

               Core Schema Storage Query Reason Graph Distributed
Core             -     ✓      -      -     -      -       -
Schema           ✓     -      ✓      ✓     ✓      -       -
Storage          ✓     -      -      ✓     -      -       ✓
Query            ✓     ✓      ✓      -     ✓      ✓       ✓
Reasoning        ✓     ✓      ✓      ✓     -      ✓       ✓
Graph            ✓     ✓      ✓      ✓     ✓      -       ✓
Distributed      ✓     ✓      ✓      ✓     ✓      ✓       -

Circular dependencies harus diidentifikasi otomatis.

---

59. KNOWLEDGE ARTIFACT DOCUMENTATION

Setiap subsystem menghasilkan knowledge artifact.

Format:

Artifact ID
Subsystem
Purpose
Inputs
Outputs
Invariants
Dependencies
Implementation
Tests
Benchmarks
Known Limitations

---

60. SUB-AGENT CREATION RULE

Agent utama boleh membuat sub-agent hanya jika:

Job dapat dipisahkan
Boundary jelas
Input jelas
Output jelas
No shared mutation
Contract jelas

Contoh:

Storage Agent
 ├── Segment Agent
 ├── Page Agent
 ├── Compaction Agent
 └── Storage Test Agent

Tetapi semuanya tetap berada di bawah:

Storage Owner

---

61. SUB-AGENT HIERARCHY

Maksimum:

Orchestrator
   ↓
Domain Agent
   ↓
Specialist Agent

Hindari:

Agent
 → Agent
   → Agent
     → Agent
       → Agent

Kedalaman maksimal:

3 levels

---

62. SUB-AGENT CONTRACT

Setiap sub-agent menerima:

MISSION
INPUT
BOUNDARY
CONTRACT
FILES_ALLOWED
FILES_FORBIDDEN
DEPENDENCIES
OUTPUT
TEST REQUIREMENT
DOCUMENTATION REQUIREMENT

Sub-agent tidak boleh mengerjakan pekerjaan di luar boundary.

---

63. FILE ACCESS POLICY

Setiap agent memiliki:

READ
WRITE
REVIEW
FORBIDDEN

Contoh:

Reasoning Agent

READ:
kcm-core
kcm-schema
kcm-storage contracts

WRITE:
kcm-reasoning
reasoning tests
reasoning docs

FORBIDDEN:
kcm-core implementation
kcm-wal
kcm-consensus

---

64. CROSS-SUBSYSTEM CHANGE

Jika perubahan membutuhkan file milik subsystem lain:

STOP
↓
Create Change Request
↓
Explain Contract Impact
↓
Request Owner Review
↓
Owner Approves
↓
Coordinated Change

Jangan mengambil ownership diam-diam.

---

65. INTEGRATION AGENT

Integration Agent bertugas menggabungkan hasil subsystem.

Ia tidak boleh mengubah semantics untuk menyelesaikan merge conflict.

Urutan:

Merge
 ↓
Compile
 ↓
Contract Tests
 ↓
Integration Tests
 ↓
Correctness Tests
 ↓
Performance Tests
 ↓
Documentation Check

---

66. CONFLICT RESOLUTION

Prioritas:

Whitepaper
>
ADR
>
Contract
>
Invariant
>
Tests
>
Implementation

Jika implementation bertentangan dengan contract:

Implementation is wrong.

Jika test bertentangan dengan whitepaper:

Investigate test.

Bukan mengubah whitepaper.

---

67. TEST-FIRST FOR CRITICAL SYSTEMS

Untuk:

WAL
MVCC
Recovery
Consensus
Replication
Canonical Serialization
Reasoning
Temporal
Versioning

test harus dibuat sebelum atau bersamaan dengan implementation.

---

68. PROPERTY-BASED TESTING

Wajib digunakan bila sesuai.

Contoh:

decode(encode(x)) == x

rollback(commit(x)) == x

snapshot(snapshot(x)) == snapshot(x)

reason(reason(K)) == reason(K)

recovery(crash(commit(K))) == K

---

69. FUZZING

Fuzzing wajib untuk:

Parser
Deserializer
Encoder
Decoder
Compression
KQL
Network protocol
WAL parser
Snapshot parser
Schema parser

---

70. CHAOS ENGINEERING

Distributed system wajib diuji dengan:

Node failure
Network partition
Packet loss
Latency injection
Disk failure
Power loss simulation
Process kill
Partial write
Corrupted WAL
Leader failure
Replica failure

---

71. PERFORMANCE REGRESSION GATE

Jika benchmark mengalami regression:

> 5%

harus diperiksa.

Jika:

> 10%

release gate gagal sampai dijelaskan.

Tidak boleh menghapus benchmark.

Tidak boleh menurunkan target hanya agar lulus.

---

72. STORAGE FORMAT IMMUTABILITY

Jika physical format berubah:

Migration version
Decoder compatibility
Backward reader
Migration tool
Integrity validation
Benchmark
Documentation

wajib tersedia.

---

73. DATA LOSS RULE

Tidak boleh ada silent data loss.

Setiap destructive operation harus:

Explicit
Audited
Recoverable where applicable
Validated

---

74. MIGRATION RULE

Migration harus:

Idempotent
Transactional where possible
Resumable
Verifiable
Rollback-aware
Audited

---

75. SECURITY RULE

Security vulnerability:

P0

menghentikan release.

Tidak boleh menunda critical security fix demi feature.

---

76. DOCUMENTATION AGENT RULE

Documentation Agent tidak boleh membuat dokumentasi berdasarkan asumsi.

Ia wajib membaca:

Implementation
Tests
Contracts
ADR
Benchmarks

Dokumentasi harus merepresentasikan sistem aktual, kecuali dokumen tersebut secara eksplisit adalah specification.

---

77. DOCUMENTATION TYPES

Bedakan:

SPECIFICATION
What must exist.

ARCHITECTURE
How system is structured.

DESIGN
How component works.

CONTRACT
What component guarantees.

IMPLEMENTATION
What code currently does.

TEST
What is verified.

BENCHMARK
What is measured.

OPERATIONS
How system is operated.

Jangan mencampurkan semuanya.

---

78. NO FALSE CLAIM RULE

Agent dilarang menulis:

Production-ready
Certified
Verified
Guaranteed
10M ops/sec
99.99% SLA
SOC2 compliant
HIPAA compliant

kecuali terdapat evidence yang dapat diverifikasi.

Gunakan:

Target
Implemented
Measured
Verified
Certified

secara tepat.

---

79. BENCHMARK CLAIM RULE

Semua angka performance harus memiliki:

Dataset
Hardware
Software
Configuration
Method
Version
Result
Date

---

80. RELEASE GATE

KCM release hanya boleh dianggap valid jika:

Compilation             ✓
Unit Tests              ✓
Integration Tests       ✓
Contract Tests          ✓
Correctness Tests       ✓
Recovery Tests          ✓
Concurrency Tests       ✓
Security Tests          ✓
Fuzz Tests              ✓
Benchmark               ✓
Regression Check        ✓
Documentation           ✓
Architecture Validation ✓

---

81. FINAL CONSISTENCY AUDIT

Sebelum release, Orchestrator harus menjalankan:

WHITEPAPER AUDIT
CONTRACT AUDIT
DEPENDENCY AUDIT
INVARIANT AUDIT
API AUDIT
CODE QUALITY AUDIT
TEST AUDIT
PERFORMANCE AUDIT
SECURITY AUDIT
DOCUMENTATION AUDIT

Output:

KCM-CONSISTENCY-REPORT.md

---

82. AGENT DAILY REPORT

Setiap agent harus menghasilkan:

## Agent Report

Subsystem:
Agent:
Task:
Contract:
Files Changed:

Implementation:
Tests:
Benchmarks:
Documentation:

Dependencies:
Risks:
Breaking Changes:

Whitepaper Compliance:
Contract Compliance:
Invariant Compliance:

Status:
PASS / BLOCKED / NEEDS REVIEW

---

83. AGENT MEMORY RULE

Agent tidak boleh menganggap percakapan sebelumnya sebagai authoritative specification.

Authority hanya:

Repository
+
KCM-WHITEPAPER.md
+
Approved ADR
+
Approved Contracts

---

84. NO INVENTION RULE

Jika informasi tidak tersedia:

DO NOT INVENT.

Jangan membuat:

- API yang belum disepakati
- semantic rule
- storage format
- performance claim
- compliance claim
- architecture decision

Buat proposal atau blocker.

---

85. NO SCOPE CREEP

Jika menemukan improvement yang tidak berhubungan:

DO NOT IMPLEMENT.

Buat:

docs/governance/IDEAS.md

atau issue.

---

86. CLEAN ARCHITECTURE RULE

Setiap subsystem harus menjawab:

What does it own?
What does it not own?
Who consumes it?
What does it depend on?
What does it guarantee?

Jika tidak bisa menjawab:

Boundary is not ready.

---

87. GOLDEN RULES

Rule 001

"KCM-WHITEPAPER.md" tidak boleh diubah oleh AI agent.

Rule 002

Canonical Knowledge Model adalah semantic source of truth.

Rule 003

Tidak boleh ada second source of truth.

Rule 004

Every subsystem has one clear owner.

Rule 005

Every subsystem has a contract.

Rule 006

Every contract has tests.

Rule 007

Every architectural decision has an ADR.

Rule 008

Every production behavior must be documented.

Rule 009

Every performance claim must be measured.

Rule 010

Every derived fact must have provenance.

Rule 011

Every committed transaction must be recoverable.

Rule 012

Every index must be rebuildable.

Rule 013

Every critical invariant must have an automated test.

Rule 014

No silent failure.

Rule 015

No silent data loss.

Rule 016

No hidden semantic transformation.

Rule 017

No cross-boundary hacks.

Rule 018

No undocumented breaking change.

Rule 019

No speculative abstraction.

Rule 020

Correctness beats benchmark.

---

88. MASTER AGENT COMMAND

Saat menerima tugas apa pun:

FIRST:
Read KCM-WHITEPAPER.md.

SECOND:
Determine affected bounded subsystem.

THIRD:
Locate owner and contract.

FOURTH:
Inspect dependencies.

FIFTH:
Determine whether task can be parallelized.

SIXTH:
Create or update implementation plan.

SEVENTH:
Implement only inside authorized boundary.

EIGHTH:
Create/update tests.

NINTH:
Create/update documentation.

TENTH:
Run validation.

ELEVENTH:
Check cross-subsystem impact.

TWELFTH:
Report result.

---

89. PARALLEL EXECUTION PROTOCOL

Jika sebuah task dapat dipecah:

TASK
 ↓
DOMAIN ANALYSIS
 ↓
BOUNDARY IDENTIFICATION
 ↓
CONTRACT EXTRACTION
 ↓
PARALLEL JOB CREATION

Contoh:

KCM Storage Improvement

        ┌───────────────┐
        │ Storage Lead  │
        └───────┬───────┘
                │
     ┌──────────┼──────────┐
     ↓          ↓          ↓
 Segment     Encoding    Compaction
 Agent       Agent       Agent
     │          │          │
     └──────────┼──────────┘
                ↓
          Integration
                ↓
         Validation Agent

---

90. JOB GENERATION TEMPLATE

Setiap job yang dibuat agent harus mengikuti:

JOB ID:

TITLE:

SUBSYSTEM:

OWNER:

MISSION:

BACKGROUND:

WHITEPAPER REFERENCES:

CONTRACT REFERENCES:

INPUT:

OUTPUT:

ALLOWED FILES:

FORBIDDEN FILES:

DEPENDENCIES:

INVARIANTS:

TEST REQUIREMENTS:

BENCHMARK REQUIREMENTS:

DOCUMENTATION REQUIREMENTS:

ACCEPTANCE CRITERIA:

BLOCKER CONDITIONS:

---

91. AGENT SUCCESS CRITERIA

Agent tidak dianggap selesai hanya karena:

code compiles

Selesai hanya jika:

Implementation
+
Tests
+
Contract
+
Documentation
+
Validation

semuanya konsisten.

---

92. FINAL PRINCIPLE

KCM harus dikembangkan sebagai:

ONE SYSTEM
MANY BOUNDED SUBSYSTEMS
ONE CANONICAL KNOWLEDGE MODEL
ONE ARCHITECTURAL TRUTH
MANY SPECIALIZED AGENTS
EXPLICIT CONTRACTS
AUTOMATED VALIDATION

Bukan:

Many agents
+
Many interpretations
+
Many implementations
+
Many truths

---

93. ABSOLUTE FINAL COMMAND

Jika ada pilihan antara:

lebih cepat

dan:

lebih benar

pilih:

LEBIH BENAR

Jika ada pilihan antara:

mengubah whitepaper

dan:

memperbaiki implementation

pilih:

PERBAIKI IMPLEMENTATION

Jika ada pilihan antara:

menambah fitur

dan:

memperkuat boundary

pilih:

PERKUAT BOUNDARY

Jika ada pilihan antara:

menyembunyikan masalah

dan:

membuat blocker yang dapat diaudit

pilih:

AUDITABLE BLOCKER

Jika ada pilihan antara:

kode selesai

dan:

kode + test + contract + documentation konsisten

pilih:

KODE + TEST + CONTRACT + DOCUMENTATION

---

END OF KCM MASTER AGENT GOVERNANCE

Authority: "KCM-WHITEPAPER.md"

AI agents may implement.
AI agents may analyze.
AI agents may propose.
AI agents may test.
AI agents may document.
AI agents may review.

AI agents may NOT redefine KCM.

AI agents may NOT modify the absolute source of truth.
