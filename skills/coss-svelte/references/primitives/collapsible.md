# Collapsible

A component that toggles visibility of content sections.

## Status and source

- Status: stable
- Foundation: bits
- Category: Layout & Navigation
- Local docs route: `/docs/components/collapsible.md` when the coss-svelte docs app is running
- Registry artifact: `apps/registry/static/r/collapsible.json`
- Upstream COSS design reference: <https://coss.com/ui/docs/components/collapsible.md>

## Public imports

```ts
import { Collapsible, CollapsibleContent, CollapsibleTrigger } from "coss-svelte";
```

## Canonical Svelte pattern

```svelte
<script lang="ts">
	import { Collapsible } from "coss-svelte";
</script>

<Collapsible title="Show recovery keys">
	<ul>
		<li>4829-1735-6621</li>
		<li>9182-6407-5532</li>
	</ul>
</Collapsible>
```

## Key contracts

- Use the `title` convenience prop for a simple disclosure or compose trigger/content parts. Bind `open` for controlled state.
- Bindable contract: `bind:open`.

## Anatomy

- `Collapsible`
- `CollapsibleContent`
- `CollapsibleTrigger`

## Common pitfalls

- Do not copy React/JSX, Base UI, Radix, shadcn, `asChild`, `render`, `className`, or `onClick` patterns into Svelte.
- Do not invent parts or bindings absent from the package declarations.
- Do not treat the upstream particle count as installable Svelte particle manifests.

## Pattern sources

- Search [the upstream pattern index](../particles.md#collapsible) for 1 COSS particle descriptions, then port intent rather than TSX.
- Inspect the package declaration and component source when a prop or snippet contract is not shown here.
