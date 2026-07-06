# Fieldset

A group of related form fields with a common label.

## Status

- Status: Stable
- Foundation: native
- Category: Forms & Validation
- Particles in source inventory: 1
- COSS reference docs: https://coss.com/ui/docs/components/fieldset.md

## Imports

```ts
import { Fieldset, FieldsetLegend } from "coss-svelte";
```

## Minimal Svelte Pattern

```svelte
<script lang="ts">
	import { Fieldset, FieldsetLegend } from "coss-svelte";
</script>

<Fieldset>
	<FieldsetLegend>Fieldset</FieldsetLegend>
</Fieldset>
```

## Anatomy

- `Fieldset`
- `FieldsetLegend`

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
