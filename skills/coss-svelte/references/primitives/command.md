# Command

A command palette component built with Dialog and Autocomplete for searching and executing commands.

## Status and source

- Status: stable
- Foundation: compound
- Category: Overlays & Popups
- Local docs route: `/docs/components/command.md` when the coss-svelte docs app is running
- Registry artifact: `apps/registry/static/r/command.json`
- Upstream COSS design reference: <https://coss.com/ui/docs/components/command.md>

## Public imports

```ts
import {
	Command,
	CommandCollection,
	CommandDialog,
	CommandDialogPopup,
	CommandDialogTrigger,
	CommandEmpty,
	CommandFooter,
	CommandGroup,
	CommandGroupLabel,
	CommandInput,
	CommandItem,
	CommandList,
	CommandPanel,
	CommandSeparator,
	CommandShortcut,
} from "coss-svelte";
```

## Canonical Svelte pattern

```svelte
<script lang="ts">
	import { Command, CommandDialog, CommandDialogPopup, CommandDialogTrigger } from "coss-svelte";

	const items = [
		{ label: "Open settings", value: "settings" },
		{ label: "Create project", value: "create" },
	];
</script>

<CommandDialog>
	<CommandDialogTrigger>Open command palette</CommandDialogTrigger>
	<CommandDialogPopup>
		<Command {items} label="Commands" placeholder="Search commands" />
	</CommandDialogPopup>
</CommandDialog>
```

## Key contracts

- This wrapper is Bits UI Command, not cmdk. Use `items` for a flat list or preserve input/empty/list/collection/group/item structure in custom palettes.
- Bindable contract: `bind:value`.

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

## Common pitfalls

- Do not copy React/JSX, Base UI, Radix, shadcn, `asChild`, `render`, `className`, or `onClick` patterns into Svelte.
- Do not invent parts or bindings absent from the package declarations.
- Do not treat the upstream particle count as installable Svelte particle manifests.

## Pattern sources

- Search [the upstream pattern index](../particles.md#command) for 2 COSS particle descriptions, then port intent rather than TSX.
- Inspect the package declaration and component source when a prop or snippet contract is not shown here.
