# Pagination

A pagination with page navigation, next and previous links.

## Status and source

- Status: stable
- Foundation: bits
- Category: Layout & Navigation
- Local docs route: `/docs/components/pagination.md` when the coss-svelte docs app is running
- Registry artifact: `apps/registry/static/r/pagination.json`
- Upstream COSS design reference: <https://coss.com/ui/docs/components/pagination.md>

## Public imports

```ts
import {
	Pagination,
	PaginationContent,
	PaginationEllipsis,
	PaginationItem,
	PaginationLink,
	PaginationNext,
	PaginationNextButton,
	PaginationPage,
	PaginationPrevious,
	PaginationPrevButton,
} from "coss-svelte";
```

## Canonical Svelte pattern

```svelte
<script lang="ts">
	import { Pagination } from "coss-svelte";

	let page = $state(1);
</script>

<Pagination aria-label="Search result pages" bind:page pages={6} />
```

## Key contracts

- Use `pages` for a known page count or `count` + `perPage` for item totals. Bind `page` for controlled navigation and provide an aria-label.
- Bindable contract: `bind:page`.

## Anatomy

- `Pagination`
- `PaginationContent`
- `PaginationEllipsis`
- `PaginationItem`
- `PaginationLink`
- `PaginationNext`
- `PaginationNextButton`
- `PaginationPage`
- `PaginationPrevious`
- `PaginationPrevButton`

## Common pitfalls

- Do not copy React/JSX, Base UI, Radix, shadcn, `asChild`, `render`, `className`, or `onClick` patterns into Svelte.
- Do not invent parts or bindings absent from the package declarations.
- Do not treat the upstream particle count as installable Svelte particle manifests.

## Pattern sources

- Search [the upstream pattern index](../particles.md#pagination) for 3 COSS particle descriptions, then port intent rather than TSX.
- Inspect the package declaration and component source when a prop or snippet contract is not shown here.
