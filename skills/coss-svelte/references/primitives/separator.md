# Separator

A visual divider for separating content sections.

## Status and source

- Status: stable
- Foundation: bits
- Category: Content & Display
- Local docs route: `/docs/components/separator.md` when the coss-svelte docs app is running
- Registry artifact: `apps/registry/static/r/separator.json`
- Upstream COSS design reference: <https://coss.com/ui/docs/components/separator.md>

## Public imports

```ts
import { Separator } from "coss-svelte";
```

## Canonical Svelte pattern

```svelte
<script lang="ts">
	import { Separator } from "coss-svelte";
</script>

<div class="w-full max-w-sm">
	<p class="mb-3">Above</p>
	<Separator />
	<p class="mt-3">Below</p>
</div>
```

## Key contracts

- Keep decorative separators decorative; use `orientation` and semantic content boundaries rather than adding empty divider markup everywhere.

## Anatomy

- `Separator`

## Common pitfalls

- Do not copy React/JSX, Base UI, Radix, shadcn, `asChild`, `render`, `className`, or `onClick` patterns into Svelte.
- Do not invent parts or bindings absent from the package declarations.
- Do not treat the upstream particle count as installable Svelte particle manifests.

## Pattern sources

- Search [the upstream pattern index](../particles.md#separator) for 1 COSS particle descriptions, then port intent rather than TSX.
- Inspect the package declaration and component source when a prop or snippet contract is not shown here.
