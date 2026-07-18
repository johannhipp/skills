# Toolbar

A container for grouping related actions or controls.

## Status and source

- Status: stable
- Foundation: bits
- Category: Layout & Navigation
- Local docs route: `/docs/components/toolbar.md` when the coss-svelte docs app is running
- Registry artifact: `apps/registry/static/r/toolbar.json`
- Upstream COSS design reference: <https://coss.com/ui/docs/components/toolbar.md>

## Public imports

```ts
import {
	Toolbar,
	ToolbarButton,
	ToolbarGroup,
	ToolbarGroupItem,
	ToolbarLink,
	ToolbarSeparator,
} from "coss-svelte";
```

## Canonical Svelte pattern

```svelte
<script lang="ts">
	import { Toolbar, ToolbarButton, ToolbarGroup, ToolbarSeparator } from "coss-svelte";
</script>

<Toolbar aria-label="Editor actions">
	<ToolbarGroup>
		<ToolbarButton>Undo</ToolbarButton>
		<ToolbarButton>Redo</ToolbarButton>
	</ToolbarGroup>
	<ToolbarSeparator />
	<ToolbarButton>Save</ToolbarButton>
</Toolbar>
```

## Key contracts

- Give the toolbar an accessible label, group related controls, and use separators sparingly. ToolbarGroup value shape follows its selection type.

## Anatomy

- `Toolbar`
- `ToolbarButton`
- `ToolbarGroup`
- `ToolbarGroupItem`
- `ToolbarLink`
- `ToolbarSeparator`

## Common pitfalls

- Do not copy React/JSX, Base UI, Radix, shadcn, `asChild`, `render`, `className`, or `onClick` patterns into Svelte.
- Do not invent parts or bindings absent from the package declarations.
- Do not treat the upstream particle count as installable Svelte particle manifests.

## Pattern sources

- Search [the upstream pattern index](../particles.md#toolbar) for 1 COSS particle descriptions, then port intent rather than TSX.
- Inspect the package declaration and component source when a prop or snippet contract is not shown here.
