# Avatar

A visual representation of a user or entity.

## Status and source

- Status: stable
- Foundation: bits
- Category: Content & Display
- Local docs route: `/docs/components/avatar.md` when the coss-svelte docs app is running
- Registry artifact: `apps/registry/static/r/avatar.json`
- Upstream COSS design reference: <https://coss.com/ui/docs/components/avatar.md>

## Public imports

```ts
import { Avatar, AvatarFallback, AvatarImage } from "coss-svelte";
```

## Canonical Svelte pattern

```svelte
<script lang="ts">
	import { Avatar, AvatarFallback } from "coss-svelte";
</script>

<Avatar aria-label="coss-svelte">
	<AvatarFallback>coss</AvatarFallback>
</Avatar>
```

## Key contracts

- Provide useful `alt` text for meaningful images and a short fallback; custom children replace the convenience image/fallback layout.

## Anatomy

- `Avatar`
- `AvatarFallback`
- `AvatarImage`

## Common pitfalls

- Do not copy React/JSX, Base UI, Radix, shadcn, `asChild`, `render`, `className`, or `onClick` patterns into Svelte.
- Do not invent parts or bindings absent from the package declarations.
- Do not treat the upstream particle count as installable Svelte particle manifests.

## Pattern sources

- Search [the upstream pattern index](../particles.md#avatar) for 14 COSS particle descriptions, then port intent rather than TSX.
- Inspect the package declaration and component source when a prop or snippet contract is not shown here.
