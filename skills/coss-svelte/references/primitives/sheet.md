# Sheet

A flyout that opens from the side of the screen, based on the dialog component.

## Status and source

- Status: stable
- Foundation: compound
- Category: Overlays & Popups
- Local docs route: `/docs/components/sheet.md` when the coss-svelte docs app is running
- Registry artifact: `apps/registry/static/r/sheet.json`
- Upstream COSS design reference: <https://coss.com/ui/docs/components/sheet.md>

## Public imports

```ts
import {
	Sheet,
	SheetClose,
	SheetContent,
	SheetDescription,
	SheetFooter,
	SheetHeader,
	SheetPanel,
	SheetPopup,
	SheetTitle,
	SheetTrigger,
} from "coss-svelte";
```

## Canonical Svelte pattern

```svelte
<script lang="ts">
	import {
		Button, Field, Form, Input, Sheet, SheetClose, SheetDescription, SheetFooter,
		SheetHeader, SheetPanel, SheetPopup, SheetTitle, SheetTrigger,
	} from "coss-svelte";
</script>

<Sheet>
	<SheetTrigger>Edit profile</SheetTrigger>
	<SheetPopup side="right">
		<SheetHeader>
			<SheetTitle>Edit profile</SheetTitle>
			<SheetDescription>Update your account details.</SheetDescription>
		</SheetHeader>
		<Form class="contents" onsubmit={(event) => event.preventDefault()}>
			<SheetPanel><Field label="Name"><Input name="name" type="text" /></Field></SheetPanel>
			<SheetFooter>
				<SheetClose>Cancel</SheetClose>
				<Button type="submit">Save</Button>
			</SheetFooter>
		</Form>
	</SheetPopup>
</Sheet>
```

## Key contracts

- Sheet is Dialog-backed; keep trigger/popup/header/title/description/panel/footer/close inside the root and set `side` on SheetPopup.
- For forms, wrap panel and footer in `Form class="contents"` so footer submit actions belong to the form.
- Bindable contract: `bind:open`.

## Anatomy

- `Sheet`
- `SheetClose`
- `SheetContent`
- `SheetDescription`
- `SheetFooter`
- `SheetHeader`
- `SheetPanel`
- `SheetPopup`
- `SheetTitle`
- `SheetTrigger`

## Common pitfalls

- Do not copy React/JSX, Base UI, Radix, shadcn, `asChild`, `render`, `className`, or `onClick` patterns into Svelte.
- Do not invent parts or bindings absent from the package declarations.
- Do not treat the upstream particle count as installable Svelte particle manifests.

## Pattern sources

- Search [the upstream pattern index](../particles.md#sheet) for 3 COSS particle descriptions, then port intent rather than TSX.
- Inspect the package declaration and component source when a prop or snippet contract is not shown here.
