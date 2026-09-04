# Paperclip — Product Overview

**Project:** Paperclip Control Plane for AI-Agent Companies
**Status:** V1 Development
**Last Updated:** 2026-09-04

## What is Paperclip?

Paperclip is a control plane for AI-agent companies. It provides:
- Multi-agent orchestration
- Task assignment and tracking
- Governance and approvals
- Budget management
- Activity logging

## Architecture

- `server/` — Express REST API and orchestration services
- `ui/` — React + Vite board UI
- `packages/db/` — Drizzle schema, migrations, DB clients
- `packages/shared/` — shared types, constants, validators
- `packages/adapters/` — agent adapter implementations
- `packages/plugins/` — plugin system
- `cli/` — paperclipai CLI

## Key Features (V1)
- Single-assignee task model
- Atomic issue checkout semantics
- Approval gates for governed actions
- Budget hard-stop auto-pause behavior
- Activity logging for mutating actions

## Recent Updates

- **2026-09-04** — Team Obsidian vault initialized at `/root/.hermes/shared/obsidian-vault/` for shared knowledge management. Each agent has a profile folder under `Agents/`.
- **2026-09-04** — All agent profiles synced to vault (Sue, Elon, Ava, Ira, Zoe done; remaining agents in progress).
- **2026-09-04** — Paperclip V1 development underway with multi-agent orchestration.

## Related
- [[OnboardAI]] — OnboardAI feature
- [[Infrastructure]] — Infrastructure docs
