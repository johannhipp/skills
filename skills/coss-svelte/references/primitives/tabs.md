# Tabs

A navigation component for switching between different views or content panels.

## Status

- Status: Stable
- Foundation: bits
- Category: Layout & Navigation
- Particles in source inventory: 13
- COSS reference docs: https://coss.com/ui/docs/components/tabs.md

## Imports

```ts
import { Tabs, TabsContent, TabsList, TabsTrigger } from "coss-svelte";
```

## Minimal Svelte Pattern

```svelte
<script lang="ts">
	import { Tabs, TabsContent, TabsList, TabsTrigger } from "coss-svelte";
</script>

<Tabs>
	<TabsContent>Tabs</TabsContent>
</Tabs>
```

## Anatomy

- `Tabs`
- `TabsContent`
- `TabsList`
- `TabsTrigger`

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
