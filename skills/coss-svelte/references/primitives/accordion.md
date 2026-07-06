# Accordion

A set of collapsible panels with headings.

## Status

- Status: Stable
- Foundation: bits
- Category: Layout & Navigation
- Particles in source inventory: 4
- COSS reference docs: https://coss.com/ui/docs/components/accordion.md

## Imports

```ts
import { Accordion, AccordionContent, AccordionHeader, AccordionItem, AccordionTrigger } from "coss-svelte";
```

## Minimal Svelte Pattern

```svelte
<script lang="ts">
	import { Accordion, AccordionContent, AccordionHeader, AccordionItem, AccordionTrigger } from "coss-svelte";
</script>

<Accordion>
	<AccordionContent>Accordion</AccordionContent>
</Accordion>
```

## Anatomy

- `Accordion`
- `AccordionContent`
- `AccordionHeader`
- `AccordionItem`
- `AccordionTrigger`

## Composition Rules

- Use the exported coss-svelte parts listed above.
- Preserve Svelte syntax and accessibility semantics.
- Prefer documented local examples before adapting upstream COSS React snippets.
- Keep child parts inside the root component unless the docs for this primitive state otherwise.

## Common Pitfalls

- Importing React COSS, Radix, shadcn, or Base UI APIs instead of `coss-svelte`.
- Copying JSX, hooks, `className`, `asChild`, or `render` patterns into Svelte.
- Ignoring the component status when using experimental or deferred primitives.
- Replacing accessible exported parts with anonymous divs that lose labels, roles, or focus behavior.
