# Command

A command palette component built with Dialog and Autocomplete for searching and executing commands.

## Status

- Status: Stable
- Foundation: compound
- Category: Overlays & Popups
- Particles in source inventory: 2
- COSS reference docs: https://coss.com/ui/docs/components/command.md

## Imports

```ts
import { Command, CommandCollection, CommandDialog, CommandDialogPopup, CommandDialogTrigger, CommandEmpty, CommandFooter, CommandGroup, CommandGroupLabel, CommandInput, CommandItem, CommandList, CommandPanel, CommandSeparator, CommandShortcut } from "coss-svelte";
```

## Minimal Svelte Pattern

```svelte
<script lang="ts">
	import { Command, CommandCollection, CommandDialog, CommandDialogPopup, CommandDialogTrigger, CommandEmpty } from "coss-svelte";
</script>

<Command>
	<CommandCollection>Command</CommandCollection>
</Command>
```

## Anatomy

- `Command`
- `CommandCollection`
- `CommandDialog`
- `CommandDialogPopup`
- `CommandDialogTrigger`
- `CommandEmpty`
- `CommandFooter`
- `CommandGroup`
- `CommandGroupLabel`
- `CommandInput`
- `CommandItem`
- `CommandList`
- `CommandPanel`
- `CommandSeparator`
- `CommandShortcut`

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
