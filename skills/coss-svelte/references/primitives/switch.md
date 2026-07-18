# Switch

A toggle control for binary on/off states.

## Status and source

- Status: stable
- Foundation: bits
- Category: Toggle & Choice
- Local docs route: `/docs/components/switch.md` when the coss-svelte docs app is running
- Registry artifact: `apps/registry/static/r/switch.json`
- Upstream COSS design reference: <https://coss.com/ui/docs/components/switch.md>

## Public imports

```ts
import { Switch, SwitchThumb } from "coss-svelte";
```

## Canonical Svelte pattern

```svelte
<script lang="ts">
	import { Switch, SwitchThumb } from "coss-svelte";
</script>

<Switch label="Marketing emails">
	<SwitchThumb />
</Switch>
```

## Key contracts

- Use for an immediate binary preference, not a submit action. Supply `label` or another accessible name and bind `checked` when controlled.
- Bindable contract: `bind:checked`.

## Anatomy

- `Switch`
- `SwitchThumb`

## Common pitfalls

- Do not copy React/JSX, Base UI, Radix, shadcn, `asChild`, `render`, `className`, or `onClick` patterns into Svelte.
- Do not invent parts or bindings absent from the package declarations.
- Do not treat the upstream particle count as installable Svelte particle manifests.

## Pattern sources

- Search [the upstream pattern index](../particles.md#switch) for 6 COSS particle descriptions, then port intent rather than TSX.
- Inspect the package declaration and component source when a prop or snippet contract is not shown here.
