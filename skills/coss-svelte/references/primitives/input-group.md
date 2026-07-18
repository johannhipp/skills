# Input Group

A flexible component for grouping inputs with addons, buttons, and other elements.

## Status and source

- Status: stable
- Foundation: compound
- Category: Selection & Input
- Local docs route: `/docs/components/input-group.md` when the coss-svelte docs app is running
- Registry artifact: `apps/registry/static/r/input-group.json`
- Upstream COSS design reference: <https://coss.com/ui/docs/components/input-group.md>

## Public imports

```ts
import {
	InputGroup,
	InputGroupAddon,
	InputGroupInput,
	InputGroupText,
	InputGroupTextarea,
} from "coss-svelte";
```

## Canonical Svelte pattern

```svelte
<script lang="ts">
	import { InputGroup, InputGroupAddon, InputGroupInput, InputGroupText } from "coss-svelte";
</script>

<InputGroup>
	<InputGroupInput aria-label="Domain" placeholder="example.com" type="text" />
	<InputGroupAddon align="inline-start"><InputGroupText>https://</InputGroupText></InputGroupAddon>
</InputGroup>
```

## Key contracts

- Use InputGroupInput/InputGroupTextarea rather than standalone Input/Textarea.
- Keep addons after the control in DOM order; use `align` to position them visually.

## Anatomy

- `InputGroup`
- `InputGroupAddon`
- `InputGroupInput`
- `InputGroupText`
- `InputGroupTextarea`

## Common pitfalls

- Do not copy React/JSX, Base UI, Radix, shadcn, `asChild`, `render`, `className`, or `onClick` patterns into Svelte.
- Do not invent parts or bindings absent from the package declarations.
- Do not treat the upstream particle count as installable Svelte particle manifests.

## Pattern sources

- Search [the upstream pattern index](../particles.md#input-group) for 28 COSS particle descriptions, then port intent rather than TSX.
- Inspect the package declaration and component source when a prop or snippet contract is not shown here.
