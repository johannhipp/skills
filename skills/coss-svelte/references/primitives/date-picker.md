# Date Picker

A date selection component, often combined with a calendar in a popover or input.

## Status

- Status: Stable
- Foundation: compound
- Category: Selection & Input
- Particles in source inventory: 9
- COSS reference docs: https://coss.com/ui/docs/components/date-picker.md

## Imports

```ts
import { DatePicker } from "coss-svelte";
```

## Minimal Svelte Pattern

```svelte
<script lang="ts">
	import { DatePicker } from "coss-svelte";
</script>

<DatePicker>Date Picker</DatePicker>
```

## Anatomy

- `DatePicker`

## Composition Rules

- Use the exported coss-svelte parts listed above.
- Preserve Svelte syntax and accessibility semantics.
- Prefer documented local examples before adapting upstream COSS React snippets.
- This primitive is either single-export or native-presentational in the current surface.

## Common Pitfalls

- Importing React COSS, Radix, shadcn, or Base UI APIs instead of `coss-svelte`.
- Copying JSX, hooks, `className`, `asChild`, or `render` patterns into Svelte.
- Ignoring the component status when using experimental or deferred primitives.
- Replacing accessible exported parts with anonymous divs that lose labels, roles, or focus behavior.
