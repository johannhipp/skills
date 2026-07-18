# Toggle Group

A group of toggle buttons where one or multiple can be selected.

## Status and source

- Status: stable
- Foundation: bits
- Category: Toggle & Choice
- Local docs route: `/docs/components/toggle-group.md` when the coss-svelte docs app is running
- Registry artifact: `apps/registry/static/r/toggle-group.json`
- Upstream COSS design reference: <https://coss.com/ui/docs/components/toggle-group.md>

## Public imports

```ts
import { ToggleGroup, ToggleGroupItem } from "coss-svelte";
```

## Canonical Svelte pattern

```svelte
<script lang="ts">
	import { ToggleGroup } from "coss-svelte";

	const items = ["Bold", "Italic", "Underline"];
	let value = $state(["Bold"]);
</script>

<ToggleGroup aria-label="Text style" bind:value {items} type="multiple" />
```

## Key contracts

- Single mode binds a string; multiple mode binds a string array. Use `items` for text controls or ToggleGroupItem for icon/custom controls with aria-labels.
- Bindable contract: `bind:value`; optional `onValueChange`.

## Anatomy

- `ToggleGroup`
- `ToggleGroupItem`

## Common pitfalls

- Do not copy React/JSX, Base UI, Radix, shadcn, `asChild`, `render`, `className`, or `onClick` patterns into Svelte.
- Do not invent parts or bindings absent from the package declarations.
- Do not treat the upstream particle count as installable Svelte particle manifests.

## Pattern sources

- Search [the upstream pattern index](../particles.md#toggle-group) for 9 COSS particle descriptions, then port intent rather than TSX.
- Inspect the package declaration and component source when a prop or snippet contract is not shown here.
