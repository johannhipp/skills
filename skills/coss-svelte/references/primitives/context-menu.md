# Context Menu

A menu of contextual actions opened from a pointer or keyboard target.

## Status and source

- Status: stable
- Foundation: bits
- Category: Overlays & Popups
- Local docs route: `/docs/components/context-menu.md` when the coss-svelte docs app is running
- Registry artifact: `apps/registry/static/r/context-menu.json`
- Upstream COSS design reference: <https://coss.com/ui/docs/components/context-menu.md>

## Avoid when

- Use Menu for a visible action trigger. Context Menu is for secondary actions attached to a region and must not be the only way to reach essential actions.

## Public imports

```ts
import {
	ContextMenu,
	ContextMenuCheckboxItem,
	ContextMenuGroup,
	ContextMenuGroupLabel,
	ContextMenuItem,
	ContextMenuLinkItem,
	ContextMenuPopup,
	ContextMenuRadioGroup,
	ContextMenuRadioItem,
	ContextMenuSeparator,
	ContextMenuShortcut,
	ContextMenuSub,
	ContextMenuSubPopup,
	ContextMenuSubTrigger,
	ContextMenuTrigger,
} from "coss-svelte";
```

## Canonical Svelte pattern

```svelte
<script lang="ts">
	import {
		ContextMenu,
		ContextMenuItem,
		ContextMenuPopup,
		ContextMenuSeparator,
		ContextMenuTrigger,
	} from "coss-svelte";
</script>

<ContextMenu>
	<ContextMenuTrigger class="block" aria-label="File actions" tabindex="0">
		<div>Right click or press Shift+F10</div>
	</ContextMenuTrigger>
	<ContextMenuPopup>
		<ContextMenuItem>Rename</ContextMenuItem>
		<ContextMenuSeparator />
		<ContextMenuItem variant="destructive">Delete</ContextMenuItem>
	</ContextMenuPopup>
</ContextMenu>
```

## Key contracts

- `ContextMenuTrigger` opens on right click and supports Shift+F10 or the Context Menu key. Make a non-interactive trigger region keyboard-focusable when keyboard access would otherwise be impossible.
- Keep `ContextMenuSubTrigger` and `ContextMenuSubPopup` inside `ContextMenuSub`. Escape closes a submenu before the root; keyboard-opened menus restore focus to their trigger.
- Use `ContextMenuCheckboxItem` with `bind:checked`/`bind:indeterminate`, and put `ContextMenuRadioItem` values inside a `ContextMenuRadioGroup bind:value`.
- Use `ContextMenuLinkItem` for navigation instead of placing an anonymous anchor inside an action item.
- Root and sub popups already portal. Pass exact Bits UI portal options through `portalProps`; do not wrap them in a second portal.
- Bindable contract: `bind:open`; submenus also expose `bind:open`.

## Anatomy

- `ContextMenu`
- `ContextMenuCheckboxItem`
- `ContextMenuGroup`
- `ContextMenuGroupLabel`
- `ContextMenuItem`
- `ContextMenuLinkItem`
- `ContextMenuPopup`
- `ContextMenuRadioGroup`
- `ContextMenuRadioItem`
- `ContextMenuSeparator`
- `ContextMenuShortcut`
- `ContextMenuSub`
- `ContextMenuSubPopup`
- `ContextMenuSubTrigger`
- `ContextMenuTrigger`

## Common pitfalls

- Do not make contextual actions pointer-only or hide essential actions exclusively behind the context menu.
- Do not copy React/JSX, Base UI, Radix, shadcn, `asChild`, `render`, `className`, or `onClick` patterns into Svelte.
- Do not invent parts or bindings absent from the package declarations.
- Do not treat the upstream particle count as installable Svelte particle manifests.

## Pattern sources

- Search [the upstream pattern index](../particles.md#context-menu) for 8 COSS particle descriptions, then port intent rather than TSX.
- Inspect the package declaration and component source when a prop or snippet contract is not shown here.
