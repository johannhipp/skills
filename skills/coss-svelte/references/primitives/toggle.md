# Toggle

A button that switches between two states.

## Status

- Status: Stable
- Foundation: bits
- Category: Toggle & Choice
- Particles in source inventory: 8
- COSS reference docs: https://coss.com/ui/docs/components/toggle.md

## Imports

```ts
import { Toggle } from "coss-svelte";
```

## Minimal Svelte Pattern

```svelte
<script lang="ts">
	import { Toggle } from "coss-svelte";
</script>

<Toggle>Toggle</Toggle>
```

## Anatomy

- `Toggle`

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
