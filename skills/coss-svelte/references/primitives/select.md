# Select

A common form component for choosing a predefined value in a dropdown menu.

## Status

- Status: Stable
- Foundation: bits
- Category: Selection & Input
- Particles in source inventory: 23
- COSS reference docs: https://coss.com/ui/docs/components/select.md

## Imports

```ts
import { Select, SelectGroup, SelectGroupLabel, SelectItem, SelectPopup, SelectScrollDownButton, SelectScrollUpButton, SelectTrigger, SelectValue, SelectViewport } from "coss-svelte";
```

## Minimal Svelte Pattern

```svelte
<script lang="ts">
	import { Select, SelectItem, SelectPopup, SelectTrigger, SelectValue, SelectViewport } from "coss-svelte";
</script>

<Select value="editor">
	<SelectTrigger>
		<SelectValue placeholder="Select role" />
	</SelectTrigger>
	<SelectPopup>
		<SelectViewport>
			<SelectItem value="viewer">Viewer</SelectItem>
			<SelectItem value="editor">Editor</SelectItem>
		</SelectViewport>
	</SelectPopup>
</Select>
```

## Anatomy

- `Select`
- `SelectGroup`
- `SelectGroupLabel`
- `SelectItem`
- `SelectPopup`
- `SelectScrollDownButton`
- `SelectScrollUpButton`
- `SelectTrigger`
- `SelectValue`
- `SelectViewport`

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
