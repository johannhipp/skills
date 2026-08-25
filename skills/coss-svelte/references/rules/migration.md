# Migration rules

## Port intent, not source

Translate the interaction, information hierarchy, accessibility, and visual density. Reimplement with Svelte 5 and current coss-svelte exports.

Never paste React COSS particle source or import Base UI, Radix, shadcn React, hooks, JSX, `className`, `onClick`, `asChild`, or `render` composition.

## Translate common patterns

| React/COSS assumption | coss-svelte approach |
| --- | --- |
| `className` | `class` |
| `onClick={handler}` | `onclick={handler}` |
| controlled `value` + setter | documented `bind:value` or callback prop |
| controlled `open` + setter | documented `bind:open` |
| Radix `asChild` / COSS `render` | nest exported Svelte Trigger/Popup parts |
| `items.map(...)` | `{#each items as item}` |
| Base UI primitive import | coss-svelte wrapper backed by Bits UI/native markup |
| React children render function | Svelte `{#snippet children(props)}` where declared |

Check declarations before applying any mapping; not every wrapper exposes every binding or callback.

## Translate component-specific assumptions

- **Select:** pass `options` so the root has an item collection; use string/string-array values for single/multiple modes.
- **Autocomplete/Combobox:** preserve popup/list/collection/item structure in custom mode and keep the distinction between editable suggestions and constrained selection.
- **Dialog/Sheet/Drawer:** do not pass root title/description while also composing title/description parts; keep form panels and footers inside the form.
- **Context Menu:** preserve right-click plus Shift+F10/Context Menu key access; use the dedicated item, link, checkbox, radio, and submenu parts.
- **Toast:** use the local `ToastProvider` + `toastManager` only when its basic title/description queue is sufficient. Adapt anchored managers, actions, promise states, swipe gestures, and Sonner-specific APIs instead of fabricating parity.
- **Drawer:** do not claim swipe, snap points, or nested drawer parity; the current implementation is Dialog-based.
- **NumberField:** use `number | null`, locale/format props, and its distinct change/commit callbacks. Do not port formatted input text as component state or silently substitute a native numeric Input.
- **Textarea:** verify the installed declaration before translating a React controlled value to `bind:value`.

## Port particles

1. Search [the particle pattern index](../particles.md) by desired behavior.
2. Fetch the upstream JSON only for reference.
3. Replace every React component with its coss-svelte guide and current export.
4. Replace React state/events/rendering with Svelte state, bindings, event properties, snippets, and `{#each}` blocks.
5. Adapt unsupported features to the current status boundary.
6. Compile and accessibility-check the Svelte result.
