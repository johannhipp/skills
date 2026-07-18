# Group

A container component for grouping related content with consistent styling.

## Status and source

- Status: stable
- Foundation: native
- Category: Content & Display
- Local docs route: `/docs/components/group.md` when the coss-svelte docs app is running
- Registry artifact: `apps/registry/static/r/group.json`
- Upstream COSS design reference: <https://coss.com/ui/docs/components/group.md>

## Public imports

```ts
import { Group, GroupSeparator } from "coss-svelte";
```

## Canonical Svelte pattern

```svelte
<script lang="ts">
	import { Button, Group, GroupSeparator } from "coss-svelte";
</script>

<Group aria-label="View density">
	<Button type="button" variant="outline">Comfortable</Button>
	<GroupSeparator />
	<Button type="button" variant="outline">Compact</Button>
</Group>
```

## Key contracts

- Use Group for visually connected controls and GroupSeparator between segments. Keep each contained control's native semantics and label.

## Anatomy

- `Group`
- `GroupSeparator`

## Common pitfalls

- Do not copy React/JSX, Base UI, Radix, shadcn, `asChild`, `render`, `className`, or `onClick` patterns into Svelte.
- Do not invent parts or bindings absent from the package declarations.
- Do not treat the upstream particle count as installable Svelte particle manifests.

## Pattern sources

- Search [the upstream pattern index](../particles.md#group) for 22 COSS particle descriptions, then port intent rather than TSX.
- Inspect the package declaration and component source when a prop or snippet contract is not shown here.
