# Breadcrumb

Displays the path to the current resource using a hierarchy of links.

## Status and source

- Status: stable
- Foundation: native
- Category: Layout & Navigation
- Local docs route: `/docs/components/breadcrumb.md` when the coss-svelte docs app is running
- Registry artifact: `apps/registry/static/r/breadcrumb.json`
- Upstream COSS design reference: <https://coss.com/ui/docs/components/breadcrumb.md>

## Public imports

```ts
import { Breadcrumb } from "coss-svelte";
```

## Canonical Svelte pattern

```svelte
<script lang="ts">
	import { Breadcrumb } from "coss-svelte";

	const breadcrumbItems = [
		{ label: "Home", href: "/docs/introduction" },
		{ ellipsis: true },
		{ label: "Components", href: "/docs/components/badge" },
		{ label: "Breadcrumb" },
	];
</script>

<Breadcrumb items={breadcrumbItems} />
```

## Key contracts

- Pass ordered `items`; omit `href` on the current page and use `{ ellipsis: true }` only for collapsed path segments.

## Anatomy

- `Breadcrumb`

## Common pitfalls

- Do not copy React/JSX, Base UI, Radix, shadcn, `asChild`, `render`, `className`, or `onClick` patterns into Svelte.
- Do not invent parts or bindings absent from the package declarations.
- Do not treat the upstream particle count as installable Svelte particle manifests.

## Pattern sources

- Search [the upstream pattern index](../particles.md#breadcrumb) for 7 COSS particle descriptions, then port intent rather than TSX.
- Inspect the package declaration and component source when a prop or snippet contract is not shown here.
