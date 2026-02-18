# Architecture Overview

## 1. Goal

Build an offline-first Notes/Tasks app with production-grade structure, testability, and performance.

## 2. Scope

**In scope (MVP):**

- CRUD notes
- Tags
- Search
- Offline-first persistence (SQLite)
- Performance for large lists

**Out of scope (for now):**

- Auth/accounts
- Server sync
- Collaboration

## 3. Non-Functional Requirements

- Offline-first operation
- Reliable persistence (migrations, integrity)
- Fast list rendering (1k–10k items)
- Testable architecture with clear boundaries
- Maintainable feature-based structure

## 4. Architecture Pattern

Layered feature architecture:

- UI (screens/components) → calls Service
- Service (business rules) → calls Repository
- Repository (interface) → calls Storage implementation (SQLite)

UI must not access SQLite directly.

## 5. Folder Structure (planned)

<insert tree>

## 6. Data Model (planned)

<Note, Tag, NoteTag>

## 7. Data Flow & State

- TanStack Query: server-like caching for repository calls
- Zustand: UI state (filters, selected note)
- React Hook Form + Zod: forms + validation

## 8. Error Handling & Observability

- Error boundaries for screens
- Typed domain errors from repository/service
- Logging wrapper

## 9. Testing Strategy

- Unit tests: service layer
- Integration: repository + SQLite
- UI smoke test: create note flow

## 10. Future Extensions

- Sync engine
- Auth
- Attachments
