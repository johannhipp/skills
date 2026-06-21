---
name: early-frontend-architecture
description: Guide early-stage web app frontend architecture before the codebase becomes large. Use when starting a new React or web app, auditing a young product, choosing frontend data/routing/state/design-system patterns, or setting day-one conventions for API clients, server-state, routing, URL state, realtime, Suspense/ErrorBoundary, deployment, and agent-friendly UI architecture.
---

# Early Frontend Architecture

## Goal

Set day-one frontend architecture decisions for young web apps so the project can scale without expensive rewrites. Keep recommendations proportional to the product's actual interaction model.

If the user asks for the original opinionated rationale, or if a recommendation needs stronger justification, read [SOURCE_ADVICE.md](SOURCE_ADVICE.md).

## First Classify The App

Before recommending libraries or conventions, classify the app:

- **Standard CRUD/SaaS**: forms, tables, dashboards, auth, settings, admin workflows.
- **Interactive workspace**: canvases, editors, inspectors, media, command palettes, nested panels.
- **Offline-first/sync-heavy**: local-first behavior, optimistic replication, collaboration, Linear-style sync.
- **AI/realtime-heavy**: streaming responses, job progress, notifications, live data, collaborative updates.
- **Content/SEO-heavy**: public pages, search traffic, SSR/SSG, marketing or docs surfaces.
- **Pure authenticated SPA**: app is mostly behind login and does not benefit much from SSR.

Name the app type explicitly. If multiple types apply, identify the primary type and the decisions that become foundational because of the secondary type.

## Required Output

Return a concise recommendation with these sections:

- **App type**
- **Recommended stack**
- **Adopt now**
- **Decide early if relevant**
- **Defer**
- **High-risk missing decisions**
- **First implementation steps**

When working inside a codebase, ground the recommendation in actual files, package choices, and existing patterns. Do not rewrite a working architecture just to match this skill; prefer incremental conventions that fit the project.

## Day-One Defaults

### API Contracts

Prefer backend-generated OpenAPI or an equivalent schema contract. Generate frontend clients and types from the server contract. Do not hand-maintain backend response types in the frontend.

If the backend cannot emit a schema yet, recommend adding that before the frontend grows. If the stack uses tRPC, GraphQL codegen, gRPC, Convex, or another typed contract system, treat that as satisfying the same goal.

### Server State

For REST/GraphQL-style APIs, prefer TanStack Query or the project's established server-state library. Use one blessed server-state layer for fetching, caching, invalidation, retries, and mutation state.

Avoid spreading fetch calls, ad hoc loading flags, cache updates, and retry behavior across components.

### Routing And Data Loading

Prefer a router with typed params/search where possible and a clear data-loading story. For React SPAs, consider TanStack Router or React Router framework mode when routing affects layouts, auth, data loading, drawers, or nested workflows.

Use route loaders or route-level data conventions instead of leaving every screen to invent its own data bootstrapping.

### URL State

If filters, table state, search, tabs, pagination, workspace state, or shareable views live in query params, make URL state typed and first-class.

Consider `nuqs`, TanStack Router search schemas, or the project's equivalent typed search-param system.

### Client State

Default to no global client-state library beyond server state.

Use Zustand for small shared client state. Use XState or state-machine modeling for highly interactive apps with complex UI modes, media, realtime updates, or many transitions.

### Sync And Offline

If the app needs local-first behavior, collaborative state, offline mode, or Linear-style sync, stop and design the sync model before building much UI.

Require an explicit strategy for identity, conflict handling, optimistic updates, persistence, server reconciliation, invalidation, and backfill. Treat this as foundational architecture, not a late feature.

### Suspense And Errors

Prefer Suspense and ErrorBoundary patterns for loading and failure surfaces where the framework and data layer support them.

Avoid scattering `isPending`, `isError`, and local fallback branching throughout feature components. Define where boundaries live: route, layout, panel, or widget.

### Realtime

For AI products, streaming UX, multiplayer/collaboration, job progress, notifications, or live updates, define a blessed WebSocket/SSE pattern early.

Specify connection ownership, auth, reconnect behavior, event typing, message validation, cancellation, and cache integration.

### React Compiler

Assume modern React compiler-aware patterns where supported by the project. Do not introduce broad `useMemo`/`useCallback` usage by habit.

Optimize only when profiling, framework constraints, referential identity contracts, or compiler limitations justify it.

### Styling And Design System

Tailwind is acceptable, but require design tokens, reusable components, and agent-friendly UI primitives before the app grows.

Avoid one-off utility-heavy product surfaces without shared components. Establish a small component library with variants, states, accessibility behavior, and examples agents can copy.

### Route-Driven UI Surfaces

If the app uses drawers, side panels, modals, or inspector panes as navigable surfaces, model them in routing or a routing-adjacent convention.

The desired end state is that an agent can express "this route renders as a drawer" through a clear local pattern.

### SPA vs Next.js

If the product is a pure authenticated SPA with little need for SSR, SEO, RSC, or server-rendered app routes, question whether Next.js is necessary.

Use Next.js when SSR, RSC, SEO, file-based full-stack conventions, image optimization, or deployment ergonomics justify it.

### Deployment

Prefer boring, well-supported deployment targets such as Vercel or Cloudflare unless project constraints say otherwise.

Check runtime needs before choosing: Node APIs, edge compatibility, background jobs, WebSockets, image optimization, cron, regions, preview deploys, secrets, and observability.

## Decision Tiers

### Always Do Early

- Generate API clients/types from server contracts.
- Pick one server-state pattern.
- Pick one routing/data-loading pattern.
- Make URL state typed if used heavily.
- Define loading/error conventions.
- Establish design-system primitives.
- Decide SPA vs SSR deliberately.

### Decide Early If Relevant

- Offline/sync/local-first architecture.
- WebSocket/SSE architecture.
- State machines for complex interaction.
- Route-driven drawers/modals.
- AI streaming patterns.

### Defer Until Needed

- Heavy global client state.
- Complex design-system governance.
- Custom routing abstractions.
- Premature memoization/performance work.
- Offline support for apps that do not need it.

## Codebase Audit Procedure

When auditing an existing young project:

1. Inspect package manager files, routing setup, API clients, state libraries, styling setup, and deployment config.
2. Identify where the app already has a coherent convention and where decisions are fragmented.
3. Recommend the smallest set of architecture moves that prevent future rewrites.
4. Separate must-do-now decisions from optional improvements.
5. If making edits, add or update conventions in the most discoverable local place: app scaffolding, shared clients, route utilities, component primitives, or project docs.

## Recommendation Template

```markdown
**App Type**
[Primary type and why.]

**Recommended Stack**
[Concrete libraries/conventions, respecting the existing project.]

**Adopt Now**
[High-leverage decisions to implement before growth.]

**Decide Early If Relevant**
[Only include items relevant to this product.]

**Defer**
[Things that would be premature.]

**High-Risk Missing Decisions**
[Architecture gaps that become expensive later.]

**First Implementation Steps**
[Small, ordered steps. Include file paths when inside a repo.]
```
