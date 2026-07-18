# Drawer

An experimental Dialog-backed drawer surface without swipe, snap-point, or nested-drawer parity.

> Experimental: verify the installed source before relying on production parity.

## Status and source

- Status: experimental
- Foundation: custom
- Category: Overlays & Popups
- Local docs route: `/docs/components/drawer.md` when the coss-svelte docs app is running
- Registry artifact: `apps/registry/static/r/drawer.json`
- Upstream COSS design reference: <https://coss.com/ui/docs/components/drawer.md>

## Avoid when

- Do not promise gesture-driven mobile behavior until the experimental implementation provides it.

## Public imports

```ts
import {
	Drawer,
	DrawerClose,
	DrawerContent,
	DrawerCreateHandle,
	DrawerDescription,
	DrawerFooter,
	DrawerHeader,
	DrawerPanel,
	DrawerPopup,
	DrawerTitle,
	DrawerTrigger,
} from "coss-svelte";
```

## Canonical Svelte pattern

```svelte
<script lang="ts">
	import {
		Drawer,
		DrawerClose,
		DrawerCreateHandle,
		DrawerDescription,
		DrawerFooter,
		DrawerHeader,
		DrawerPopup,
		DrawerTitle,
		DrawerTrigger,
	} from "coss-svelte";
</script>

<Drawer>
	<DrawerTrigger>Open drawer</DrawerTrigger>
	<DrawerPopup>
		<DrawerCreateHandle />
		<DrawerHeader class="text-center">
			<DrawerTitle>Notifications</DrawerTitle>
			<DrawerDescription>This is the description of the drawer.</DrawerDescription>
		</DrawerHeader>
		<DrawerFooter>
			<DrawerClose>Close</DrawerClose>
		</DrawerFooter>
	</DrawerPopup>
</Drawer>
```

## Key contracts

- Experimental: the current implementation is Dialog-based and does not promise swipe gestures, snap points, or upstream COSS drawer parity.
- Use the exported trigger/popup/header/panel/footer/close anatomy and bind `open` when state is controlled.
- Bindable contract: `bind:open`.

## Anatomy

- `Drawer`
- `DrawerClose`
- `DrawerContent`
- `DrawerCreateHandle`
- `DrawerDescription`
- `DrawerFooter`
- `DrawerHeader`
- `DrawerPanel`
- `DrawerPopup`
- `DrawerTitle`
- `DrawerTrigger`

## Common pitfalls

- Do not copy React/JSX, Base UI, Radix, shadcn, `asChild`, `render`, `className`, or `onClick` patterns into Svelte.
- Do not invent parts or bindings absent from the package declarations.
- Do not treat the upstream particle count as installable Svelte particle manifests.

## Pattern sources

- Search [the upstream pattern index](../particles.md#drawer) for 14 COSS particle descriptions, then port intent rather than TSX.
- Inspect the package declaration and component source when a prop or snippet contract is not shown here.
