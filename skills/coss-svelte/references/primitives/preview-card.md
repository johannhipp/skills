# Preview Card

A rich preview component for displaying linked content.

## Status and source

- Status: stable
- Foundation: bits
- Category: Overlays & Popups
- Local docs route: `/docs/components/preview-card.md` when the coss-svelte docs app is running
- Registry artifact: `apps/registry/static/r/preview-card.json`
- Upstream COSS design reference: <https://coss.com/ui/docs/components/preview-card.md>

## Public imports

```ts
import { PreviewCard, PreviewCardPopup, PreviewCardTrigger } from "coss-svelte";
```

## Canonical Svelte pattern

```svelte
<script lang="ts">
	import { PreviewCard } from "coss-svelte";
</script>

<PreviewCard
	href="/docs/components/button"
	label="Button docs"
	title="Button"
	description="Actions, links, variants, sizes, and loading states."
/>
```

## Key contracts

- Use for link previews, with a real href and concise content. Custom children require both PreviewCardTrigger and PreviewCardPopup.

## Anatomy

- `PreviewCard`
- `PreviewCardPopup`
- `PreviewCardTrigger`

## Common pitfalls

- Do not copy React/JSX, Base UI, Radix, shadcn, `asChild`, `render`, `className`, or `onClick` patterns into Svelte.
- Do not invent parts or bindings absent from the package declarations.
- Do not treat the upstream particle count as installable Svelte particle manifests.

## Pattern sources

- Search [the upstream pattern index](../particles.md#preview-card) for 1 COSS particle descriptions, then port intent rather than TSX.
- Inspect the package declaration and component source when a prop or snippet contract is not shown here.
