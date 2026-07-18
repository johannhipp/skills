# Toast

An experimental local notification surface with bindable visibility, not a queue or manager API.

> Experimental: verify the installed source before relying on production parity.

## Status and source

- Status: experimental
- Foundation: custom
- Category: Feedback & Status
- Local docs route: `/docs/components/toast.md` when the coss-svelte docs app is running
- Registry artifact: `apps/registry/static/r/toast.json`
- Upstream COSS design reference: <https://coss.com/ui/docs/components/toast.md>

## Avoid when

- Do not use when the message must persist or interrupt the workflow.

## Public imports

```ts
import { Toast } from "coss-svelte";
```

## Canonical Svelte pattern

```svelte
<script lang="ts">
	import { Button, Toast } from "coss-svelte";

	let open = $state(false);
</script>

<Button type="button" variant="outline" onclick={() => (open = true)}>Show toast</Button>
<Toast bind:open title="Saved" description="Your changes are up to date." />
```

## Key contracts

- Experimental: this is a local bindable status surface, not COSS React `toastManager`, Sonner, or a provider/queue system.
- Bind `open` for visibility and use Alert for persistent feedback or AlertDialog for blocking confirmation.
- Bindable contract: `bind:open`.

## Anatomy

- `Toast`

## Common pitfalls

- Do not copy React/JSX, Base UI, Radix, shadcn, `asChild`, `render`, `className`, or `onClick` patterns into Svelte.
- Do not invent parts or bindings absent from the package declarations.
- Do not treat the upstream particle count as installable Svelte particle manifests.

## Pattern sources

- Search [the upstream pattern index](../particles.md#toast) for 13 COSS particle descriptions, then port intent rather than TSX.
- Inspect the package declaration and component source when a prop or snippet contract is not shown here.
