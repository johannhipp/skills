# Empty

A container for displaying empty state information.

## Status and source

- Status: stable
- Foundation: native
- Category: Content & Display
- Local docs route: `/docs/components/empty.md` when the coss-svelte docs app is running
- Registry artifact: `apps/registry/static/r/empty.json`
- Upstream COSS design reference: <https://coss.com/ui/docs/components/empty.md>

## Public imports

```ts
import {
	Empty,
	EmptyContent,
	EmptyDescription,
	EmptyHeader,
	EmptyMedia,
	EmptyTitle,
} from "coss-svelte";
```

## Canonical Svelte pattern

```svelte
<script lang="ts">
	import { Button, Empty, EmptyContent, EmptyDescription, EmptyHeader, EmptyTitle } from "coss-svelte";
</script>

<Empty>
	<EmptyHeader>
		<EmptyTitle>No projects yet</EmptyTitle>
		<EmptyDescription>Create a project to get started.</EmptyDescription>
	</EmptyHeader>
	<EmptyContent><Button type="button">Create project</Button></EmptyContent>
</Empty>
```

## Key contracts

- Use header/title/description for the explanation and content for recovery actions; do not show an empty state while data is merely loading.

## Anatomy

- `Empty`
- `EmptyContent`
- `EmptyDescription`
- `EmptyHeader`
- `EmptyMedia`
- `EmptyTitle`

## Common pitfalls

- Do not copy React/JSX, Base UI, Radix, shadcn, `asChild`, `render`, `className`, or `onClick` patterns into Svelte.
- Do not invent parts or bindings absent from the package declarations.
- Do not treat the upstream particle count as installable Svelte particle manifests.

## Pattern sources

- Search [the upstream pattern index](../particles.md#empty) for 1 COSS particle descriptions, then port intent rather than TSX.
- Inspect the package declaration and component source when a prop or snippet contract is not shown here.
