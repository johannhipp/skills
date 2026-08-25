# Tooltip

A small overlay that provides contextual information on hover or focus.

## Status and source

- Status: stable
- Foundation: bits
- Category: Overlays & Popups
- Local docs route: `/docs/components/tooltip.md` when the coss-svelte docs app is running
- Registry artifact: `apps/registry/static/r/tooltip.json`
- Upstream COSS design reference: <https://coss.com/ui/docs/components/tooltip.md>

## Avoid when

- Do not put required instructions or interactive controls in a tooltip.

## Public imports

```ts
import {
	Tooltip,
	TooltipPopup,
	TooltipProvider,
	TooltipTrigger,
} from "coss-svelte";
```

## Canonical Svelte pattern

```svelte
<script lang="ts">
	import { Tooltip, TooltipPopup, TooltipTrigger } from "coss-svelte";
</script>

<Tooltip>
	<TooltipTrigger>Hover me</TooltipTrigger>
	<TooltipPopup>Helpful hint</TooltipPopup>
</Tooltip>
```

## Key contracts

- Tooltip establishes the Bits UI provider required by both convenience and custom modes. Keep tooltip content brief and non-interactive; custom composition requires TooltipTrigger + TooltipPopup. `TooltipProvider` remains exported for direct provider composition, but wrapping each Tooltip in another provider is unnecessary.

## Anatomy

- `Tooltip`
- `TooltipPopup`
- `TooltipProvider`
- `TooltipTrigger`

## Common pitfalls

- Do not copy React/JSX, Base UI, Radix, shadcn, `asChild`, `render`, `className`, or `onClick` patterns into Svelte.
- Do not invent parts or bindings absent from the package declarations.
- Do not treat the upstream particle count as installable Svelte particle manifests.

## Pattern sources

- Search [the upstream pattern index](../particles.md#tooltip) for 4 COSS particle descriptions, then port intent rather than TSX.
- Inspect the package declaration and component source when a prop or snippet contract is not shown here.
