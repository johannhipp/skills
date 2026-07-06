# Field

A wrapper component for form inputs with labels and validation.

## Status

- Status: Stable
- Foundation: compound
- Category: Forms & Validation
- Particles in source inventory: 18
- COSS reference docs: https://coss.com/ui/docs/components/field.md

## Imports

```ts
import { Field, FieldDescription, FieldError, FieldLabel, FieldValidity } from "coss-svelte";
```

## Minimal Svelte Pattern

```svelte
<script lang="ts">
	import { Field, FieldDescription, FieldError, FieldLabel, FieldValidity } from "coss-svelte";
</script>

<Field>
	<FieldDescription>Field</FieldDescription>
</Field>
```

## Anatomy

- `Field`
- `FieldDescription`
- `FieldError`
- `FieldLabel`
- `FieldValidity`

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
