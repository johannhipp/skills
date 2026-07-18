# Checkbox Group

A layout and semantics wrapper for related checkboxes; each Checkbox owns its state.

## Status and source

- Status: stable
- Foundation: custom
- Category: Toggle & Choice
- Local docs route: `/docs/components/checkbox-group.md` when the coss-svelte docs app is running
- Registry artifact: `apps/registry/static/r/checkbox-group.json`
- Upstream COSS design reference: <https://coss.com/ui/docs/components/checkbox-group.md>

## Public imports

```ts
import { CheckboxGroup } from "coss-svelte";
```

## Canonical Svelte pattern

```svelte
<script lang="ts">
	import { Checkbox, CheckboxGroup } from "coss-svelte";
</script>

<CheckboxGroup label="Notifications">
	<Checkbox label="Product updates" />
	<Checkbox label="Security alerts" checked />
</CheckboxGroup>
```

## Key contracts

- CheckboxGroup provides grouping/layout only; each Checkbox still owns its checked state. Give the group and every control an accessible name.

## Anatomy

- `CheckboxGroup`

## Common pitfalls

- Do not copy React/JSX, Base UI, Radix, shadcn, `asChild`, `render`, `className`, or `onClick` patterns into Svelte.
- Do not invent parts or bindings absent from the package declarations.
- Do not treat the upstream particle count as installable Svelte particle manifests.

## Pattern sources

- Search [the upstream pattern index](../particles.md#checkbox-group) for 5 COSS particle descriptions, then port intent rather than TSX.
- Inspect the package declaration and component source when a prop or snippet contract is not shown here.
