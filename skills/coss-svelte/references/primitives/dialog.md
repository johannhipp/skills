# Dialog

A modal overlay for displaying content that requires user interaction.

## Status

- Status: Stable
- Foundation: bits
- Category: Overlays & Popups
- Particles in source inventory: 6
- COSS reference docs: https://coss.com/ui/docs/components/dialog.md

## Imports

```ts
import { Dialog, DialogClose, DialogDescription, DialogFooter, DialogHeader, DialogPanel, DialogPopup, DialogTitle, DialogTrigger } from "coss-svelte";
```

## Minimal Svelte Pattern

```svelte
<script lang="ts">
	import { Button, Dialog, DialogClose, DialogDescription, DialogFooter, DialogHeader, DialogPopup, DialogTitle, DialogTrigger } from "coss-svelte";
</script>

<Dialog>
	<DialogTrigger>Edit profile</DialogTrigger>
	<DialogPopup>
		<DialogHeader>
			<DialogTitle>Edit profile</DialogTitle>
			<DialogDescription>Update workspace details.</DialogDescription>
		</DialogHeader>
		<DialogFooter>
			<DialogClose>Cancel</DialogClose>
			<Button type="submit">Save</Button>
		</DialogFooter>
	</DialogPopup>
</Dialog>
```

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
