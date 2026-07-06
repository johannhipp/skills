# Sidebar

A collapsible side panel for navigation and secondary content.

## Status

- Status: Experimental
- Foundation: compound
- Category: Layout & Navigation
- Particles in source inventory: 0
- COSS reference docs: https://coss.com/ui/docs/components/sidebar.md

This component is experimental in coss-svelte. Mention the status and avoid promising full upstream parity.

## Imports

```ts
import { Sidebar, SidebarContent, SidebarFooter, SidebarGroup, SidebarGroupAction, SidebarGroupContent, SidebarGroupLabel, SidebarHeader, SidebarInput, SidebarInset, SidebarMenu, SidebarMenuAction, SidebarMenuBadge, SidebarMenuButton, SidebarMenuItem, SidebarMenuSkeleton, SidebarMenuSub, SidebarMenuSubButton, SidebarMenuSubItem, SidebarProvider, SidebarRail, SidebarSeparator, SidebarTrigger } from "coss-svelte";
```

## Minimal Svelte Pattern

```svelte
<script lang="ts">
	import { Sidebar, SidebarContent, SidebarFooter, SidebarGroup, SidebarGroupAction, SidebarGroupContent } from "coss-svelte";
</script>

<Sidebar>
	<SidebarContent>Sidebar</SidebarContent>
</Sidebar>
```

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
