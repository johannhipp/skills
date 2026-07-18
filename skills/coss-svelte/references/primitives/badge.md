# Badge

A small status indicator or label component.

## Status and source

- Status: stable
- Foundation: native
- Category: Content & Display
- Local docs route: `/docs/components/badge.md` when the coss-svelte docs app is running
- Registry artifact: `apps/registry/static/r/badge.json`
- Upstream COSS design reference: <https://coss.com/ui/docs/components/badge.md>

## Public imports

```ts
import { Badge } from "coss-svelte";
```

## Canonical Svelte pattern

```svelte
<script lang="ts">
	import { Badge } from "coss-svelte";
</script>

<Badge>Badge</Badge>
```

## Key contracts

- Use semantic variants for status; do not use a badge as an interactive control unless the actual exported element supports that behavior.

## Anatomy

- `Badge`

## Common pitfalls

- Do not copy React/JSX, Base UI, Radix, shadcn, `asChild`, `render`, `className`, or `onClick` patterns into Svelte.
- Do not invent parts or bindings absent from the package declarations.
- Do not treat the upstream particle count as installable Svelte particle manifests.

## Pattern sources

- Search [the upstream pattern index](../particles.md#badge) for 20 COSS particle descriptions, then port intent rather than TSX.
- Inspect the package declaration and component source when a prop or snippet contract is not shown here.
