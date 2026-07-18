# Spinner

An indicator that can be used to show a loading state.

## Status and source

- Status: stable
- Foundation: native
- Category: Feedback & Status
- Local docs route: `/docs/components/spinner.md` when the coss-svelte docs app is running
- Registry artifact: `apps/registry/static/r/spinner.json`
- Upstream COSS design reference: <https://coss.com/ui/docs/components/spinner.md>

## Public imports

```ts
import { Spinner } from "coss-svelte";
```

## Canonical Svelte pattern

```svelte
<script lang="ts">
	import { Spinner } from "coss-svelte";
</script>

<Spinner label="Loading projects" />
```

## Key contracts

- Use the `label` prop to give the status an accessible name; avoid adding a second competing live region.

## Anatomy

- `Spinner`

## Common pitfalls

- Do not copy React/JSX, Base UI, Radix, shadcn, `asChild`, `render`, `className`, or `onClick` patterns into Svelte.
- Do not invent parts or bindings absent from the package declarations.
- Do not treat the upstream particle count as installable Svelte particle manifests.

## Pattern sources

- Search [the upstream pattern index](../particles.md#spinner) for 1 COSS particle descriptions, then port intent rather than TSX.
- Inspect the package declaration and component source when a prop or snippet contract is not shown here.
