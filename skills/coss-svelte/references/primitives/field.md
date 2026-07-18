# Field

A wrapper component for form inputs with labels and validation.

## Status and source

- Status: stable
- Foundation: compound
- Category: Forms & Validation
- Local docs route: `/docs/components/field.md` when the coss-svelte docs app is running
- Registry artifact: `apps/registry/static/r/field.json`
- Upstream COSS design reference: <https://coss.com/ui/docs/components/field.md>

## Public imports

```ts
import {
	Field,
	FieldDescription,
	FieldError,
	FieldLabel,
	FieldValidity,
} from "coss-svelte";
```

## Canonical Svelte pattern

```svelte
<script lang="ts">
	import { Field, FieldDescription, FieldLabel, Input } from "coss-svelte";
</script>

<Field class="w-full max-w-64">
	<FieldLabel>Name</FieldLabel>
	<Input placeholder="Enter your name" type="text" />
	<FieldDescription>Visible on your profile</FieldDescription>
</Field>
```

## Key contracts

- Use either convenience `label`/`description`/`error` props or the corresponding child parts, not both.
- Set `invalid`, `required`, and `disabled` on Field so descendant Input/Textarea/InputGroup controls inherit accessible state.

## Anatomy

- `Field`
- `FieldDescription`
- `FieldError`
- `FieldLabel`
- `FieldValidity`

## Common pitfalls

- Do not copy React/JSX, Base UI, Radix, shadcn, `asChild`, `render`, `className`, or `onClick` patterns into Svelte.
- Do not invent parts or bindings absent from the package declarations.
- Do not treat the upstream particle count as installable Svelte particle manifests.

## Pattern sources

- Search [the upstream pattern index](../particles.md#field) for 18 COSS particle descriptions, then port intent rather than TSX.
- Inspect the package declaration and component source when a prop or snippet contract is not shown here.
