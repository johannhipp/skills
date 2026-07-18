# Alert

A callout for displaying important information.

## Status and source

- Status: stable
- Foundation: native
- Category: Feedback & Status
- Local docs route: `/docs/components/alert.md` when the coss-svelte docs app is running
- Registry artifact: `apps/registry/static/r/alert.json`
- Upstream COSS design reference: <https://coss.com/ui/docs/components/alert.md>

## Avoid when

- Do not use for a destructive confirmation; use AlertDialog.

## Public imports

```ts
import {
	Alert,
	AlertAction,
	AlertDescription,
	AlertTitle,
} from "coss-svelte";
```

## Canonical Svelte pattern

```svelte
<script lang="ts">
	import { Alert, AlertDescription, AlertTitle } from "coss-svelte";
</script>

<Alert>
	<AlertTitle>Heads up!</AlertTitle>
	<AlertDescription>Describe what can be done about it here.</AlertDescription>
</Alert>
```

## Key contracts

- Use a semantic `role` appropriate to the message; use AlertDialog when progress must stop for acknowledgment.

## Anatomy

- `Alert`
- `AlertAction`
- `AlertDescription`
- `AlertTitle`

## Common pitfalls

- Do not copy React/JSX, Base UI, Radix, shadcn, `asChild`, `render`, `className`, or `onClick` patterns into Svelte.
- Do not invent parts or bindings absent from the package declarations.
- Do not treat the upstream particle count as installable Svelte particle manifests.

## Pattern sources

- Search [the upstream pattern index](../particles.md#alert) for 7 COSS particle descriptions, then port intent rather than TSX.
- Inspect the package declaration and component source when a prop or snippet contract is not shown here.
