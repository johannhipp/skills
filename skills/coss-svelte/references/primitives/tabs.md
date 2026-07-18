# Tabs

A component for toggling between related panels on the same page.

## Status and source

- Status: stable
- Foundation: bits
- Category: Layout & Navigation
- Local docs route: `/docs/components/tabs.md` when the coss-svelte docs app is running
- Registry artifact: `apps/registry/static/r/tabs.json`
- Upstream COSS design reference: <https://coss.com/ui/docs/components/tabs.md>

## Avoid when

- Do not use when each view needs a shareable URL; prefer route navigation.

## Public imports

```ts
import {
	Tabs,
	TabsContent,
	TabsList,
	TabsTrigger,
} from "coss-svelte";
```

## Canonical Svelte pattern

```svelte
<script lang="ts">
	import { Tabs, TabsContent, TabsList, TabsTrigger } from "coss-svelte";
</script>

<Tabs value="tab-1">
	<TabsList>
		<TabsTrigger value="tab-1">Tab 1</TabsTrigger>
		<TabsTrigger value="tab-2">Tab 2</TabsTrigger>
		<TabsTrigger value="tab-3">Tab 3</TabsTrigger>
	</TabsList>
	<TabsContent class="text-center text-muted-foreground text-sm" value="tab-1">
		Tab 1 content
	</TabsContent>
	<TabsContent class="text-center text-muted-foreground text-sm" value="tab-2">
		Tab 2 content
	</TabsContent>
	<TabsContent class="text-center text-muted-foreground text-sm" value="tab-3">
		Tab 3 content
	</TabsContent>
</Tabs>
```

## Key contracts

- Match every TabsTrigger value with a TabsContent value. Use `tabs` for the convenience path or exported parts for custom panels; bind a scalar value.
- Bindable contract: `bind:value`.

## Anatomy

- `Tabs`
- `TabsContent`
- `TabsList`
- `TabsTrigger`

## Common pitfalls

- Do not copy React/JSX, Base UI, Radix, shadcn, `asChild`, `render`, `className`, or `onClick` patterns into Svelte.
- Do not invent parts or bindings absent from the package declarations.
- Do not treat the upstream particle count as installable Svelte particle manifests.

## Pattern sources

- Search [the upstream pattern index](../particles.md#tabs) for 13 COSS particle descriptions, then port intent rather than TSX.
- Inspect the package declaration and component source when a prop or snippet contract is not shown here.
