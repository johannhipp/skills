# Dialog

A modal overlay for displaying content that requires user interaction.

## Status and source

- Status: stable
- Foundation: bits
- Category: Overlays & Popups
- Local docs route: `/docs/components/dialog.md` when the coss-svelte docs app is running
- Registry artifact: `apps/registry/static/r/dialog.json`
- Upstream COSS design reference: <https://coss.com/ui/docs/components/dialog.md>

## Avoid when

- Do not use for a lightweight anchored editor; use Popover. Use AlertDialog for irreversible confirmation.

## Public imports

```ts
import {
	Dialog,
	DialogClose,
	DialogDescription,
	DialogFooter,
	DialogHeader,
	DialogPanel,
	DialogPopup,
	DialogTitle,
	DialogTrigger,
} from "coss-svelte";
```

## Canonical Svelte pattern

```svelte
<script lang="ts">
	import {
		Button, Dialog, DialogClose, DialogDescription, DialogFooter, DialogHeader,
		DialogPanel, DialogPopup, DialogTitle, DialogTrigger, Field, Form, Input,
	} from "coss-svelte";
</script>

<Dialog>
	<DialogTrigger>Edit profile</DialogTrigger>
	<DialogPopup>
		<DialogHeader>
			<DialogTitle>Edit profile</DialogTitle>
			<DialogDescription>Update the public name for this account.</DialogDescription>
		</DialogHeader>
		<Form class="contents" onsubmit={(event) => event.preventDefault()}>
			<DialogPanel>
				<Field label="Name" required><Input name="name" type="text" /></Field>
			</DialogPanel>
			<DialogFooter>
				<DialogClose>Cancel</DialogClose>
				<Button type="submit">Save</Button>
			</DialogFooter>
		</Form>
	</DialogPopup>
</Dialog>
```

## Key contracts

- Keep title and description in the popup for accessible modal naming; use `DialogPanel` for body content.
- When composing parts, omit root `title`/`description`; those props activate a separate convenience scaffold.
- For forms, place `Form class="contents"` around panel and footer so the submit button remains inside the form.
- Bindable contract: `bind:open`.

## Anatomy

- `Dialog`
- `DialogClose`
- `DialogDescription`
- `DialogFooter`
- `DialogHeader`
- `DialogPanel`
- `DialogPopup`
- `DialogTitle`
- `DialogTrigger`

## Common pitfalls

- Do not copy React/JSX, Base UI, Radix, shadcn, `asChild`, `render`, `className`, or `onClick` patterns into Svelte.
- Do not invent parts or bindings absent from the package declarations.
- Do not treat the upstream particle count as installable Svelte particle manifests.

## Pattern sources

- Search [the upstream pattern index](../particles.md#dialog) for 6 COSS particle descriptions, then port intent rather than TSX.
- Inspect the package declaration and component source when a prop or snippet contract is not shown here.
