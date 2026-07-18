# Alert Dialog

A modal dialog that interrupts the user workflow for critical confirmations.

## Status and source

- Status: stable
- Foundation: bits
- Category: Overlays & Popups
- Local docs route: `/docs/components/alert-dialog.md` when the coss-svelte docs app is running
- Registry artifact: `apps/registry/static/r/alert-dialog.json`
- Upstream COSS design reference: <https://coss.com/ui/docs/components/alert-dialog.md>

## Public imports

```ts
import {
	AlertDialog,
	AlertDialogAction,
	AlertDialogCancel,
	AlertDialogDescription,
	AlertDialogFooter,
	AlertDialogHeader,
	AlertDialogPopup,
	AlertDialogTitle,
	AlertDialogTrigger,
} from "coss-svelte";
```

## Canonical Svelte pattern

```svelte
<script lang="ts">
	import {
		AlertDialog,
		AlertDialogAction,
		AlertDialogCancel,
		AlertDialogDescription,
		AlertDialogFooter,
		AlertDialogHeader,
		AlertDialogPopup,
		AlertDialogTitle,
		AlertDialogTrigger,
	} from "coss-svelte";
</script>

<AlertDialog>
	<AlertDialogTrigger class="cn-button-destructive-outline">Delete Account</AlertDialogTrigger>
	<AlertDialogPopup>
		<AlertDialogHeader>
			<AlertDialogTitle>Are you absolutely sure?</AlertDialogTitle>
			<AlertDialogDescription>
				This action cannot be undone. This will permanently delete your account and remove your data
				from our servers.
			</AlertDialogDescription>
		</AlertDialogHeader>
		<AlertDialogFooter>
			<AlertDialogCancel>Cancel</AlertDialogCancel>
			<AlertDialogAction>Delete Account</AlertDialogAction>
		</AlertDialogFooter>
	</AlertDialogPopup>
</AlertDialog>
```

## Key contracts

- Keep trigger, popup, title, description, footer, cancel, and action inside `AlertDialog`.
- When composing exported parts, omit root `title`/`description`; those props activate the convenience scaffold.
- Bindable contract: `bind:open`.

## Anatomy

- `AlertDialog`
- `AlertDialogAction`
- `AlertDialogCancel`
- `AlertDialogDescription`
- `AlertDialogFooter`
- `AlertDialogHeader`
- `AlertDialogPopup`
- `AlertDialogTitle`
- `AlertDialogTrigger`

## Common pitfalls

- Do not copy React/JSX, Base UI, Radix, shadcn, `asChild`, `render`, `className`, or `onClick` patterns into Svelte.
- Do not invent parts or bindings absent from the package declarations.
- Do not treat the upstream particle count as installable Svelte particle manifests.

## Pattern sources

- Search [the upstream pattern index](../particles.md#alert-dialog) for 2 COSS particle descriptions, then port intent rather than TSX.
- Inspect the package declaration and component source when a prop or snippet contract is not shown here.
