# Input

A native input element.

## Status and source

- Status: stable
- Foundation: native
- Category: Selection & Input
- Local docs route: `/docs/components/input.md` when the coss-svelte docs app is running
- Registry artifact: `apps/registry/static/r/input.json`
- Upstream COSS design reference: <https://coss.com/ui/docs/components/input.md>

## Public imports

```ts
import { Input } from "coss-svelte";
```

## Canonical Svelte pattern

```svelte
<script lang="ts">
	import { Input } from "coss-svelte";
</script>

<Input aria-label="Project name" name="project" placeholder="Acme" type="text" />
```

## Key contracts

- Set an explicit input `type`, `name`, and accessible label. Input supports `bind:value` and consumes Field context when nested.
- Bindable contract: `bind:value`.

## Anatomy

- `Input`

## Common pitfalls

- Do not copy React/JSX, Base UI, Radix, shadcn, `asChild`, `render`, `className`, or `onClick` patterns into Svelte.
- Do not invent parts or bindings absent from the package declarations.
- Do not treat the upstream particle count as installable Svelte particle manifests.

## Pattern sources

- Search [the upstream pattern index](../particles.md#input) for 19 COSS particle descriptions, then port intent rather than TSX.
- Inspect the package declaration and component source when a prop or snippet contract is not shown here.
