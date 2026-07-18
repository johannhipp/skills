# Progress

A visual indicator showing the completion status of a task.

## Status and source

- Status: stable
- Foundation: bits
- Category: Feedback & Status
- Local docs route: `/docs/components/progress.md` when the coss-svelte docs app is running
- Registry artifact: `apps/registry/static/r/progress.json`
- Upstream COSS design reference: <https://coss.com/ui/docs/components/progress.md>

## Public imports

```ts
import { Progress } from "coss-svelte";
```

## Canonical Svelte pattern

```svelte
<script lang="ts">
	import { Progress } from "coss-svelte";
</script>

<Progress value={72} />
```

## Key contracts

- Use a numeric value for determinate progress and `null` for indeterminate state; provide a label when surrounding text does not name it.

## Anatomy

- `Progress`

## Common pitfalls

- Do not copy React/JSX, Base UI, Radix, shadcn, `asChild`, `render`, `className`, or `onClick` patterns into Svelte.
- Do not invent parts or bindings absent from the package declarations.
- Do not treat the upstream particle count as installable Svelte particle manifests.

## Pattern sources

- Search [the upstream pattern index](../particles.md#progress) for 3 COSS particle descriptions, then port intent rather than TSX.
- Inspect the package declaration and component source when a prop or snippet contract is not shown here.
