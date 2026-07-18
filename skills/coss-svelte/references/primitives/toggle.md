# Toggle

A button that switches between two states.

## Status and source

- Status: stable
- Foundation: bits
- Category: Toggle & Choice
- Local docs route: `/docs/components/toggle.md` when the coss-svelte docs app is running
- Registry artifact: `apps/registry/static/r/toggle.json`
- Upstream COSS design reference: <https://coss.com/ui/docs/components/toggle.md>

## Public imports

```ts
import { Toggle } from "coss-svelte";
```

## Canonical Svelte pattern

```svelte
<script lang="ts">
	import { Toggle } from "coss-svelte";
</script>

<Toggle>Toggle</Toggle>
```

## Key contracts

- Use for a pressable on/off command and bind `pressed`; use Switch for a preference whose effect is immediate and persistent.
- Bindable contract: `bind:pressed`.

## Anatomy

- `Toggle`

## Common pitfalls

- Do not copy React/JSX, Base UI, Radix, shadcn, `asChild`, `render`, `className`, or `onClick` patterns into Svelte.
- Do not invent parts or bindings absent from the package declarations.
- Do not treat the upstream particle count as installable Svelte particle manifests.

## Pattern sources

- Search [the upstream pattern index](../particles.md#toggle) for 8 COSS particle descriptions, then port intent rather than TSX.
- Inspect the package declaration and component source when a prop or snippet contract is not shown here.
