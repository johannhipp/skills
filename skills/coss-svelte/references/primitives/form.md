# Form

A styled native form wrapper; validation and submission behavior remain application-owned.

## Status and source

- Status: stable
- Foundation: native
- Category: Forms & Validation
- Local docs route: `/docs/components/form.md` when the coss-svelte docs app is running
- Registry artifact: `apps/registry/static/r/form.json`
- Upstream COSS design reference: <https://coss.com/ui/docs/components/form.md>

## Public imports

```ts
import { Form } from "coss-svelte";
```

## Canonical Svelte pattern

```svelte
<script lang="ts">
	import { Button, Field, Form, Input } from "coss-svelte";

	let email = $state("");
	let submitted = $state(false);
	let invalid = $derived(submitted && !email.includes("@"));
</script>

<Form onsubmit={(event) => { event.preventDefault(); submitted = true; }}>
	<Field label="Email" error={invalid ? "Enter a valid email." : ""} {invalid} required>
		<Input bind:value={email} name="email" type="email" />
	</Field>
	<Button type="submit">Continue</Button>
</Form>
```

## Key contracts

- Form is a styled native `<form>` wrapper; it does not provide schema parsing or a validation library. Handle `onsubmit` and field errors explicitly.

## Anatomy

- `Form`

## Common pitfalls

- Do not copy React/JSX, Base UI, Radix, shadcn, `asChild`, `render`, `className`, or `onClick` patterns into Svelte.
- Do not invent parts or bindings absent from the package declarations.
- Do not treat the upstream particle count as installable Svelte particle manifests.

## Pattern sources

- Search [the upstream pattern index](../particles.md#form) for 2 COSS particle descriptions, then port intent rather than TSX.
- Inspect the package declaration and component source when a prop or snippet contract is not shown here.
