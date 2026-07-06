# Input Group

A flexible component for grouping inputs with addons, buttons, and other elements.

## Status

- Status: Stable
- Foundation: compound
- Category: Selection & Input
- Particles in source inventory: 28
- COSS reference docs: https://coss.com/ui/docs/components/input-group.md

## Imports

```ts
import { InputGroup, InputGroupAddon, InputGroupInput, InputGroupText, InputGroupTextarea } from "coss-svelte";
```

## Minimal Svelte Pattern

```svelte
<script lang="ts">
	import { InputGroup, InputGroupAddon, InputGroupInput, InputGroupText, InputGroupTextarea } from "coss-svelte";
</script>

<InputGroup>
	<InputGroupAddon>Input Group</InputGroupAddon>
</InputGroup>
```

## Anatomy

- `InputGroup`
- `InputGroupAddon`
- `InputGroupInput`
- `InputGroupText`
- `InputGroupTextarea`

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
