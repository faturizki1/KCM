# AGENT.md

## KCM Engineering Foundation

This repository follows the principles defined in KCM-WHITEPAPER.md as the absolute source of truth.

## 1. Source of Truth
- Treat KCM-WHITEPAPER.md as the highest authority for product purpose, architecture, and constraints.
- Do not edit, move, rename, delete, or reformat KCM-WHITEPAPER.md.
- If requirements conflict with the whitepaper, follow the whitepaper and adjust implementation accordingly.

## 2. Repository Safety
- Preserve repository integrity and avoid destructive changes.
- Do not make broad refactors, architectural rewrites, API changes, or data model changes unless explicitly requested.
- Prefer minimal, reversible changes.
- Keep git history and existing content intact unless the task explicitly requires a restructure.

## 3. Architecture Rules
- Keep KCM aligned with its knowledge-first, columnar-native, deterministic, provenance-aware, temporal, and version-aware model.
- Do not introduce patterns that contradict the whitepaper.
- Keep changes bounded to the relevant subsystem.

## 4. Bounded Subsystem Rule
- Work within the relevant subsystem and avoid unrelated changes.
- Do not modify other subsystems without clear necessity and explicit scope.
- Respect subsystem boundaries and interfaces.

## 5. Ownership Rule
- Respect existing ownership and responsibility boundaries in the repository.
- If ownership is unclear, limit the change and request clarification instead of expanding scope.

## 6. Contract Rule
- Preserve interfaces and contracts between subsystems.
- If a contract must change, document the reason and keep the change as narrow as possible.

## 7. Dependency Rule
- Keep dependencies minimal, explicit, and justified.
- Avoid introducing unnecessary coupling.

## 8. Coding Rule
- Favor clarity, consistency, and maintainability over cleverness.
- Keep implementation aligned with existing conventions.
- Avoid speculative abstractions.

## 9. Testing Rule
- Validate changes with the most relevant checks available.
- Add or update tests when behavior is changed.
- Do not claim completion without verification.

## 10. Documentation Rule
- Document meaningful changes clearly and concisely.
- Keep documentation consistent with the repository’s current foundation.

## 11. Change and Validation Rule
- Before claiming completion, inspect the affected files, verify the repository structure, and confirm that the whitepaper remains unchanged.
- Summarize what changed, why it changed, and what validation was performed.
