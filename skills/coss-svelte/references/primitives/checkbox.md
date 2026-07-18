# Checkbox

A binary toggle input for selecting one or multiple options.

## Status and source

- Status: stable
- Foundation: bits
- Category: Toggle & Choice
- Local docs route: `/docs/components/checkbox.md` when the coss-svelte docs app is running
- Registry artifact: `apps/registry/static/r/checkbox.json`
- Upstream COSS design reference: <https://coss.com/ui/docs/components/checkbox.md>

## Public imports

```ts
import { Checkbox } from "coss-svelte";
```

## Canonical Svelte pattern

```svelte
<script lang="ts">
	import { Checkbox } from "coss-svelte";
</script>

<Checkbox label="Accept terms and conditions" />
```

## Key contracts

- Use `label` or an associated external label; bind `checked` and `indeterminate` separately when needed.
- Bindable contract: `bind:checked`, `bind:indeterminate`.

## Anatomy

- `Checkbox`

## Common pitfalls

- Do not copy React/JSX, Base UI, Radix, shadcn, `asChild`, `render`, `className`, or `onClick` patterns into Svelte.
- Do not invent parts or bindings absent from the package declarations.
- Do not treat the upstream particle count as installable Svelte particle manifests.

## Pattern sources

- Search [the upstream pattern index](../particles.md#checkbox) for 5 COSS particle descriptions, then port intent rather than TSX.
- Inspect the package declaration and component source when a prop or snippet contract is not shown here.
