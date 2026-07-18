# Sidebar

An experimental collapsible navigation shell with provider-backed open state.

> Experimental: verify the installed source before relying on production parity.

## Contents

- Status and source
- Public imports and canonical pattern
- Key contracts and anatomy
- Pitfalls and pattern sources

## Status and source

- Status: experimental
- Foundation: compound
- Category: Layout & Navigation
- Local docs route: `/docs/components/sidebar.md` when the coss-svelte docs app is running
- Registry artifact: `apps/registry/static/r/sidebar.json`
- Upstream COSS design reference: <https://coss.com/ui/docs/components/sidebar.md>

## Public imports

```ts
import {
	Sidebar,
	SidebarContent,
	SidebarFooter,
	SidebarGroup,
	SidebarGroupAction,
	SidebarGroupContent,
	SidebarGroupLabel,
	SidebarHeader,
	SidebarInput,
	SidebarInset,
	SidebarMenu,
	SidebarMenuAction,
	SidebarMenuBadge,
	SidebarMenuButton,
	SidebarMenuItem,
	SidebarMenuSkeleton,
	SidebarMenuSub,
	SidebarMenuSubButton,
	SidebarMenuSubItem,
	SidebarProvider,
	SidebarRail,
	SidebarSeparator,
	SidebarTrigger,
} from "coss-svelte";
```

## Canonical Svelte pattern

```svelte
<script lang="ts">
	import { Sidebar, SidebarInset, SidebarProvider, SidebarTrigger } from "coss-svelte";

	const items = [
		{ label: "Overview", href: "/overview" },
		{ label: "Settings", href: "/settings" },
	];
</script>

<SidebarProvider>
	<Sidebar {items} label="Workspace" />
	<SidebarInset>
		<header><SidebarTrigger /> Dashboard</header>
		<main>Workspace content</main>
	</SidebarInset>
</SidebarProvider>
```

## Key contracts

- Experimental: wrap interactive/collapsible layouts in SidebarProvider so SidebarTrigger can toggle shared state.
- The `items` convenience path is a simple link list; use exported menu/group parts for a production navigation shell.
- Bindable contract: `bind:open` on SidebarProvider.

## Anatomy

- `Sidebar`
- `SidebarContent`
- `SidebarFooter`
- `SidebarGroup`
- `SidebarGroupAction`
- `SidebarGroupContent`
- `SidebarGroupLabel`
- `SidebarHeader`
- `SidebarInput`
- `SidebarInset`
- `SidebarMenu`
- `SidebarMenuAction`
- `SidebarMenuBadge`
- `SidebarMenuButton`
- `SidebarMenuItem`
- `SidebarMenuSkeleton`
- `SidebarMenuSub`
- `SidebarMenuSubButton`
- `SidebarMenuSubItem`
- `SidebarProvider`
- `SidebarRail`
- `SidebarSeparator`
- `SidebarTrigger`

## Common pitfalls

- Do not copy React/JSX, Base UI, Radix, shadcn, `asChild`, `render`, `className`, or `onClick` patterns into Svelte.
- Do not invent parts or bindings absent from the package declarations.
- Do not treat the upstream particle count as installable Svelte particle manifests.

## Pattern sources

- No upstream COSS particle inventory is recorded for this component.
- Inspect the package declaration and component source when a prop or snippet contract is not shown here.
