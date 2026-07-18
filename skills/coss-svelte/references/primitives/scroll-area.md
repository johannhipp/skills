# Scroll Area

A container with custom scrollbars for overflow content.

## Status and source

- Status: stable
- Foundation: bits
- Category: Layout & Navigation
- Local docs route: `/docs/components/scroll-area.md` when the coss-svelte docs app is running
- Registry artifact: `apps/registry/static/r/scroll-area.json`
- Upstream COSS design reference: <https://coss.com/ui/docs/components/scroll-area.md>

## Public imports

```ts
import {
	ScrollArea,
	ScrollAreaCorner,
	ScrollAreaScrollbar,
	ScrollAreaThumb,
	ScrollAreaViewport,
} from "coss-svelte";
```

## Canonical Svelte pattern

```svelte
<script lang="ts">
	import { ScrollArea, ScrollAreaCorner, ScrollAreaScrollbar, ScrollAreaThumb, ScrollAreaViewport } from "coss-svelte";

	const tags = Array.from({ length: 50 }, (_, index) => `v1.0.0-alpha.${index}`);
</script>

<ScrollArea class="h-64 w-72 rounded-lg border">
	<ScrollAreaViewport>
		<div class="px-4 py-2">
			<h4 class="mb-2 font-medium text-sm">Tags</h4>
			<div class="flex flex-col gap-1">
				{#each tags as tag}
					<div class="text-sm">{tag}</div>
				{/each}
			</div>
		</div>
	</ScrollAreaViewport>
	<ScrollAreaScrollbar orientation="vertical">
		<ScrollAreaThumb />
	</ScrollAreaScrollbar>
	<ScrollAreaCorner />
</ScrollArea>
```

## Key contracts

- Place content inside ScrollAreaViewport. Add matching ScrollAreaScrollbar/Thumb parts for each direction and Corner when both axes scroll.

## Anatomy

- `ScrollArea`
- `ScrollAreaCorner`
- `ScrollAreaScrollbar`
- `ScrollAreaThumb`
- `ScrollAreaViewport`

## Common pitfalls

- Do not copy React/JSX, Base UI, Radix, shadcn, `asChild`, `render`, `className`, or `onClick` patterns into Svelte.
- Do not invent parts or bindings absent from the package declarations.
- Do not treat the upstream particle count as installable Svelte particle manifests.

## Pattern sources

- Search [the upstream pattern index](../particles.md#scroll-area) for 5 COSS particle descriptions, then port intent rather than TSX.
- Inspect the package declaration and component source when a prop or snippet contract is not shown here.
