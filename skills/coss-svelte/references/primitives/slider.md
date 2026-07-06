# Slider

A draggable control for selecting values from a continuous range.

## Status

- Status: Stable
- Foundation: bits
- Category: Selection & Input
- Particles in source inventory: 23
- COSS reference docs: https://coss.com/ui/docs/components/slider.md

## Imports

```ts
import { Slider, SliderRange, SliderThumb, SliderThumbLabel, SliderTick, SliderTickLabel } from "coss-svelte";
```

## Minimal Svelte Pattern

```svelte
<script lang="ts">
	import { Slider, SliderRange, SliderThumb, SliderThumbLabel, SliderTick, SliderTickLabel } from "coss-svelte";
</script>

<Slider>
	<SliderRange>Slider</SliderRange>
</Slider>
```

## Anatomy

- `Slider`
- `SliderRange`
- `SliderThumb`
- `SliderThumbLabel`
- `SliderTick`
- `SliderTickLabel`

## Composition Rules

- Use the exported coss-svelte parts listed above.
- Preserve Svelte syntax and accessibility semantics.
- Prefer documented local examples before adapting upstream COSS React snippets.
- Keep child parts inside the root component unless the docs for this primitive state otherwise.

## Common Pitfalls

- Importing React COSS, Radix, shadcn, or Base UI APIs instead of `coss-svelte`.
- Copying JSX, hooks, `className`, `asChild`, or `render` patterns into Svelte.
- Ignoring the component status when using experimental or deferred primitives.
- Replacing accessible exported parts with anonymous divs that lose labels, roles, or focus behavior.
