# Toast

A temporary notification message that appears and disappears automatically.

## Status

- Status: Experimental
- Foundation: custom
- Category: Feedback & Status
- Particles in source inventory: 13
- COSS reference docs: https://coss.com/ui/docs/components/toast.md

This component is experimental in coss-svelte. Mention the status and avoid promising full upstream parity.

## Imports

```ts
import { Toast } from "coss-svelte";
```

## Minimal Svelte Pattern

```svelte
<script lang="ts">
	import { Toast } from "coss-svelte";
</script>

<Toast>Toast</Toast>
```

## Anatomy

- `Toast`

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
