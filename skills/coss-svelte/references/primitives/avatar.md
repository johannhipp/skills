# Avatar

A visual representation of a user or entity.

## Status

- Status: Stable
- Foundation: bits
- Category: Content & Display
- Particles in source inventory: 14
- COSS reference docs: https://coss.com/ui/docs/components/avatar.md

## Imports

```ts
import { Avatar, AvatarFallback, AvatarImage } from "coss-svelte";
```

## Minimal Svelte Pattern

```svelte
<script lang="ts">
	import { Avatar, AvatarFallback, AvatarImage } from "coss-svelte";
</script>

<Avatar>
	<AvatarFallback>Avatar</AvatarFallback>
</Avatar>
```

## Anatomy

- `Avatar`
- `AvatarFallback`
- `AvatarImage`

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
