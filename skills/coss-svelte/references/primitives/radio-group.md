# Radio Group

A set of mutually exclusive options presented as radio buttons.

## Status and source

- Status: stable
- Foundation: bits
- Category: Toggle & Choice
- Local docs route: `/docs/components/radio-group.md` when the coss-svelte docs app is running
- Registry artifact: `apps/registry/static/r/radio-group.json`
- Upstream COSS design reference: <https://coss.com/ui/docs/components/radio-group.md>

## Public imports

```ts
import { RadioGroup, RadioGroupItem } from "coss-svelte";
```

## Canonical Svelte pattern

```svelte
<script lang="ts">
	import { RadioGroup } from "coss-svelte";

	const options = ["SvelteKit", "Astro", "Next.js"];
	let value = $state("SvelteKit");
</script>

<RadioGroup aria-label="Framework" bind:value {options} />
```

## Key contracts

- Use `options` for the compact path or RadioGroupItem children for custom rows. Bind a scalar value and give the root an accessible label.
- Bindable contract: `bind:value`.

## Anatomy

- `RadioGroup`
- `RadioGroupItem`

## Common pitfalls

- Do not copy React/JSX, Base UI, Radix, shadcn, `asChild`, `render`, `className`, or `onClick` patterns into Svelte.
- Do not invent parts or bindings absent from the package declarations.
- Do not treat the upstream particle count as installable Svelte particle manifests.

## Pattern sources

- Search [the upstream pattern index](../particles.md#radio-group) for 6 COSS particle descriptions, then port intent rather than TSX.
- Inspect the package declaration and component source when a prop or snippet contract is not shown here.
