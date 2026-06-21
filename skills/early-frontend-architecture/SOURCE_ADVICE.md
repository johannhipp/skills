# Source Advice And Rationale

Use this reference when a user wants the opinionated reasoning behind the `early-frontend-architecture` skill or when a recommendation needs more context. Keep the main skill proportional: this reference is intentionally stronger than the default operating guidance.

## Original Principles, Normalized

- Make server code generate an OpenAPI spec or equivalent contract, then generate the client-side code. Handwritten backend response types should be treated as a smell.
- Decide how the client talks to the backend. For REST or GraphQL-style API calls, prefer TanStack Query unless the project already has a strong established alternative.
- If the app needs Linear-style sync or offline mode, think hard and architect it from day one. Retrofitting this later is tedious.
- Prefer modern routing with data loaders and typed route/search handling. Consider React Router framework mode or TanStack Router rather than plain component-only routing.
- If the app stores significant state in query params, make that state typed and first-class. Consider `nuqs` or the router's typed search-param system.
- Most apps only need one server-state management story. Add client-state tools only when there are concrete non-server-state needs. Zustand is reasonable for simple shared state; XState is appropriate for complex interaction models.
- For very interactive apps with many UI modes, media, realtime events, and elements entering or leaving view, use state machines to avoid tangled `useEffect` logic.
- React Compiler changes the default posture around `useMemo` and `useCallback`. Do not cargo-cult memoization.
- Tailwind is fast, but large apps still need an agent-first design system or component library to maintain consistency.
- Do not be afraid to extend routing conventions for product needs such as drawers, side panels, and inspectors. Navigable UI surfaces should have a first-class pattern.
- Prefer Suspense and ErrorBoundary patterns over repetitive component-local `isPending` and `isError` branching when the stack supports it.
- For AI-related products, define a blessed WebSocket/SSE/streaming path early.
- If building a pure SPA, question whether Next.js is the right choice. It is valuable when SSR, RSC, SEO, or full-stack conventions matter; otherwise it can add unnecessary complexity.
- Prefer Cloudflare or Vercel for deployment unless the project has constraints that make another platform clearly better.
- Once the product has demand, the engineering job becomes building the factory that efficiently builds the product. Early conventions should make future agents and humans faster.

## Interpretation Guidance

Apply the advice as architectural pressure, not dogma. The skill should steer young projects toward generated contracts, coherent server-state, typed routing/URL state, clear async boundaries, reusable UI primitives, and explicit realtime/sync decisions.

Do not force every project into every recommendation. Standard CRUD apps should stay boring. Interactive, realtime, or offline-heavy apps need earlier architecture investment because those decisions are expensive to retrofit.
