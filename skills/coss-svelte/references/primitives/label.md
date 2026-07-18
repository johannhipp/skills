# Label

Renders an accessible label associated with controls.

## Status and source

- Status: stable
- Foundation: bits
- Category: Forms & Validation
- Local docs route: `/docs/components/label.md` when the coss-svelte docs app is running
- Registry artifact: `apps/registry/static/r/label.json`
- Upstream COSS design reference: <https://coss.com/ui/docs/components/label.md>

## Public imports

```ts
import { Label } from "coss-svelte";
```

## Canonical Svelte pattern

```svelte
<script lang="ts">
	import { Input, Label } from "coss-svelte";
</script>

<Label class="grid gap-2">
	<span>Email</span>
	<Input name="email" placeholder="jane@example.com" type="email" />
</Label>
```

## Key contracts

- The current generic Label declaration does not expose a `for` prop. Nest the control for native implicit association, or use Field/FieldLabel for composed forms.
- Re-check the installed declaration before switching to an explicit `for`/`id` pair; do not suppress the type error.

## Anatomy

- `Label`

## Common pitfalls

- Do not copy React/JSX, Base UI, Radix, shadcn, `asChild`, `render`, `className`, or `onClick` patterns into Svelte.
- Do not invent parts or bindings absent from the package declarations.
- Do not treat the upstream particle count as installable Svelte particle manifests.

## Pattern sources

- No upstream COSS particle inventory is recorded for this component.
- Inspect the package declaration and component source when a prop or snippet contract is not shown here.
