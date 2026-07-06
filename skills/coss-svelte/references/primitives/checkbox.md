# Checkbox

A binary toggle input for selecting one or multiple options.

## Status

- Status: Stable
- Foundation: bits
- Category: Toggle & Choice
- Particles in source inventory: 5
- COSS reference docs: https://coss.com/ui/docs/components/checkbox.md

## Imports

```ts
import { Checkbox } from "coss-svelte";
```

## Minimal Svelte Pattern

```svelte
<script lang="ts">
	import { Checkbox } from "coss-svelte";
</script>

<Checkbox>Checkbox</Checkbox>
```

## Anatomy

- `Checkbox`

## Composition Rules

- Use the exported coss-svelte parts listed above.
- Preserve Svelte syntax and accessibility semantics.
- Prefer documented local examples before adapting upstream COSS React snippets.
- This primitive is either single-export or native-presentational in the current surface.

## Common Pitfalls

- Importing React COSS, Radix, shadcn, or Base UI APIs instead of `coss-svelte`.
- Copying JSX, hooks, `className`, `asChild`, or `render` patterns into Svelte.
- Ignoring the component status when using experimental or deferred primitives.
- Replacing accessible exported parts with anonymous divs that lose labels, roles, or focus behavior.
