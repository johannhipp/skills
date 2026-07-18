# Meter

A visual representation of a value within a known range.

## Status and source

- Status: stable
- Foundation: bits
- Category: Feedback & Status
- Local docs route: `/docs/components/meter.md` when the coss-svelte docs app is running
- Registry artifact: `apps/registry/static/r/meter.json`
- Upstream COSS design reference: <https://coss.com/ui/docs/components/meter.md>

## Avoid when

- Do not use for task progress; use Progress.

## Public imports

```ts
import {
	Meter,
	MeterIndicator,
	MeterLabel,
	MeterTrack,
	MeterValue,
} from "coss-svelte";
```

## Canonical Svelte pattern

```svelte
<script lang="ts">
	import { Meter, MeterIndicator, MeterLabel, MeterTrack, MeterValue } from "coss-svelte";
</script>

<Meter value={75} class="w-full max-w-sm">
	<div class="flex items-center justify-between gap-2">
		<MeterLabel>Storage usage</MeterLabel>
		<MeterValue>75%</MeterValue>
	</div>
	<MeterTrack>
		<MeterIndicator />
	</MeterTrack>
</Meter>
```

## Key contracts

- Use Meter for a bounded measurement such as storage; use Progress for task completion. Supply value/min/max and an accessible label.

## Anatomy

- `Meter`
- `MeterIndicator`
- `MeterLabel`
- `MeterTrack`
- `MeterValue`

## Common pitfalls

- Do not copy React/JSX, Base UI, Radix, shadcn, `asChild`, `render`, `className`, or `onClick` patterns into Svelte.
- Do not invent parts or bindings absent from the package declarations.
- Do not treat the upstream particle count as installable Svelte particle manifests.

## Pattern sources

- Search [the upstream pattern index](../particles.md#meter) for 4 COSS particle descriptions, then port intent rather than TSX.
- Inspect the package declaration and component source when a prop or snippet contract is not shown here.
