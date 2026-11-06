# ADR-0002: Technology stack

- Status: Proposed
- Date: 2026-11-06

## Context

Zeven analyses a player's recent games and produces a personalised
improvement report. It must be practical to run locally, simple to self-host,
and able to grow into a public deployment later. The maintainer already
knows Python. Engine analysis is CPU-heavy, so architecture decisions must not
make future scaling unnecessarily difficult. We avoid infrastructure the
initial product does not need.

## Decision

| Layer | Choice |
|---|---|
| Core language | Python 3.12+ |
| Project and dependency management | uv (workspace with lockfile) |
| Chess logic, PGN, UCI | python-chess |
| Engine | Stockfish via UCI subprocess, behind an `Engine` interface |
| API | FastAPI with Pydantic v2 |
| HTTP client | httpx (async) |
| Jobs (initial) | In-process asyncio with a subprocess engine pool; job state in SQLite |
| Database (initial) | SQLite via SQLAlchemy 2.0 and Alembic |
| Frontend | Vite, React, TypeScript (single-page app) |
| Board component | chessground, with chess.js for client-side move logic |
| Progress updates | Server-Sent Events |
| Packaging for self-hosting | Docker and docker compose |
| Lint, format | Ruff |
| Type checking | pyright |
| Tests | pytest with coverage |

Build order: a pure core library and CLI first, then the API, then the web UI.
The core library has no web, database or network dependencies beyond injected
interfaces.

## Alternatives considered

- **Next.js instead of Vite and React:** adds server-side rendering we do not
  need. Revisit only if SEO landing pages become important.
- **Redis with a task queue (ARQ or Celery) from the start:** unnecessary for a
  single-user install. Introduce when multiple workers or public traffic require it.
- **PostgreSQL from the start:** SQLite is enough for caching and jobs.
  Move to PostgreSQL when optional accounts and concurrency arrive.
- **mypy instead of pyright:** both are viable. Pyright is faster and stricter by
  default. Either can be swapped later.
- **Poetry instead of uv:** mature, but uv is faster and handles workspaces well.
- **Stockfish in the browser (WebAssembly):** the only route to near-zero server
  cost at scale, but slower and constrained on weak devices. Investigate in
  the public-launch phase. The `Engine` interface keeps this open.
- **Machine learning for insight generation:** rejected. Rule-based, statistical
  insights are explainable and cannot invent facts.

## Consequences

- Python 3.12+ is required, as is a local Stockfish binary.
- python-chess and chessground are GPL-3.0, which is compatible with the
  AGPL-3.0 choice in ADR-0001.
- Evaluations are cached by position, engine version and settings, so results
  are reproducible and reusable across reports.
- Swapping the engine, database or job runner later is intended to be a
  contained change, because each sits behind an interface.
- Versions and licences of every dependency must be verified before this ADR is
  accepted, and checked continuously in CI.