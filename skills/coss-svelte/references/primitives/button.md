# Button

A button or a component that looks like a button.

## Status

- Status: Stable
- Foundation: native
- Category: Actions
- Particles in source inventory: 40
- COSS reference docs: https://coss.com/ui/docs/components/button.md

## Imports

```ts
import { Button } from "coss-svelte";
```

## Minimal Svelte Pattern

```svelte
<script lang="ts">
	import { Button } from "coss-svelte";
</script>

<Button>Save changes</Button>
<Button variant="outline">Cancel</Button>
```

## Anatomy

- `Button`

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
