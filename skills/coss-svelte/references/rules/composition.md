# Composition rules

## Select a root mode

Use one mode deliberately:

- **Convenience mode:** pass root data props such as `items`, `options`, `tabs`, `trigger`, `title`, or `description` and let the component render its fallback anatomy.
- **Composed mode:** provide exported child parts for custom content and layout.

For Menu, Select, Combobox, Autocomplete, Command, Popover, PreviewCard, and Tooltip, custom children replace the built-in fallback content. ContextMenu is composed-only and always requires a trigger and popup.

For Dialog, AlertDialog, Sheet, and Drawer, root `title` or `description` activates a convenience scaffold. Omit those root props when composing Trigger/Popup/Title/Description parts yourself.

For Accordion and ToggleGroup, a non-empty `items` array takes precedence over custom children. For Tabs, a non-empty `tabs` array renders convenience triggers/panels.

## Compose overlays

Preserve this shape when the parts exist:

```svelte
<Dialog>
	<DialogTrigger>Open</DialogTrigger>
	<DialogPopup>
		<DialogHeader>
			<DialogTitle>Title</DialogTitle>
			<DialogDescription>Description</DialogDescription>
		</DialogHeader>
		<DialogPanel>Body</DialogPanel>
		<DialogFooter><DialogClose>Close</DialogClose></DialogFooter>
	</DialogPopup>
</Dialog>
```

- Keep popup parts inside their root so Bits UI context exists.
- Keep Dialog/AlertDialog titles and descriptions inside the popup.
- Keep MenuSubTrigger and MenuSubPopup inside MenuSub.
- Keep ContextMenuSubTrigger and ContextMenuSubPopup inside ContextMenuSub; preserve the root trigger's Shift+F10 and Context Menu key access.
- Keep Select/Combobox collection items inside the documented popup/list/viewport structure.
- Do not add a second portal or overlay around composed `*Popup` wrappers; those wrappers already portal their content where implemented. Configure the owned portal through documented `portalProps`.

## Use Svelte state contracts

- Prefer `bind:open`, `bind:value`, `bind:checked`, `bind:pressed`, or `bind:page` only when the generated declaration marks the prop bindable.
- Match scalar values to `type="single"` and arrays to `type="multiple"`.
- Use `onValueChange` only on wrappers that declare it; do not translate every React callback mechanically.
- Use lowercase event properties such as `onclick` and `onsubmit`, not React `onClick`/`onSubmit` casing.
- Use Svelte snippets for child render data such as Slider thumb/tick items or OTP cells.

## Use providers where they exist

- Tooltip roots establish their required provider in convenience and composed modes. The exported TooltipProvider is available for direct provider composition; do not redundantly wrap every Tooltip.
- Wrap interactive/collapsible Sidebar layouts with SidebarProvider.
- Mount ToastProvider before using the shared `toastManager`; direct `Toast bind:open` remains available for one local status surface.

## Avoid cross-ecosystem composition

- Do not use `asChild`, React `render`, JSX children functions, hooks, `cloneElement`, `className`, or Base UI imports.
- Do not reach into Bits UI directly unless the user explicitly asks for a custom primitive outside the coss-svelte public surface.
- Do not flatten accessible exported parts into anonymous divs.
