# Popover

A floating container that appears near a trigger element.

## Status and source

- Status: stable
- Foundation: bits
- Category: Overlays & Popups
- Local docs route: `/docs/components/popover.md` when the coss-svelte docs app is running
- Registry artifact: `apps/registry/static/r/popover.json`
- Upstream COSS design reference: <https://coss.com/ui/docs/components/popover.md>

## Avoid when

- Do not use for modal flows or destructive confirmation.

## Public imports

```ts
import {
	Popover,
	PopoverClose,
	PopoverDescription,
	PopoverPopup,
	PopoverTitle,
	PopoverTrigger,
} from "coss-svelte";
```

## Canonical Svelte pattern

```svelte
<script lang="ts">
	import {
		Button,
		Field,
		Form,
		Popover,
		PopoverClose,
		PopoverDescription,
		PopoverPopup,
		PopoverTitle,
		PopoverTrigger,
		Textarea,
	} from "coss-svelte";
</script>

<Popover>
	<PopoverTrigger>Open Popover</PopoverTrigger>
	<PopoverPopup class="w-80">
		<div class="mb-4">
			<PopoverTitle class="text-base">Send us feedback</PopoverTitle>
			<PopoverDescription>Let us know how we can improve.</PopoverDescription>
		</div>
		<Form class="flex w-full flex-col gap-4">
			<Field>
				<Textarea aria-label="Send feedback" id="feedback" placeholder="How can we improve?" />
			</Field>
			<Button type="submit">Send feedback</Button>
		</Form>
		<PopoverClose class="sr-only">Close</PopoverClose>
	</PopoverPopup>
</Popover>
```

## Key contracts

- Use for non-modal anchored content. Preserve trigger/popup and add title/description for richer content; use Tooltip for short hints.
- Bindable contract: `bind:open`.

## Anatomy

- `Popover`
- `PopoverClose`
- `PopoverDescription`
- `PopoverPopup`
- `PopoverTitle`
- `PopoverTrigger`

## Common pitfalls

- Do not copy React/JSX, Base UI, Radix, shadcn, `asChild`, `render`, `className`, or `onClick` patterns into Svelte.
- Do not invent parts or bindings absent from the package declarations.
- Do not treat the upstream particle count as installable Svelte particle manifests.

## Pattern sources

- Search [the upstream pattern index](../particles.md#popover) for 3 COSS particle descriptions, then port intent rather than TSX.
- Inspect the package declaration and component source when a prop or snippet contract is not shown here.
