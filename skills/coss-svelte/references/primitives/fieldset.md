# Fieldset

A group of related form fields with a common label.

## Status and source

- Status: stable
- Foundation: native
- Category: Forms & Validation
- Local docs route: `/docs/components/fieldset.md` when the coss-svelte docs app is running
- Registry artifact: `apps/registry/static/r/fieldset.json`
- Upstream COSS design reference: <https://coss.com/ui/docs/components/fieldset.md>

## Public imports

```ts
import { Fieldset, FieldsetLegend } from "coss-svelte";
```

## Canonical Svelte pattern

```svelte
<script lang="ts">
	import { Field, FieldDescription, FieldLabel, Fieldset, FieldsetLegend, Input } from "coss-svelte";
</script>

<Fieldset class="w-full max-w-64">
	<FieldsetLegend>Billing Details</FieldsetLegend>
	<Field>
		<FieldLabel>Company</FieldLabel>
		<Input placeholder="Enter company name" type="text" />
		<FieldDescription>The name that will appear on invoices.</FieldDescription>
	</Field>
	<Field>
		<FieldLabel>Tax ID</FieldLabel>
		<Input placeholder="Enter tax identification number" type="text" />
		<FieldDescription>Your business tax identification number.</FieldDescription>
	</Field>
</Fieldset>
```

## Key contracts

- Use native fieldset/legend semantics for related controls. Use the `legend` convenience prop or FieldsetLegend, not duplicate legends.

## Anatomy

- `Fieldset`
- `FieldsetLegend`

## Common pitfalls

- Do not copy React/JSX, Base UI, Radix, shadcn, `asChild`, `render`, `className`, or `onClick` patterns into Svelte.
- Do not invent parts or bindings absent from the package declarations.
- Do not treat the upstream particle count as installable Svelte particle manifests.

## Pattern sources

- Search [the upstream pattern index](../particles.md#fieldset) for 1 COSS particle descriptions, then port intent rather than TSX.
- Inspect the package declaration and component source when a prop or snippet contract is not shown here.
