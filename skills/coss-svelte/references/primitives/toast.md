# Toast

An experimental notification surface with a local provider and queue manager.

> Experimental: verify the installed source before relying on production parity.

## Status and source

- Status: experimental
- Foundation: custom
- Category: Feedback & Status
- Local docs route: `/docs/components/toast.md` when the coss-svelte docs app is running
- Registry artifact: `apps/registry/static/r/toast.json`
- Upstream COSS design reference: <https://coss.com/ui/docs/components/toast.md>

## Avoid when

- Use Alert for persistent in-page feedback and AlertDialog for a blocking confirmation.

## Public imports

```ts
import { Toast, ToastProvider, toastManager } from "coss-svelte";
```

## Canonical Svelte pattern

```svelte
<script lang="ts">
	import { Button, ToastProvider, toastManager } from "coss-svelte";
</script>

<ToastProvider>
	<Button
		type="button"
		variant="outline"
		onclick={() =>
			toastManager.add({
				title: "Event created",
				description: "Monday at 6:00 PM",
			})}
	>
		Show toast
	</Button>
</ToastProvider>
```

## Key contracts

- Mount one `ToastProvider` around the subtree that triggers managed notifications. It subscribes to the shared manager and renders the notification viewport.
- `toastManager.add({ title, description?, duration?, dismissible?, id? })` returns the resolved ID. Reusing an ID replaces the previous entry; `toastManager.close(id)` removes it.
- The default duration is 5000 ms. Use `duration: 0` for a toast that remains until explicitly closed.
- `Toast` remains directly usable as a local status surface with `bind:open`, `title`, `description`, `dismissible`, and `ondismiss`.
- This is not full upstream COSS parity: there are no anchored managers, actions, promise states, swipe gestures, placement variants, or Sonner API.

## Anatomy

- `Toast`
- `ToastProvider`
- `toastManager`

## Common pitfalls

- Do not call `toastManager.add` without mounting a provider in the rendered application.
- Do not create a second application-specific queue around `toastManager` unless the missing behavior genuinely requires it.
- Do not copy React/JSX, Base UI, Radix, shadcn, `asChild`, `render`, `className`, or `onClick` patterns into Svelte.
- Do not invent parts or bindings absent from the package declarations.
- Do not treat the upstream particle count as installable Svelte particle manifests.

## Pattern sources

- Search [the upstream pattern index](../particles.md#toast) for 13 COSS particle descriptions, then port intent rather than TSX.
- Inspect the package declaration and component source when a prop or snippet contract is not shown here.
