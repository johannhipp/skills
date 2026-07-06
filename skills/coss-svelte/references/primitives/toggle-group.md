# Toggle Group

A group of toggle buttons where one or multiple can be selected.

## Status

- Status: Stable
- Foundation: bits
- Category: Toggle & Choice
- Particles in source inventory: 9
- COSS reference docs: https://coss.com/ui/docs/components/toggle-group.md

## Imports

```ts
import { ToggleGroup, ToggleGroupItem } from "coss-svelte";
```

## Minimal Svelte Pattern

```svelte
<script lang="ts">
	import { ToggleGroup, ToggleGroupItem } from "coss-svelte";
</script>

<ToggleGroup>
	<ToggleGroupItem>Toggle Group</ToggleGroupItem>
</ToggleGroup>
```

## Anatomy

- `ToggleGroup`
- `ToggleGroupItem`

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
