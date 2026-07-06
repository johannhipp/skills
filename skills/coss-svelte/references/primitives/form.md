# Form

A complete form implementation with validation and submission handling.

## Status

- Status: Stable
- Foundation: native
- Category: Forms & Validation
- Particles in source inventory: 2
- COSS reference docs: https://coss.com/ui/docs/components/form.md

## Imports

```ts
import { Form } from "coss-svelte";
```

## Minimal Svelte Pattern

```svelte
<script lang="ts">
	import { Button, Field, FieldError, FieldLabel, Form, Input } from "coss-svelte";
</script>

<Form>
	<Field>
		<FieldLabel>Email</FieldLabel>
		<Input type="email" placeholder="team@example.com" />
		<FieldError>Use a work email address.</FieldError>
	</Field>
	<Button type="submit">Submit</Button>
</Form>
```

## Anatomy

- `Form`

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
