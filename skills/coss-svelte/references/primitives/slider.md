# Slider

A draggable control for selecting values from a continuous range.

## Status and source

- Status: stable
- Foundation: bits
- Category: Selection & Input
- Local docs route: `/docs/components/slider.md` when the coss-svelte docs app is running
- Registry artifact: `apps/registry/static/r/slider.json`
- Upstream COSS design reference: <https://coss.com/ui/docs/components/slider.md>

## Public imports

```ts
import {
	Slider,
	SliderRange,
	SliderThumb,
	SliderThumbLabel,
	SliderTick,
	SliderTickLabel,
} from "coss-svelte";
```

## Canonical Svelte pattern

```svelte
<script lang="ts">
	import { Slider } from "coss-svelte";

	let volume = $state(40);
</script>

<Slider aria-label="Volume" bind:value={volume} min={0} max={100} />
```

## Key contracts

- Always provide an accessible label. Single mode uses a number; multiple/range mode uses a number array.
- The root renders range/ticks/thumbs automatically; custom children receive `thumbItems` and `tickItems` and must render indexed parts.
- Bindable contract: `bind:value`; optional `onValueChange`.

## Anatomy

- `Slider`
- `SliderRange`
- `SliderThumb`
- `SliderThumbLabel`
- `SliderTick`
- `SliderTickLabel`

## Common pitfalls

- Do not copy React/JSX, Base UI, Radix, shadcn, `asChild`, `render`, `className`, or `onClick` patterns into Svelte.
- Do not invent parts or bindings absent from the package declarations.
- Do not treat the upstream particle count as installable Svelte particle manifests.

## Pattern sources

- Search [the upstream pattern index](../particles.md#slider) for 23 COSS particle descriptions, then port intent rather than TSX.
- Inspect the package declaration and component source when a prop or snippet contract is not shown here.
