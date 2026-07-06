# Number Field

A specialized input for numeric values with increment/decrement controls.

## Status

- Status: Deferred
- Foundation: custom
- Category: Selection & Input
- Particles in source inventory: 11
- COSS reference docs: https://coss.com/ui/docs/components/number-field.md

This component is deferred in coss-svelte. Do not implement it as available production API unless the local package has changed.

## Imports

```ts
import { NumberField } from "coss-svelte";
```

## Minimal Svelte Pattern

```svelte
<script lang="ts">
	import { NumberField } from "coss-svelte";
</script>

<NumberField>Number Field</NumberField>
```

## Anatomy

- `NumberField`

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
