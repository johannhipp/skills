# Table

A structured data display component with rows and columns.

## Status and source

- Status: stable
- Foundation: native
- Category: Content & Display
- Local docs route: `/docs/components/table.md` when the coss-svelte docs app is running
- Registry artifact: `apps/registry/static/r/table.json`
- Upstream COSS design reference: <https://coss.com/ui/docs/components/table.md>

## Public imports

```ts
import {
	Table,
	TableBody,
	TableCaption,
	TableCell,
	TableFooter,
	TableHead,
	TableHeader,
	TableRow,
} from "coss-svelte";
```

## Canonical Svelte pattern

```svelte
<script lang="ts">
	import { Table, TableBody, TableCell, TableHead, TableHeader, TableRow } from "coss-svelte";
</script>

<Table>
	<TableHeader>
		<TableRow><TableHead>Project</TableHead><TableHead>Status</TableHead></TableRow>
	</TableHeader>
	<TableBody>
		<TableRow><TableCell>Website</TableCell><TableCell>Active</TableCell></TableRow>
		<TableRow><TableCell>Mobile app</TableCell><TableCell>Paused</TableCell></TableRow>
	</TableBody>
</Table>
```

## Key contracts

- Preserve native table/header/body/row/head/cell hierarchy. Use TableHead scope correctly and do not replace tabular data with generic grid divs.

## Anatomy

- `Table`
- `TableBody`
- `TableCaption`
- `TableCell`
- `TableFooter`
- `TableHead`
- `TableHeader`
- `TableRow`

## Common pitfalls

- Do not copy React/JSX, Base UI, Radix, shadcn, `asChild`, `render`, `className`, or `onClick` patterns into Svelte.
- Do not invent parts or bindings absent from the package declarations.
- Do not treat the upstream particle count as installable Svelte particle manifests.

## Pattern sources

- Search [the upstream pattern index](../particles.md#table) for 8 COSS particle descriptions, then port intent rather than TSX.
- Inspect the package declaration and component source when a prop or snippet contract is not shown here.
