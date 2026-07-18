# Accordion

A set of collapsible panels with headings.

## Status and source

- Status: stable
- Foundation: bits
- Category: Layout & Navigation
- Local docs route: `/docs/components/accordion.md` when the coss-svelte docs app is running
- Registry artifact: `apps/registry/static/r/accordion.json`
- Upstream COSS design reference: <https://coss.com/ui/docs/components/accordion.md>

## Public imports

```ts
import {
	Accordion,
	AccordionContent,
	AccordionHeader,
	AccordionItem,
	AccordionTrigger,
} from "coss-svelte";
```

## Canonical Svelte pattern

```svelte
<script lang="ts">
	import { Accordion } from "coss-svelte";

	const items = [
		{ value: "billing", title: "How does billing work?", content: "Plans renew monthly." },
		{ value: "cancel", title: "Can I cancel?", content: "Cancel at any time." },
	];
</script>

<Accordion {items} value="billing" />
```

## Key contracts

- Use `items` for the compact path or exported item/header/trigger/content parts for custom markup.
- Use a string value for `type="single"` and a string array for `type="multiple"`; `bind:value` and `onValueChange` are supported.
- Bindable contract: `bind:value`; optional `onValueChange`.

## Anatomy

- `Accordion`
- `AccordionContent`
- `AccordionHeader`
- `AccordionItem`
- `AccordionTrigger`

## Common pitfalls

- Do not copy React/JSX, Base UI, Radix, shadcn, `asChild`, `render`, `className`, or `onClick` patterns into Svelte.
- Do not invent parts or bindings absent from the package declarations.
- Do not treat the upstream particle count as installable Svelte particle manifests.

## Pattern sources

- Search [the upstream pattern index](../particles.md#accordion) for 4 COSS particle descriptions, then port intent rather than TSX.
- Inspect the package declaration and component source when a prop or snippet contract is not shown here.
