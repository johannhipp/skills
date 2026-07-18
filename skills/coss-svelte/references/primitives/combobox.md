# Combobox

An input combined with a list of predefined items to select.

## Status and source

- Status: stable
- Foundation: bits
- Category: Selection & Input
- Local docs route: `/docs/components/combobox.md` when the coss-svelte docs app is running
- Registry artifact: `apps/registry/static/r/combobox.json`
- Upstream COSS design reference: <https://coss.com/ui/docs/components/combobox.md>

## Avoid when

- Do not use for a short visible choice set; use RadioGroup.

## Public imports

```ts
import {
	Combobox,
	ComboboxClear,
	ComboboxCollection,
	ComboboxEmpty,
	ComboboxGroup,
	ComboboxGroupLabel,
	ComboboxInput,
	ComboboxItem,
	ComboboxList,
	ComboboxPopup,
	ComboboxSeparator,
	ComboboxTrigger,
	ComboboxValue,
} from "coss-svelte";
```

## Canonical Svelte pattern

```svelte
<script lang="ts">
	import { Combobox } from "coss-svelte";

	const options = [
		{ label: "SvelteKit", value: "sveltekit" },
		{ label: "Astro", value: "astro" },
	];
	let value = $state("");
</script>

<Combobox bind:value {options} placeholder="Choose a framework" />
```

## Key contracts

- Use for searchable option selection; use Select when search is unnecessary and Autocomplete for editable free text.
- Pass `options` to establish the item collection; scalar and array values follow `type`.
- Bindable contract: `bind:value`, `bind:open`; optional `onValueChange`.

## Anatomy

- `Combobox`
- `ComboboxClear`
- `ComboboxCollection`
- `ComboboxEmpty`
- `ComboboxGroup`
- `ComboboxGroupLabel`
- `ComboboxInput`
- `ComboboxItem`
- `ComboboxList`
- `ComboboxPopup`
- `ComboboxSeparator`
- `ComboboxTrigger`
- `ComboboxValue`

## Common pitfalls

- Do not copy React/JSX, Base UI, Radix, shadcn, `asChild`, `render`, `className`, or `onClick` patterns into Svelte.
- Do not invent parts or bindings absent from the package declarations.
- Do not treat the upstream particle count as installable Svelte particle manifests.

## Pattern sources

- Search [the upstream pattern index](../particles.md#combobox) for 18 COSS particle descriptions, then port intent rather than TSX.
- Inspect the package declaration and component source when a prop or snippet contract is not shown here.
