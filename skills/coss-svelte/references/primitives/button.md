# Button

A button or a component that looks like a button.

## Status and source

- Status: stable
- Foundation: native
- Category: Actions
- Local docs route: `/docs/components/button.md` when the coss-svelte docs app is running
- Registry artifact: `apps/registry/static/r/button.json`
- Upstream COSS design reference: <https://coss.com/ui/docs/components/button.md>

## Public imports

```ts
import { Button } from "coss-svelte";
```

## Canonical Svelte pattern

```svelte
<script lang="ts">
	import { Button } from "coss-svelte";
</script>

<Button type="submit">Save changes</Button>
<Button type="button" variant="outline">Cancel</Button>
```

## Key contracts

- Set `type` explicitly in forms. `href` renders an anchor; otherwise Button renders a native button.
- Use `loading` for the built-in spinner/disabled state and prefer `variant`/`size` over one-off classes.

## Anatomy

- `Button`

## Common pitfalls

- Do not copy React/JSX, Base UI, Radix, shadcn, `asChild`, `render`, `className`, or `onClick` patterns into Svelte.
- Do not invent parts or bindings absent from the package declarations.
- Do not treat the upstream particle count as installable Svelte particle manifests.

## Pattern sources

- Search [the upstream pattern index](../particles.md#button) for 40 COSS particle descriptions, then port intent rather than TSX.
- Inspect the package declaration and component source when a prop or snippet contract is not shown here.
