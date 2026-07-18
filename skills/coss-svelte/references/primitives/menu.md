# Menu

A list of actions or options revealed on demand.

## Status and source

- Status: stable
- Foundation: compound
- Category: Overlays & Popups
- Local docs route: `/docs/components/menu.md` when the coss-svelte docs app is running
- Registry artifact: `apps/registry/static/r/menu.json`
- Upstream COSS design reference: <https://coss.com/ui/docs/components/menu.md>

## Avoid when

- Do not use for arbitrary form content; use Popover or Dialog.

## Public imports

```ts
import {
	Menu,
	MenuCheckboxItem,
	MenuGroup,
	MenuGroupLabel,
	MenuItem,
	MenuPopup,
	MenuRadioGroup,
	MenuRadioItem,
	MenuSeparator,
	MenuShortcut,
	MenuSub,
	MenuSubPopup,
	MenuSubTrigger,
	MenuTrigger,
} from "coss-svelte";
```

## Canonical Svelte pattern

```svelte
<script lang="ts">
	import {
		Menu, MenuGroup, MenuGroupLabel, MenuItem, MenuPopup, MenuSeparator,
		MenuSub, MenuSubPopup, MenuSubTrigger, MenuTrigger,
	} from "coss-svelte";
</script>

<Menu>
	<MenuTrigger>Actions</MenuTrigger>
	<MenuPopup>
		<MenuGroup>
			<MenuGroupLabel>Project</MenuGroupLabel>
			<MenuItem>Edit</MenuItem>
			<MenuItem>Duplicate</MenuItem>
		</MenuGroup>
		<MenuSeparator />
		<MenuSub>
			<MenuSubTrigger>Move to</MenuSubTrigger>
			<MenuSubPopup><MenuItem>Archive</MenuItem></MenuSubPopup>
		</MenuSub>
		<MenuSeparator />
		<MenuItem variant="destructive">Delete</MenuItem>
	</MenuPopup>
</Menu>
```

## Key contracts

- Use `items` only for simple flat menus; custom menus require MenuTrigger + MenuPopup.
- Pair MenuSubTrigger with MenuSubPopup inside MenuSub, and use checkbox/radio parts for persistent choices.
- Bindable contract: `bind:open`.

## Anatomy

- `Menu`
- `MenuCheckboxItem`
- `MenuGroup`
- `MenuGroupLabel`
- `MenuItem`
- `MenuPopup`
- `MenuRadioGroup`
- `MenuRadioItem`
- `MenuSeparator`
- `MenuShortcut`
- `MenuSub`
- `MenuSubPopup`
- `MenuSubTrigger`
- `MenuTrigger`

## Common pitfalls

- Do not copy React/JSX, Base UI, Radix, shadcn, `asChild`, `render`, `className`, or `onClick` patterns into Svelte.
- Do not invent parts or bindings absent from the package declarations.
- Do not treat the upstream particle count as installable Svelte particle manifests.

## Pattern sources

- Search [the upstream pattern index](../particles.md#menu) for 9 COSS particle descriptions, then port intent rather than TSX.
- Inspect the package declaration and component source when a prop or snippet contract is not shown here.
