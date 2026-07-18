# Skeleton

A placeholder for loading content.

## Status and source

- Status: stable
- Foundation: native
- Category: Feedback & Status
- Local docs route: `/docs/components/skeleton.md` when the coss-svelte docs app is running
- Registry artifact: `apps/registry/static/r/skeleton.json`
- Upstream COSS design reference: <https://coss.com/ui/docs/components/skeleton.md>

## Public imports

```ts
import { Skeleton } from "coss-svelte";
```

## Canonical Svelte pattern

```svelte
<script lang="ts">
	import { Skeleton } from "coss-svelte";
</script>

<Skeleton class="h-20 w-72" />
```

## Key contracts

- Treat Skeleton as visual placeholder only; keep loading status and accessible names in surrounding content.

## Anatomy

- `Skeleton`

## Common pitfalls

- Do not copy React/JSX, Base UI, Radix, shadcn, `asChild`, `render`, `className`, or `onClick` patterns into Svelte.
- Do not invent parts or bindings absent from the package declarations.
- Do not treat the upstream particle count as installable Svelte particle manifests.

## Pattern sources

- Search [the upstream pattern index](../particles.md#skeleton) for 2 COSS particle descriptions, then port intent rather than TSX.
- Inspect the package declaration and component source when a prop or snippet contract is not shown here.
