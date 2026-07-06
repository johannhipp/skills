# Sheet

A flyout that opens from the side of the screen, based on the dialog component.

## Status

- Status: Stable
- Foundation: compound
- Category: Overlays & Popups
- Particles in source inventory: 3
- COSS reference docs: https://coss.com/ui/docs/components/sheet.md

## Imports

```ts
import { Sheet, SheetClose, SheetContent, SheetDescription, SheetFooter, SheetHeader, SheetPanel, SheetPopup, SheetTitle, SheetTrigger } from "coss-svelte";
```

## Minimal Svelte Pattern

```svelte
<script lang="ts">
	import { Sheet, SheetClose, SheetContent, SheetDescription, SheetFooter, SheetHeader } from "coss-svelte";
</script>

<Sheet>
	<SheetClose>Sheet</SheetClose>
</Sheet>
```

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
