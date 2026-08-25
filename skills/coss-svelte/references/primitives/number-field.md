# Number Field

A locale-aware numeric input with increment/decrement controls, optional pointer scrubbing, and native form integration.

## Status and source

- Status: stable
- Foundation: custom
- Category: Selection & Input
- Local docs route: `/docs/components/number-field.md` when the coss-svelte docs app is running
- Registry artifact: `apps/registry/static/r/number-field.json`
- Upstream COSS design reference: <https://coss.com/ui/docs/components/number-field.md>

## Public imports

```ts
import {
	NumberField,
	NumberFieldDecrement,
	NumberFieldGroup,
	NumberFieldIncrement,
	NumberFieldInput,
	NumberFieldScrubArea,
} from "coss-svelte";
```

## Canonical Svelte pattern

```svelte
<script lang="ts">
	import { NumberField } from "coss-svelte";

	let amount = $state<number | null>(0);
</script>

<NumberField
	bind:value={amount}
	label="Amount"
	name="amount"
	min={0}
	step={1}
	onValueCommit={(value, details) => console.log(value, details.reason)}
/>
```

## Key contracts

- `bind:value` is `number | null`. Values must be finite; do not send numeric strings, `NaN`, or infinities.
- `defaultValue` is the captured native form-reset baseline. `name` serializes an invariant numeric value through the component's hidden form control; `form` can associate it with an external form.
- Text editing is parsed and formatted with `locale` and `Intl.NumberFormatOptions`. Direct text is not snapped to `step`; buttons, keys, wheel, and scrubbing use the configured step sizes.
- `onValueChange` runs for each accepted value change. `onValueCommit` runs once when the input, keyboard, button, wheel, scrub, or reset transaction commits; use it for persistence or expensive effects.
- `smallStep` is used by Alt+Arrow and `largeStep` by Shift+Arrow/PageUp/PageDown. Wheel changes are opt-in through `allowWheelScrub`.
- Convenience mode renders the scrub label, group, decrement button, input, and increment button. Custom children replace that fallback and must retain a labelled `NumberFieldInput` inside `NumberFieldGroup`.
- An enclosing Field label supplies the accessible name when root `label` is omitted. Custom `NumberFieldScrubArea` requires a non-empty `label` even when its visual children are replaced.

## Anatomy

- `NumberField`
- `NumberFieldDecrement`
- `NumberFieldGroup`
- `NumberFieldIncrement`
- `NumberFieldInput`
- `NumberFieldScrubArea`

## Common pitfalls

- Do not treat the visible locale-formatted text as the submitted value or application state.
- Do not persist on every key repeat when `onValueCommit` matches the intended transaction boundary.
- Do not copy React/JSX, Base UI, Radix, shadcn, `asChild`, `render`, `className`, or `onClick` patterns into Svelte.
- Do not invent parts or bindings absent from the package declarations.
- Do not treat the upstream particle count as installable Svelte particle manifests.

## Pattern sources

- Search [the upstream pattern index](../particles.md#number-field) for 11 COSS particle descriptions, then port intent rather than TSX.
- Inspect the package declaration and component source when a prop or snippet contract is not shown here.
