# Calendar

A date picker for selecting single dates, ranges, or multiple dates.

## Status and source

- Status: stable
- Foundation: bits
- Category: Selection & Input
- Local docs route: `/docs/components/calendar.md` when the coss-svelte docs app is running
- Registry artifact: `apps/registry/static/r/calendar.json`
- Upstream COSS design reference: <https://coss.com/ui/docs/components/calendar.md>

## Public imports

```ts
import { Calendar } from "coss-svelte";
```

## Canonical Svelte pattern

```svelte
<script lang="ts">
	import { Calendar } from "coss-svelte";
</script>

<Calendar aria-label="Choose a date" />
```

## Key contracts

- Use `@internationalized/date` value objects when controlling dates; scalar and array value shapes follow `type`. Always provide an accessible label.
- Bindable contract: `bind:value`; optional `onValueChange`.

## Anatomy

- `Calendar`

## Common pitfalls

- Do not copy React/JSX, Base UI, Radix, shadcn, `asChild`, `render`, `className`, or `onClick` patterns into Svelte.
- Do not invent parts or bindings absent from the package declarations.
- Do not treat the upstream particle count as installable Svelte particle manifests.

## Pattern sources

- Search [the upstream pattern index](../particles.md#calendar) for 24 COSS particle descriptions, then port intent rather than TSX.
- Inspect the package declaration and component source when a prop or snippet contract is not shown here.
