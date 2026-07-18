# Select

A common form component for choosing a predefined value in a dropdown menu.

## Status and source

- Status: stable
- Foundation: bits
- Category: Selection & Input
- Local docs route: `/docs/components/select.md` when the coss-svelte docs app is running
- Registry artifact: `apps/registry/static/r/select.json`
- Upstream COSS design reference: <https://coss.com/ui/docs/components/select.md>

## Avoid when

- Do not use when the user needs search; use Combobox.

## Public imports

```ts
import {
	Select,
	SelectGroup,
	SelectGroupLabel,
	SelectItem,
	SelectPopup,
	SelectScrollDownButton,
	SelectScrollUpButton,
	SelectTrigger,
	SelectValue,
	SelectViewport,
} from "coss-svelte";
```

## Canonical Svelte pattern

```svelte
<script lang="ts">
	import { Select } from "coss-svelte";

	const options = [
		{ label: "Viewer", value: "viewer" },
		{ label: "Editor", value: "editor" },
	];
	let role = $state("");
</script>

<Select bind:value={role} name="role" {options} placeholder="Choose a role" />
```

## Key contracts

- Use for predefined selection without search. Pass `options`; custom trigger/value/popup/viewport/items still rely on that item collection.
- Use a string value for single mode and a string array for multiple mode; `bind:value`, `bind:open`, and `onValueChange` are supported.
- Bindable contract: `bind:value`, `bind:open`; optional `onValueChange`.

## Anatomy

- `Select`
- `SelectGroup`
- `SelectGroupLabel`
- `SelectItem`
- `SelectPopup`
- `SelectScrollDownButton`
- `SelectScrollUpButton`
- `SelectTrigger`
- `SelectValue`
- `SelectViewport`

## Common pitfalls

- Do not copy React/JSX, Base UI, Radix, shadcn, `asChild`, `render`, `className`, or `onClick` patterns into Svelte.
- Do not invent parts or bindings absent from the package declarations.
- Do not treat the upstream particle count as installable Svelte particle manifests.

## Pattern sources

- Search [the upstream pattern index](../particles.md#select) for 23 COSS particle descriptions, then port intent rather than TSX.
- Inspect the package declaration and component source when a prop or snippet contract is not shown here.
