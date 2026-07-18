# Number Field

A specialized input for numeric values with increment/decrement controls.

> Deferred: this is not an importable component in the current package.

## Status and source

- Status: deferred
- Foundation: custom
- Category: Selection & Input
- Local docs route: `/docs/components/number-field.md` when the coss-svelte docs app is running
- Registry artifact: `apps/registry/static/r/number-field.json`
- Upstream COSS design reference: <https://coss.com/ui/docs/components/number-field.md>

## Public imports

```ts
// No public import exists in the current package.
```

## Current implementation

Do not import or generate this component as available. Use the fallback described below and re-check package exports before changing that guidance.

## Key contracts

- Deferred: `NumberField` is metadata only and is not exported. Use Input with `type="number"` or a project-local control until the status changes.

## Anatomy

- No exported anatomy while deferred.

## Common pitfalls

- Do not copy React/JSX, Base UI, Radix, shadcn, `asChild`, `render`, `className`, or `onClick` patterns into Svelte.
- Do not invent parts or bindings absent from the package declarations.
- Do not treat the upstream particle count as installable Svelte particle manifests.

## Pattern sources

- Search [the upstream pattern index](../particles.md#number-field) for 11 COSS particle descriptions, then port intent rather than TSX.
- Inspect the package declaration and component source when a prop or snippet contract is not shown here.
