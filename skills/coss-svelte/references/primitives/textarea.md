# Textarea

A multi-line text input for longer content.

## Status

- Status: Stable
- Foundation: native
- Category: Selection & Input
- Particles in source inventory: 15
- COSS reference docs: https://coss.com/ui/docs/components/textarea.md

## Imports

```ts
import { Textarea } from "coss-svelte";
```

## Minimal Svelte Pattern

```svelte
<script lang="ts">
	import { Textarea } from "coss-svelte";
</script>

<Textarea>Textarea</Textarea>
```

## Anatomy

- `Textarea`

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
