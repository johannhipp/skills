# Card

A content container for grouping related information.

## Status and source

- Status: stable
- Foundation: native
- Category: Content & Display
- Local docs route: `/docs/components/card.md` when the coss-svelte docs app is running
- Registry artifact: `apps/registry/static/r/card.json`
- Upstream COSS design reference: <https://coss.com/ui/docs/components/card.md>

## Public imports

```ts
import {
	Card,
	CardDescription,
	CardFooter,
	CardHeader,
	CardPanel,
	CardTitle,
} from "coss-svelte";
```

## Canonical Svelte pattern

```svelte
<script lang="ts">
	import { Button, Card, CardDescription, CardFooter, CardHeader, CardPanel, CardTitle } from "coss-svelte";
</script>

<Card class="w-full max-w-sm">
	<CardHeader>
		<CardTitle>Project status</CardTitle>
		<CardDescription>Deployment is ready for review.</CardDescription>
	</CardHeader>
	<CardPanel>All checks passed.</CardPanel>
	<CardFooter>
		<Button type="button">Open deployment</Button>
	</CardFooter>
</Card>
```

## Key contracts

- Keep header, panel, and footer roles meaningful; Card is a visual container, not automatically an article or form.

## Anatomy

- `Card`
- `CardDescription`
- `CardFooter`
- `CardHeader`
- `CardPanel`
- `CardTitle`

## Common pitfalls

- Do not copy React/JSX, Base UI, Radix, shadcn, `asChild`, `render`, `className`, or `onClick` patterns into Svelte.
- Do not invent parts or bindings absent from the package declarations.
- Do not treat the upstream particle count as installable Svelte particle manifests.

## Pattern sources

- Search [the upstream pattern index](../particles.md#card) for 11 COSS particle descriptions, then port intent rather than TSX.
- Inspect the package declaration and component source when a prop or snippet contract is not shown here.
