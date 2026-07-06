# Card

A content container for grouping related information.

## Status

- Status: Stable
- Foundation: native
- Category: Content & Display
- Particles in source inventory: 11
- COSS reference docs: https://coss.com/ui/docs/components/card.md

## Imports

```ts
import { Card, CardDescription, CardFooter, CardHeader, CardPanel, CardTitle } from "coss-svelte";
```

## Minimal Svelte Pattern

```svelte
<script lang="ts">
	import { Card, CardDescription, CardFooter, CardHeader, CardPanel, CardTitle } from "coss-svelte";
</script>

<Card>
	<CardDescription>Card</CardDescription>
</Card>
```

## Anatomy

- `Card`
- `CardDescription`
- `CardFooter`
- `CardHeader`
- `CardPanel`
- `CardTitle`

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
