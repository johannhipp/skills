# Drawer

A panel that slides in from the edge of the screen with swipe gestures, snap points, and nested drawer support.

## Status

- Status: Experimental
- Foundation: custom
- Category: Overlays & Popups
- Particles in source inventory: 14
- COSS reference docs: https://coss.com/ui/docs/components/drawer.md

This component is experimental in coss-svelte. Mention the status and avoid promising full upstream parity.

## Imports

```ts
import { Drawer, DrawerClose, DrawerContent, DrawerCreateHandle, DrawerDescription, DrawerFooter, DrawerHeader, DrawerPanel, DrawerPopup, DrawerTitle, DrawerTrigger } from "coss-svelte";
```

## Minimal Svelte Pattern

```svelte
<script lang="ts">
	import { Drawer, DrawerClose, DrawerContent, DrawerCreateHandle, DrawerDescription, DrawerFooter } from "coss-svelte";
</script>

<Drawer>
	<DrawerClose>Drawer</DrawerClose>
</Drawer>
```

## Anatomy

- `Drawer`
- `DrawerClose`
- `DrawerContent`
- `DrawerCreateHandle`
- `DrawerDescription`
- `DrawerFooter`
- `DrawerHeader`
- `DrawerPanel`
- `DrawerPopup`
- `DrawerTitle`
- `DrawerTrigger`

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
