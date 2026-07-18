# Autocomplete

An input that suggests options as you type.

## Status and source

- Status: stable
- Foundation: compound
- Category: Selection & Input
- Local docs route: `/docs/components/autocomplete.md` when the coss-svelte docs app is running
- Registry artifact: `apps/registry/static/r/autocomplete.json`
- Upstream COSS design reference: <https://coss.com/ui/docs/components/autocomplete.md>

## Avoid when

- Do not use when input must be restricted to known options; use Combobox or Select.

## Public imports

```ts
import {
	Autocomplete,
	AutocompleteCollection,
	AutocompleteEmpty,
	AutocompleteGroup,
	AutocompleteGroupLabel,
	AutocompleteInput,
	AutocompleteItem,
	AutocompleteList,
	AutocompletePopup,
	AutocompleteSeparator,
	AutocompleteStatus,
} from "coss-svelte";
```

## Canonical Svelte pattern

```svelte
<script lang="ts">
	import { Autocomplete } from "coss-svelte";

	const options = ["Apple", "Banana", "Orange"];
	let value = $state("");
</script>

<Autocomplete bind:value {options} placeholder="Search fruit" />
```

## Key contracts

- Use for editable text with suggestions; use Combobox when the result must be an option selection.
- Pass `options` even in custom composition so Bits UI knows the item set; scalar and array value shapes follow `type`.
- Bindable contract: `bind:value`, `bind:open`; optional `onValueChange`.

## Anatomy

- `Autocomplete`
- `AutocompleteCollection`
- `AutocompleteEmpty`
- `AutocompleteGroup`
- `AutocompleteGroupLabel`
- `AutocompleteInput`
- `AutocompleteItem`
- `AutocompleteList`
- `AutocompletePopup`
- `AutocompleteSeparator`
- `AutocompleteStatus`

## Common pitfalls

- Do not copy React/JSX, Base UI, Radix, shadcn, `asChild`, `render`, `className`, or `onClick` patterns into Svelte.
- Do not invent parts or bindings absent from the package declarations.
- Do not treat the upstream particle count as installable Svelte particle manifests.

## Pattern sources

- Search [the upstream pattern index](../particles.md#autocomplete) for 15 COSS particle descriptions, then port intent rather than TSX.
- Inspect the package declaration and component source when a prop or snippet contract is not shown here.
