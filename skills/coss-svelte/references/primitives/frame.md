# Frame

A container component for displaying content in a frame.

## Status and source

- Status: stable
- Foundation: native
- Category: Content & Display
- Local docs route: `/docs/components/frame.md` when the coss-svelte docs app is running
- Registry artifact: `apps/registry/static/r/frame.json`
- Upstream COSS design reference: <https://coss.com/ui/docs/components/frame.md>

## Public imports

```ts
import {
	Frame,
	FrameDescription,
	FrameFooter,
	FrameHeader,
	FramePanel,
	FrameTitle,
} from "coss-svelte";
```

## Canonical Svelte pattern

```svelte
<script lang="ts">
	import { Frame, FrameDescription, FrameFooter, FrameHeader, FramePanel, FrameTitle } from "coss-svelte";
</script>

<Frame class="w-full max-w-sm">
	<FrameHeader>
		<FrameTitle>Section header</FrameTitle>
		<FrameDescription>Brief description about the section</FrameDescription>
	</FrameHeader>
	<FramePanel>
		<h2 class="font-semibold text-sm">Section title</h2>
		<p class="text-muted-foreground text-sm">Section description</p>
	</FramePanel>
	<FrameFooter>
		<p class="text-muted-foreground text-sm">Footer</p>
	</FrameFooter>
</Frame>
```

## Key contracts

- Use Frame for bordered product surfaces; preserve header/panel/footer hierarchy and avoid nesting frames without a clear information hierarchy.

## Anatomy

- `Frame`
- `FrameDescription`
- `FrameFooter`
- `FrameHeader`
- `FramePanel`
- `FrameTitle`

## Common pitfalls

- Do not copy React/JSX, Base UI, Radix, shadcn, `asChild`, `render`, `className`, or `onClick` patterns into Svelte.
- Do not invent parts or bindings absent from the package declarations.
- Do not treat the upstream particle count as installable Svelte particle manifests.

## Pattern sources

- Search [the upstream pattern index](../particles.md#frame) for 4 COSS particle descriptions, then port intent rather than TSX.
- Inspect the package declaration and component source when a prop or snippet contract is not shown here.
