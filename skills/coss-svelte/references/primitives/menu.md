# Menu

A list of actions or options revealed on demand.

## Status

- Status: Stable
- Foundation: compound
- Category: Overlays & Popups
- Particles in source inventory: 9
- COSS reference docs: https://coss.com/ui/docs/components/menu.md

## Imports

```ts
import { Menu, MenuCheckboxItem, MenuGroup, MenuGroupLabel, MenuItem, MenuPopup, MenuRadioGroup, MenuRadioItem, MenuSeparator, MenuShortcut, MenuSub, MenuSubPopup, MenuSubTrigger, MenuTrigger } from "coss-svelte";
```

## Minimal Svelte Pattern

```svelte
<script lang="ts">
	import { Menu, MenuCheckboxItem, MenuGroup, MenuGroupLabel, MenuItem, MenuPopup } from "coss-svelte";
</script>

<Menu>
	<MenuCheckboxItem>Menu</MenuCheckboxItem>
</Menu>
```

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
