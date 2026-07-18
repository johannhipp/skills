# Date Picker

A date selection component, often combined with a calendar in a popover or input.

## Status and source

- Status: stable
- Foundation: compound
- Category: Selection & Input
- Local docs route: `/docs/components/date-picker.md` when the coss-svelte docs app is running
- Registry artifact: `apps/registry/static/r/date-picker.json`
- Upstream COSS design reference: <https://coss.com/ui/docs/components/date-picker.md>

## Public imports

```ts
import { DatePicker } from "coss-svelte";
```

## Canonical Svelte pattern

```svelte
<script lang="ts">
	import { DatePicker } from "coss-svelte";
</script>

<DatePicker label="Pick a date" class="cn-date-picker-demo" />
```

## Key contracts

- Bind `value` and `open`; values use Bits UI/@internationalized/date contracts. Custom children replace the built-in trigger and calendar popup.
- Bindable contract: `bind:value`, `bind:open`.

## Anatomy

- `DatePicker`

## Common pitfalls

- Do not copy React/JSX, Base UI, Radix, shadcn, `asChild`, `render`, `className`, or `onClick` patterns into Svelte.
- Do not invent parts or bindings absent from the package declarations.
- Do not treat the upstream particle count as installable Svelte particle manifests.

## Pattern sources

- Search [the upstream pattern index](../particles.md#date-picker) for 9 COSS particle descriptions, then port intent rather than TSX.
- Inspect the package declaration and component source when a prop or snippet contract is not shown here.
