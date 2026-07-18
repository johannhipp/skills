# OTP Field

A segmented input for one-time passwords and verification codes.

## Status and source

- Status: stable
- Foundation: bits
- Category: Selection & Input
- Local docs route: `/docs/components/otp-field.md` when the coss-svelte docs app is running
- Registry artifact: `apps/registry/static/r/otp-field.json`
- Upstream COSS design reference: <https://coss.com/ui/docs/components/otp-field.md>

## Public imports

```ts
import { OTPField, OTPFieldCell, OTPFieldInput } from "coss-svelte";
```

## Canonical Svelte pattern

```svelte
<script lang="ts">
	import { OTPField } from "coss-svelte";

	let code = $state("");
</script>

<OTPField aria-label="One-time password" bind:value={code} length={6} />
```

## Key contracts

- Keep `length` synchronized with the intended code length. The root can render cells automatically; custom cells receive the `cells` snippet payload.
- Bindable contract: `bind:value`.

## Anatomy

- `OTPField`
- `OTPFieldCell`
- `OTPFieldInput`

## Common pitfalls

- Do not copy React/JSX, Base UI, Radix, shadcn, `asChild`, `render`, `className`, or `onClick` patterns into Svelte.
- Do not invent parts or bindings absent from the package declarations.
- Do not treat the upstream particle count as installable Svelte particle manifests.

## Pattern sources

- Search [the upstream pattern index](../particles.md#otp-field) for 9 COSS particle descriptions, then port intent rather than TSX.
- Inspect the package declaration and component source when a prop or snippet contract is not shown here.
