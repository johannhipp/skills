# Input

A native input element.

## Status

- Status: Stable
- Foundation: native
- Category: Selection & Input
- Particles in source inventory: 19
- COSS reference docs: https://coss.com/ui/docs/components/input.md

## Imports

```ts
import { Input } from "coss-svelte";
```

## Minimal Svelte Pattern

```svelte
<script lang="ts">
	import { Input } from "coss-svelte";
</script>

<Input>Input</Input>
```

## Anatomy

- `Input`

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
